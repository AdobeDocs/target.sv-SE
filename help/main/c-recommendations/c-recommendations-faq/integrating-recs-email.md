---
keywords: e-post;ESP;e-postleverantör;rawbox;delivery API;download only template;email template;batch processing;build-time email
description: Lär dig hur du integrerar e-post med Adobe [!DNL Target Recommendations], including using the [!DNL Target] Delivery API, rawbox templates och down-load only templates.
title: Hur integrerar jag Recommendations med e-post?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
source-git-commit: 1f505991ea9a0caf0d6d49f6464550243128ffaf
workflow-type: tm+mt
source-wordcount: '1715'
ht-degree: 0%

---

# Integrera [!DNL Recommendations] med e-post

[!DNL Adobe Target] stöder personalisering av rekommendationer i e-postmeddelanden vid sändning.

Tre integreringsmetoder [!DNL Target Recommendations] med din e-postleverantör (ESP) är tillgänglig. ESP:s funktioner avgör vilken metod som ska användas. Din kontoansvarige eller konsult kan hjälpa dig att välja det alternativ som passar dig bäst.

| Metod | Detaljer |
| --- | --- |
| [Metod 1: [!DNL Adobe Target Delivery API]](#delivery-api) (Önskat) | Använd [!DNL Adobe Target Delivery API] för att skapa rekommendationer per kund/per e-post. |
| [Metod 2: [!DNL Adobe Rawbox API]](#rawbox) | Använd [!DNL Adobe Target Rawbox API] för att skapa rekommendationer per kund/per e-post. |
| [Metod 3: [!DNL Recommendations Download API]](#download-api) | Använd Recommendations Download API för att begära massrekommendationer för en lista över produkter eller kategorier i CSV-format. |

Om du använder metod 1 eller metod 2 måste ESP ringa anrop till ett externt API per kund/per e-post och vänta på att innehållet returneras. Dessa metoder stöds inte av alla ESP:er. kontakta din ESP för att avgöra om den är kompatibel med det här integreringsmönstret.

Om du använder metod 3 måste din ESP ansluta till en lista med rekommendationer per produkt-ID eller kategori-ID i din lista med e-postmeddelanden. Den här metoden kan baseras på ett attribut som kundens senast visade produkt, den senast köpta produkten eller den mest visade kategorin. Din ESP måste dock ha tillgång till dessa data i sin kundprofil för att kunna genomföra kopplingen. Kontakta din ESP för att avgöra om den har tillgång till dessa data och är kompatibel med det här integreringsmönstret.

Anpassning av rekommendationer i öppen tid stöds inte av [!DNL Adobe Target].

>[!IMPORTANT]
>
>Följande riktlinjer för kapacitet gäller för e-postmallsmetoderna Delivery API och rawbox som beskrivs nedan (metoderna 1 och 2):
>
>* Begäranden bör begränsas till det lägre av 1 000 förfrågningar per sekund eller 25 gånger din högsta dagliga trafik.
>* Ramptrafik i steg om 200 förfrågningar per sekund varje minut.
> 
>Kontakta din kontoansvarige om du vill använda högre avgiftsgränser.

## Metod 1: Använd leverans-API (standard) {#delivery-api}

Leverans-API:t är en begäran om POST som fungerar med e-post vid byggtid. Det här alternativet är den rekommenderade metoden för e-post under byggtid.

De flesta e-postklienter tillåter inte förfrågningar från POSTER. Detta API rekommenderas därför inte för användningsfall under öppen tid. Vissa e-postklienter, som Gmail eller Outlook, kan cachelagra innehållet eller blockera bilden och kräva att mottagaren aktivt tillåter att bilden återges.

Du kan inte returnera standardinnehåll med leverans-API:t.

Följande kod är ett exempel på en API-leveransbegäran:

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

Plats `clientcode` är din [!DNL Target] klientkod.

>[!NOTE]
>
>Var noga med att ange ett unikt värde för båda `sessionId` och en av `tntId` eller `thirdPartyId` för varje e-postmottagare (till exempel för varje API-anrop). Om du inte anger unika värden för de här fälten kan API-svar ta lång tid eller misslyckas på grund av många händelser som genereras i en enskild profil.

Se [Dokumentation för leverans-API](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html){target=_blank} för mer information.

## Metod 2: Använda en e-postmall för en rawbox {#rawbox}

En sandlåda liknar en mbox-begäran, men för icke-webbmiljöer, som e-postleverantörer (ESP). För du har inte [!DNL Adobe Experience Platform Web SDK] eller [!DNL at.js] om du vill använda i en rawbox-begäran måste du skapa din begäran manuellt. Exemplen nedan förklarar hur du arbetar med rawbox-begäranden i e-postmeddelanden.

>[!NOTE]
>
>När du använder en radruta och [!DNL Target], se viktig säkerhetsinformation i [Skapa tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist).

Med den här metoden kan du följa upp hur rekommendationerna fungerar i e-postmeddelanden, testa dem på det vanliga sättet med en rekommendation och fortsätta spåra dem på webbplatsen.

Konfigurera en [!DNL Recommendations] aktivitet i [!DNL Target], med [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) alternativ. För platsen väljer du namnet på den mbox som du har valt att använda i den rawbox-begäran som kommer från ESP. Välj en design med det utseende och den känsla du vill ha för e-postmeddelandet. När ESP skapar e-postmeddelanden ringer de [!DNL Target] servrar för varje enskild kryssruta i varje e-postmeddelande som genereras. Din ESP måste ha ett sätt att inkludera den returnerade HTML i e-postmeddelandet när det skickas.

E-postsystemet du använder måste kunna hantera följande scenarier:

### Ett giltigt svar togs emot, men det finns inga rekommendationer

* I det här fallet är svaret det som anges som `mboxDefault` parametervärde. Se förklaringen nedan om den här parametern.
* E-postprovidern bör ha ett standardblock med rekommendationer i HTML som ska användas i det här fallet.

### The [!DNL Target] servern gör timeout och returnerar utan data

* I det här fallet [!DNL Target] servern returnerar följande innehåll:

   `//ERROR: application server timeout`

* E-postprogrammet bör söka efter den texten och måste kunna hantera felet. E-postleverantören har flera alternativ för att hantera det här fallet:

   * Prova ett annat serversamtal omedelbart (rekommenderas, kanske med en räknare).
   * Kasta bort just det mejlet och fortsätt till nästa.
   * Köa just den e-postadressen och kör misslyckade e-postmeddelanden som en batch i slutet av den första körningen.

### URL för exempelbegäran

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Obligatoriska parametrar: {#reqparams}

>[!NOTE]
>
>Används [!DNL Recommendations] i e-postmeddelanden måste anropet till rawbox vanligtvis innehålla antingen `entity.id` eller `entity.categoryId` eller båda, beroende på typen av rekommendationskriterier. Samtalet ovan innehåller båda.

| Parameter | Värde | Beskrivning | Validering |
|--- |--- |--- |--- |
| `client_code` | *client_code* | Kundens kod som används i Recommendations. Din Adobe-konsult kan ge det här värdet. |  |
| `mbox` | *mboxName* | Det mbox-namn som används för mål. | Samma validering som för alla mbox-anrop.<br>Högst 250 tecken.<br>Kan inte innehålla något av följande tecken: `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | inaktiverad | Förhindrar att svaret ställer in en cookie i icke-webbmiljöer. |  |
| `entity.id`<br>(Krävs för vissa typer av kriterier: vy/vy, vy/köpt, köpt/köpt) | *entity_id* | Produkt-ID som rekommendationen baseras på, till exempel en övergiven produkt i kundvagnen eller ett tidigare köp.<br>Om det krävs enligt kriterierna måste anropet till rawbox innehålla `entity.id`. |  |
| `entity.event.detailsOnly` | true | If `entity.id` vi skickar är det mycket lämpligt att skicka den här parametern även för att förhindra att begäran ökar antalet tallied-sidvisningar för ett objekt, så att man inte skevar produktvybaserade algoritmer. |  |
| `entity.categoryId`<br>(Krävs för vissa typer av kriterier: mest visade per kategori och bästsäljare per kategori) | *category_id* | Den kategori som rekommendationen baseras på, till exempel de främsta säljarna i en kategori.<br>Om det krävs enligt kriterierna måste anropet till rawbox innehålla `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Om `mboxNoRedirect` parametern finns inte, `mboxDefault` ska vara en absolut URL som returnerar standardinnehåll om ingen rekommendation är tillgänglig. Den här URL:en kan vara en bild eller annat statiskt innehåll.<br>Om `mboxNoRedirect` parametern finns, `mboxDefault` kan vara vilken text som helst som indikerar att det inte finns några rekommendationer, till exempel `no_content`.<br>E-postleverantören måste hantera det fall där det här värdet returneras och infoga HTML i e-postmeddelandet. <br> **Bästa praxis för säkerhet**: Om domänen som används i `mboxDefault` URL:en är inte tillåtslista, du kan utsättas för en risk för ett Open Redirect-fel. För att undvika obehörig användning av omdirigeringslänkar eller `mboxDefault` av tredje part rekommenderar Adobe att du använder&quot;auktoriserade värdar&quot; för att tillåtslista standarddomänerna för omdirigering av URL-adresser. Target använder värdar för att tillåtslista domäner som du vill tillåta omdirigeringar till. Mer information finns i [Skapa Tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist) in *Värdar*. |  |
| `mboxHost` | *mbox_host* | Domänen som läggs till i standardmiljön (värdgruppen) när anropet utlöses. |  |
| `mboxPC` | Tom | (Krävs för rekommendationer som använder en besökarprofil.)<br>Om inget&quot;thirdPartyId&quot; har angetts genereras ett nytt tntId som returneras som en del av svaret. Annars förblir den tom.<br>**Anteckning**: Var noga med att ange det unika värdet `mboxSession` och `mboxPC` för varje e-postmottagare (dvs. för varje API-anrop). Om du inte anger unika värden för de här fälten kan API-svar ta lång tid eller misslyckas på grund av det stora antalet händelser som genereras i en enskild profil. | 1 &lt; längd &lt; 128<br>Kan inte innehålla mer än en enskild &quot;.&quot; (punkt).<br>Den enda tillåtna punkten är för profilplatsens suffix. |

### Valfria parametrar

| Parameter | Värde | Beskrivning | Validering |
|--- |--- |--- |--- |
| `mboxPC`<br>(Valfritt) | *mboxPCId* | Målbesökar-ID. Använd det här värdet om du vill spåra en användares fullständiga cirkel tillbaka till webbplatsen vid flera besök eller när du använder en användarprofilsparameter.<br>Värdet måste vara det faktiska [!DNL Adobe Target] PCID för användaren, som skulle exporteras från webbplatsen till din CRM. E-postleverantören hämtar detta ID från CRM eller Data warehouse och använder det som värde för den här parametern.<br>The `mboxPC` Värdet är också användbart för att spåra besökares webbplatsbeteende vid flera besök för mätspårning när en rekommendation ingår i en A/B-aktivitet.<br>**Anteckning**: Var noga med att ange det unika värdet `mboxSession` och `mboxPC` för varje e-postmottagare (dvs. för varje API-anrop). Om du inte anger unika värden för de här fälten kan API-svar ta lång tid eller misslyckas på grund av det stora antalet händelser som genereras i en enskild profil. | 1 &lt; längd &lt; 128<br>Kan inte innehålla mer än en enskild &quot;.&quot; (punkt).<br>Den enda tillåtna punkten är för profilplatsens suffix. |
| `mboxNoRedirect`<br>(Valfritt) | 1 | Som standard dirigeras anroparen om när inget slutbart innehåll hittas. Används för att inaktivera standardbeteendet. |  |
| `mbox3rdPartyId` | *xxx* | Använd det här alternativet om du har ett eget anpassat besökar-ID att använda för profilanpassning. |  |

### Potentiell [!DNL Target] serversvar

| Svar | Beskrivning |
|--- |--- |
| //FEL: | Genereras av belastningsutjämnare när innehållet inte kan returneras |
| Lyckades | The `mboxNoRedirect` parametern är inställd på true och servern returnerar inga rekommendationer (d.v.s. det finns ingen matchning för mbox eller så har servercachen inte initierats). |
| felaktig begäran | The `mbox` parameter saknas.<ul><li>Antingen `mboxDefault` eller `mboxNoRedirect` parametern har inte angetts.</li><li>`mboxTrace` begärandeparametern har angetts men `mboxNoRedirect` inte.</li><li>`mboxTarget`parametern anges inte när mbox-namn slutar med `-clicked` suffix.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` inte anges när det inte finns någon matchning för begäran och `mboxNoRedirect` parametern har inte angetts. |
| `Invalid mbox name:= MBOX_NAME` | Anger `mbox` parametern innehåller ogiltiga tecken. |
| `Mbox name [MBOX_NAME] is too long` | Anger `mbox` parametern är längre än 250 tecken. |

## Metod 3: Använda Recommendations Download API {#download-api}

Konfigurera en rekommendation som vanligt, men välj **endast nedladdning** i presentationsavsnittet i stället för en mall- och mbox-kombination. I ESP anger du sedan för ESP vilket rekommendation-ID du har skapat. ESP får åtkomst till rekommendationsdata via API. Dessa data visar vilka artiklar som bör rekommenderas för en viss kategori eller nyckelartikel, t.ex. artiklar i en övergiven kundvagn. ESP lagrar dessa data, kopplar dem till sitt eget utseende, visar information om varje objekt och levererar det i e-postmeddelandena.

Med det här alternativet kan rekommendationsservern inte direkt spåra prestanda för en rekommendation eller dela trafik mellan flera algoritm-/mallkombinationer. Rekommendationerna är inte heller knutna till någon besökarprofil.

Mer information om nedladdnings-API:t finns i [Äldre API:er > Hämta](/help/main/assets/adobe-recommendations-classic.pdf).
