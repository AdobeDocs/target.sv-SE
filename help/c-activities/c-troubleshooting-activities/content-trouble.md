---
keywords: felsökningsruta;felsökningsruta;mbox issues;flimmer;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst purchase mbox;top selling;top selling;top seller
description: Hitta förslag på hjälp med att åtgärda problem om sidan inte visar det förväntade innehållet. Lär dig hur du felsöker innehållsleverans i Adobe Target.
title: Hur felsöker jag innehållsleverans?
feature: Activities
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
source-git-commit: 4a4a0a3178c40288214bdfb0fa16f7ba83ed39cc
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# Felsöka innehållsleverans

Om sidan inte visar det förväntade innehållet kan du utföra några steg för att felsöka innehållsleveransen.

* Kontrollera aktiviteten eller kampanjkoden noggrant. Ett skrivfel eller ett annat fel kan göra att det förväntade innehållet inte visas.
* Använd mboxTrace eller mboxDebug för att felsöka [!DNL Target] begäran.
* Använd Adobe Experience Cloud Debugger, ett lättanvänt verktyg som ger mycket av samma information som mboxDebug, för att felsöka [!DNL Target] begäran.

mboxDebug är särskilt användbar när du konfigurerar [!DNL Target] på sidan för att se till att Target-begäran utlöses och att cookien ställs in. Men den går inte in på den typ av detaljer som är användbar vid felsökning av innehållsleverans. Om aktiviteten inte visas på sidan eller om oönskat innehåll visas använder du mboxTrace för att undersöka och felsöka sidan i detalj.

## Hämta den auktoriseringstoken som ska användas med felsökningsverktyg {#section_BED130298E794D1FA229DB7C3358BA54}

Eftersom mboxTrace och mboxDebug kan visa kampanjdata och profildata för externa parter krävs en auktoriseringstoken. Auktoriseringstoken kan hämtas i [!DNL Target] Gränssnitt. Token gäller i sex timmar.

Du måste ha någon av följande användarbehörigheter för att generera en autentiseringstoken:

* Minst [!UICONTROL Editor] behörighet (eller [!UICONTROL Approver])

   Mer information om [!DNL Target Standard] kunder, se [Ange roller och behörigheter](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) in *Användare*. Mer information om [!DNL Target Premium] kunder, se [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* Administratörsroll på arbetsyta/produktprofilnivå

   Arbetsytor är tillgängliga för [!DNL Target Premium] endast kunder. Mer information finns i [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* Administratörsrättigheter (behörighet som systemadministratör) på [!DNL Adobe Target] produktnivå

Så här hämtar du auktoriseringstoken:

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. I avsnittet Felsökningsverktyg klickar du på **[!UICONTROL Generate New Authentication Token]**.

   ![Generera ny autentiseringstoken](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Lägg till den genererade variabeln som en parameter i URL-adressen för att aktivera ett av de avancerade felsökningsverktygen.

   ![Auktoriseringstoken](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace gör att du kan ta emot spårningsinformation som är kopplad till [!DNL Target] svar. Spårningsinformationen återspeglar resultatet av en [!DNL Target] anropa (t.ex. en konvertering eller ett intryck) och eventuella ytterligare data som kan hjälpa till att avgöra varför just detta resultat inträffade, t.ex. en uppsättning tillgängliga grenar som urvalet gjordes i en kampanj. Använd den här informationen för att felsöka innehållsleverans.

Följande parametrar är tillgängliga:

| mboxTrace-alternativ | Resultat |
|--- |--- |
| `?mboxTrace=console` | Skriver ut som objekt i konsolloggen.<br>I stället för att öppna ett nytt webbläsarfönster eller skriva ut till konsolen som i mbox.js måste du granska nätverksbegäran och titta under Förhandsgranska (Chrome) eller Response (Firefox). |
| `?mboxTrace=json` | Skriver ut i konsolloggen som en literal JSON-sträng |
| `?mboxTrace=window` | Skriver ut i ett popup-fönster som en JSON-sträng |
| `?mboxTrace=disable` | Inaktiverar spårningssessionsläge |

**Exempel på mboxTrace-anrop**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

Utdata visar detaljerad information om ditt innehåll. mboxTrace visar information om din kampanj eller aktivitet och profil. Den innehåller även en ögonblicksbild av profilen före körning och en ögonblicksbild av vad som ändrats efter körningen. Det visar också vilka kampanjer eller aktiviteter som utvärderats för varje plats.

En del av informationen innehåller matchade och omatchade segment- och mål-ID:n:

* **SegmentId**: ID:n för segment, antingen från det återanvändbara segmentbiblioteket eller anonyma som skapats för den aktuella kampanjen.
* **TargetId**: ID:n för mål, antingen från måluttrycksbiblioteket eller anonyma mål för alla segment från kampanjen.
* **Omatchad**: Begäran var inte berättigad i denna inbjudan för dessa segment eller mål.
* **Matchad**: Begäran kvalificerad för de angivna segmenten eller målen.

**Använda mboxTrace på rekommendationssidor**: Om du lägger till mboxTrace som en frågeparameter på sidor med rekommendationer ersätts Recommendations-designen på sidan med ett mboxTrace-informationsfönster, som visar detaljerad information om dina rekommendationer, inklusive:

* Recommendations returnerade jämfört med begärda rekommendationer
* Nyckeln som används och om den genererar rekommendationer
* Villkorsgenererade rekommendationer jämfört med rekommendationer för säkerhetskopiering
* Villkorskonfiguration
* Undantag och inkluderingar som tillämpas
* Samlingsregler

Du behöver inte inkludera `=console`, `=json`, eller `=window` i frågeparametern. Lägg till `=disable` och tryck **[!UICONTROL Enter]** för att återgå till normalt visningsläge.

Webbplatsens normala funktion och utseende påverkas inte av mboxTrace. Besökarna ser din vanliga Recommendations-design.

## mboxDebug {#mboxdebug}

Om du vill använda mboxDebug lägger du till en mboxDebug-parameter i slutet av URL:en. Följande tabell innehåller information om [!DNL Target] Svarsrelaterade URL-parametrar.

>[!NOTE]
>
>Vissa mboxDebug-parametrar är tillgängliga med eller utan autentisering.

| URL-parametrar | Syfte |
|--- |--- |
| `mboxDebug=1` | Felsökning<br>Om du lägger till den här parametern till en URL med definierade Target-begäranden öppnas ett popup-fönster med värdefull felsökningsinformation. Cookie-information, PCid- och sessions-ID-värden skrivs ut och alla URL:er visas. Klicka på en URL för en målbegäran för att visa svaret för den [!DNL Target] begäran. Mer information finns i [mbox_debug.pdf](/help/assets/mbox_debug.pdf). |
| `mboxDebug=x-cookie` | Ändra cookien |
| `mboxDisable=1` | Inaktivera kryssrutor på sidan |
| `mboxDebug=x-profile` | Visa profiler. |
| `mboxDebug=x-time` | Visa svarstid för varje [!DNL Target] förfrågan |
| `mboxOverride.browserIp=<Insert IP address>` | Testa geolokalisering<br>Testa målanpassning med den här URL-parametern. Ange en IP-adress som värde för det här attributet, och Test&amp;Target-målet utvärderar den IP-adressen så att den matchar alla geografiska mål och segmenteringar som angetts i en kampanj. |

>[!NOTE]
>
>Kontrollera att URL-fragmentet är efter frågesträngsparametrar. Allt efter det första `#` är en fragmentidentifierare och orsakar att felsökningsparametrar inte fungerar som de ska.

## Adobe Experience Cloud Debugger {#section_A2798ED3A431409690A4BE08A1BFCF17}

Med Adobe Experience Cloud Debugger är det snabbt och enkelt att förstå hur Target-implementeringen fungerar. Du kan snabbt visa bibliotekskonfigurationen, granska förfrågningar för att se till att dina anpassade parametrar skickas korrekt, aktivera konsolloggning och inaktivera alla Target-förfrågningar. Logga in på Experience Cloud och använd det kraftfulla MboxTrace-verktyget för att granska din aktivitet och dina målgruppskvalifikationer liksom din besökarprofil.

Mer information finns i utbildningsvideorna nedan:

Mer detaljerad information finns i [Felsöka at.js med Adobe Experience Cloud Debugger](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md).

## De största säljarna visas inte i Recommendations {#section_3920C857270A406C80BE6CBAC8221ECD}

The *`SiteCatalyst: purchase`* anropet kan inte användas för trafikdata för inköpsalgoritmen. Använd *`orderConfirmPage`* ring istället.

## Kontrollera aktivitetsprioritet {#section_3D0DD07240F0465BAF655D0804100AED}

Blankettbaserade aktiviteter skapade med [!DNL Target Standard/Premium] kan kollidera med aktiviteter som skapats i [!DNL Target Classic] Gränssnitt som har samma prioritet och använder samma [!DNL Target] begäran.

## Anpassad kod ger inte det förväntade resultatet i Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target har inte längre stöd för IE 8.

## Målcookie har inte angetts {#section_77AFEB541C0B495EB67E29A4475DF960}

Om din webbplats har en underdomän, som [!DNL us.domain.com], men du måste ha Target-cookien inställd på [!DNL domain.com] (i stället för [!DNL us.domain.com]) måste du åsidosätta `cookieDomain` inställning. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Målinnehållet flimrar eller visas inte om ett element också ingår i Adobe Experience Manager personalisering. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Om ett DOM-element är en del av Adobe Experience Manager (AEM) personalisering, och en Target-aktivitet, kan målinnehållet flimra eller inte visas.

För att åtgärda detta kan du inaktivera AEM på sidor där Target körs.

## Omdirigerings- och fjärrerbjudanden levereras inte på grund av en ogiltig URL. {#section_7D09043B687F43B39DAEDF17D00375AC}

Om omdirigerings- eller fjärrerbjudandet använder en ogiltig URL kanske det inte kan levereras.

För omdirigeringserbjudanden [!DNL Target] svar kan innehålla `/* invalid redirect offer URL */`

eller

För fjärrerbjudanden finns [!DNL Target] svar kan innehålla `/* invalid remote offer URL */`

Du kan kontrollera [!DNL Target] svar i webbläsaren eller med mboxTrace. Se [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) om du vill ha mer information om giltiga URL:er.

## [!DNL Target] förfrågningar utlöses inte på min webbplats.

at.js utlöser inte Target-begäranden om du använder en ogiltig doctype. at.js kräver dokumenttypen HTML 5.

## Se till att [!DNL Target] aktiviteter hanterar URL:er med frågesträngsparametrar korrekt. {#query-strings}

The [!UICONTROL Activity URL] bestämmer vilken sida som kvalificerar besökarna för aktiviteten och återger aktivitetsupplevelsen till användarna. När en uppmaning visas när en aktivitet skapas säkerställer inte alltid att innehållet levereras på den webbplatssidan, särskilt inte med URL:er som innehåller frågesträngsparametrar.

Som standard är [!UICONTROL Visual Experience Composer] (VEC) öppnar sidan som anges i [Inställningar för Visual Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md). Du kan också ange en annan sida när du skapar en aktivitet.

Om du vill visa en annan sida efter att VEC har öppnats klickar du på **[!UICONTROL Configure gear icon]** > markera **[!UICONTROL Page Delivery]** > anger du önskad URL i dialogrutan [!UICONTROL Activity URL] fält.

![Konfigurera gränssnitt för inställningar för sidleverans](assets/configure-page-delivery.png)

Men tänk om URL:en innehåller frågesträngsparametrar? Fungerar det och visar det personaliserade innehållet? I det här scenariot kan du, oavsett vilken målgrupp du har, inkludera mallregler förutom bas-URL:en för att definiera frågeparametrarna.

Följande alternativ kan användas för att inkludera ytterligare mallregler:

### Alternativ 1: Replikera URL-adressen och behåll den i mallregeln med alternativet &quot;contains&quot;.

Det här alternativet ser till att den här URL:en kvalificerar sig för aktiviteten, men tänk på att det finns hörnfall kopplade till den som kan påverka rapportdata med ytterligare poster till URL:er som innehåller bas-URL:en.

I det här scenariot är URL:en `https://shopping.mycart.com?type=Summers%20Offers` och ytterligare mallregler&quot;innehåller&quot; samma URL, avgränsade med operatorn OR:

![Replikera URL i mallregler](assets/option1.png)

### Alternativ 2: Begränsa URL-villkoret &quot;contains&quot; med endast frågesträngen.

I det här alternativet används det hörnfall som beskrivs i det föregående alternativet, men här begränsas villkorsinställningarna till enbart frågesträngen.

I det här scenariot är URL:en `https://shopping.mycart.com?type=Summers%20Offers` och ytterligare mallregler&quot;innehåller&quot; endast frågesträngen, avgränsade med operatorn OR:

![Mallregeln innehåller bara frågesträngen](assets/option2.png)

### Alternativ 3: Använd en specifik del av webbadressen i stället för att ange den fullständiga webbadressen som mål.

I det här scenariot är URL:en `https://shopping.mycart.com?type=Summers%20Offers` och ytterligare mallregler anger [!UICONTROL Query] med [!UICONTROL type] > [!UICONTROL is (case sensitive)] > type=Summers%20Erbjudanden, avgränsade med operatorn OR:

![Mallregel som utnyttjar en viss del av URL:en](assets/option3.png)

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Lägg till tillägget ![Självstudiemärke](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Grundläggande Adobe Target-felsökning ![Självstudiemärke](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace ![Självstudiemärke](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)
