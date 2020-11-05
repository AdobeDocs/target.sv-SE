---
keywords: email;ESP;email service provider;rawbox;delivery API;download-only template;email template;batch processing;build-time email
description: Information om hur man integrerar e-post med Recommendations.
title: Integrera Recommendations med e-post
feature: recommendations general
topic: Recommendations
uuid: ae137d7c-58c5-4601-92fc-2dc5548760fd
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1459'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Integrera Recommendations med e-post{#integrate-recommendations-with-email}

Information om hur man integrerar e-post med Recommendations.

E-postleverantörens funktioner avgör vilken metod som ska användas. Din kontoansvarige eller konsult kan hjälpa dig att välja det alternativ som passar dig bäst.

## Alternativ 1: Använda leverans-API {#section_9F00D271BABA4B7390B461F4C44EC319}

Leverans-API:t är en begäran om POST som fungerar med e-post vid byggtid. Det här alternativet är den rekommenderade metoden för e-post under byggtid.

De flesta e-postklienter tillåter inte förfrågningar från POSTER. Därför rekommenderas inte denna API för användning i öppet läge. Vissa e-postklienter, som Gmail eller Outlook, kan cachelagra innehållet eller blockera bilden och kräva att mottagaren aktivt tillåter att bilden återges.

Du kan inte returnera standardinnehåll med leverans-API:t.

Följande kod är ett exempel på en API-leveransbegäran:

```
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

Var `clientcode` är din målklientkod?

>[!NOTE]
>
>Var noga med att ange ett unikt värde för både `sessionId` och en av `tntId` eller `thirdPartyId` för varje e-postmottagare (till exempel för varje API-anrop). Om du inte anger unika värden för de här fälten kan API-svaret ta lång tid eller misslyckas på grund av det stora antalet händelser som genereras i en enskild profil.

Mer information finns i [dokumentationen](https://developers.adobetarget.com/api/#server-side-delivery) för leverans-API.

## Alternativ 2: Använda en e-postmall för en rawbox {#section_C0D48A42BCCE45D6A68852F722C7C352}

En sandlåda liknar en mbox-begäran, men för icke-webbmiljöer, som e-postleverantörer (ESP). Eftersom du inte behöver [!DNL mbox.js] eller [!DNL at.js] kan använda i en rawbox-begäran måste du skapa din begäran manuellt. Exemplen nedan förklarar hur du arbetar med rawbox-begäranden i e-postmeddelanden.

>[!NOTE]
>
>När du använder en radruta och [!DNL Target]läser du det viktiga säkerhetsmeddelandet under [Skapa tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till Target](/help/administrating-target/hosts.md#allowlist).

Med den här metoden kan du följa upp hur rekommendationerna fungerar i e-postmeddelanden, testa dem på det vanliga sättet med en rekommendation och fortsätta spåra dem på webbplatsen.

Ställ in en [!DNL Recommendations] aktivitet i [!DNL Adobe Target]med alternativet [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) . För platsen väljer du namnet på den mbox som du har valt att använda i den rawbox-begäran som kommer från ESP. Välj en design med det utseende och den känsla du vill ha för e-postmeddelandet. När ESP skapar e-postmeddelanden ringer han/hon [!DNL Adobe Target] servrarna för varje ruta i varje e-postmeddelande som genereras. Din ESP måste ha ett sätt att inkludera den returnerade HTML-koden i e-postmeddelandet när den skickas.

E-postsystemet du använder bör kunna hantera följande scenarier:

### Ett giltigt svar togs emot, men det finns inga rekommendationer

* I det här fallet är svaret det som anges som mboxDefault-parametervärde. Se förklaringen nedan om den här parametern.
* E-postprovidern bör ha ett HTML-standardblock med rekommendationer att använda i det här fallet.

### Målservern gör timeout och returnerar utan data

* I det här fallet returnerar målservern följande innehåll:

   `//ERROR: application server timeout`

* E-postprogrammet bör söka efter den texten och kunna hantera felet. E-postleverantören har flera alternativ för att hantera det här fallet:

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
>Om du vill använda [!DNL Recommendations] i e-postmeddelanden måste rawbox-anropet oftast innehålla antingen `entity.id` eller `entity.categoryId` eller både och, beroende på typen av rekommendationskriterier. Samtalet ovan innehåller båda.

| Parameter | Värde | Beskrivning | Validering |
|--- |--- |--- |--- |
| `client_code` | *client_code* | Kundens kod som används i Recommendations. Din Adobe-konsult kan ge det här värdet. |  |
| `mbox` | *mboxName* | Det mbox-namn som används för mål. | Samma validering som för alla mbox-anrop.<br>Högst 250 tecken.<br>Kan inte innehålla något av följande tecken: `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | inaktiverad | Förhindrar att svaret ställer in en cookie i icke-webbmiljöer. |  |
| `entity.id`<br>(Krävs för vissa typer av kriterier: vy/vy, vy/köpt, köpt/köpt) | *entity_id* | Produkt-ID som rekommendationen baseras på, till exempel en övergiven produkt i kundvagnen eller ett tidigare köp.<br>Om villkoret kräver det måste anropet till rawbox innehålla `entity.id`. |  |
| `entity.event.detailsOnly` | true | Om `entity.id` skickas rekommenderas att även skicka den här parametern för att förhindra att begäran ökar antalet tallied-sidvisningar för ett objekt, så att man inte skevar produktvybaserade algoritmer. |  |
| `entity.categoryId`<br>(Krävs för vissa typer av kriterier: mest visade per kategori och bästsäljare per kategori) | *category_id* | Den kategori som rekommendationen baseras på, till exempel de främsta säljarna i en kategori.<br>Om villkoret kräver det måste anropet till rawbox innehålla `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Om `mboxNoRedirect` parametern inte finns bör `mboxDefault` den vara en absolut URL som returnerar standardinnehåll om ingen rekommendation är tillgänglig. Det kan vara en bild eller annat statiskt innehåll.<br>Om `mboxNoRedirect` parametern finns `mboxDefault` kan det vara vilken text som helst som anger att det inte finns några rekommendationer, till exempel `no_content`.<br>E-postleverantören måste hantera det fall där värdet returneras och infoga standard-HTML i e-postmeddelandet. <br> **Bästa praxis** för säkerhet: Observera att om domänen som används i URL:en inte är tillåtslista kan du utsättas för en risk för ett Open Redirect-fel. `mboxDefault` För att undvika obehörig användning av omdirigeringslänkar eller `mboxDefault` av tredje part rekommenderar vi att du använder &quot;auktoriserade värdar&quot; för att tillåtslista standarddomänerna för omdirigering av URL. Target använder värdar för att tillåtslista domäner som du vill tillåta omdirigeringar till. Mer information finns i [Skapa Tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till Target](/help/administrating-target/hosts.md#allowlist) i *Hosts*. |  |
| `mboxHost` | *mbox_host* | Det här är domänen som läggs till i standardmiljön (värdgruppen) när anropet utlöses. |  |
| `mboxPC` | Tom | (Krävs för rekommendationer som använder en besökarprofil.)<br>Om inget&quot;thirdPartyId&quot; har angetts genereras ett nytt tntId som returneras som en del av svaret. Annars förblir den tom.<br>**Obs**: Var noga med att ange det unika värdet `mboxSession` och `mboxPC` för varje e-postmottagare (dvs. för varje API-anrop). Om du inte anger unika värden för de här fälten kan API-svaret ta lång tid eller misslyckas på grund av det stora antalet händelser som genereras i en enskild profil. | 1 &lt; Längd &lt; 128<br>Får inte innehålla mer än ett enda &quot;.&quot; (punkt).<br>Den enda tillåtna punkten är för profilplatsens suffix. |

### Valfria parametrar

| Parameter | Värde | Beskrivning | Validering |
|--- |--- |--- |--- |
| `mboxPC`<br>(Valfritt) | *mboxPCId* | Målbesökar-ID. Använd det här värdet om du vill spåra en användares fullständiga cirkel tillbaka till webbplatsen vid flera besök eller när du använder en användarprofilsparameter.<br>Detta värde måste vara det faktiska Adobe Target PCID för användaren, som skulle exporteras från webbplatsen till din CRM. E-postleverantören hämtar detta ID från CRM eller Data warehouse och använder det som värde för den här parametern.<br>Värdet är också användbart för att spåra besökares webbplatsbeteende vid flera besök för mätspårning när en rekommendation ingår i en A/B-aktivitet. `mboxPC`<br>**Obs**: Var noga med att ange det unika värdet `mboxSession` och `mboxPC` för varje e-postmottagare (dvs. för varje API-anrop). Om du inte anger unika värden för de här fälten kan API-svaret ta lång tid eller misslyckas på grund av det stora antalet händelser som genereras i en enskild profil. | 1 &lt; Längd &lt; 128<br>Får inte innehålla mer än ett enda &quot;.&quot; (punkt).<br>Den enda tillåtna punkten är för profilplatsens suffix. |
| `mboxNoRedirect`<br>(Valfritt) | 1 | Som standard dirigeras anroparen om när inget slutbart innehåll hittas. Används för att inaktivera standardbeteendet. |  |
| `mbox3rdPartyId` | *xxx* | Använd det här alternativet om du har ett eget besökar-ID som du kan använda för att målinrikta profiler. |  |

### Potentiella målserversvar

| Svar | Beskrivning |
|--- |--- |
| //FEL: | Genereras av belastningsutjämnare när innehållet inte kan returneras |
| framgång | Parametern `mboxNoRedirect` är inställd på true och servern returnerar inga rekommendationer (d.v.s. det finns ingen matchning för mbox eller så har servercachen inte initierats). |
| felaktig begäran | Parametern `mbox` saknas.<ul><li>Antingen `mboxDefault` eller så har `mboxNoRedirect` parametern inte angetts.</li><li>`mboxTrace` request-parametern har angetts, men `mboxNoRedirect` är inte det.</li><li>`mboxTarget`parametern anges inte när mbox-namn slutar med `-clicked` suffix.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` anges inte när det inte finns någon matchning för begäran och `mboxNoRedirect` parametern inte har angetts. |
| `Invalid mbox name:= MBOX_NAME` | Anger att `mbox` parametern innehåller ogiltiga tecken. |
| `Mbox name [MBOX_NAME] is too long` | Anger att `mbox` parametern är längre än 250 tecken. |

## Alternativ 3: Använda mallen Endast nedladdning {#section_518C279AF0094BE780F4EA40A832A164}

Ställ in en rekommendation som vanligt, men välj bara **nedladdning** i presentationsavsnittet i stället för en mall- och mbox-kombination. I ESP anger du sedan för ESP vilket rekommendation-ID du har skapat. ESP får åtkomst till rekommendationsdata via API. Dessa data visar vilka artiklar som bör rekommenderas för en viss kategori eller nyckelartikel, t.ex. artiklar i en övergiven kundvagn. ESP lagrar dessa data, kopplar dem till sitt eget utseende, visar information om varje objekt och levererar det i e-postmeddelandena.

Med det här alternativet kan rekommendationsservern inte direkt spåra prestanda för en rekommendation eller dela trafik mellan flera algoritm-/mallkombinationer. Rekommendationerna är inte heller knutna till någon besökarprofil.

Mer information om hämtnings-API:t finns i [Äldre API:er > Hämta](/help/assets/adobe-recommendations-classic.pdf).
