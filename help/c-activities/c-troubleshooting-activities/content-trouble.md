---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: Om sidan inte visar det förväntade innehållet kan du utföra några steg för att felsöka innehållsleverans i Adobe Target.
title: Felsöka innehållsleverans i Adobe Target
subtopic: Multivariate Test
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Felsöka innehållsleverans{#troubleshoot-content-delivery}

Om sidan inte visar det förväntade innehållet kan du utföra några steg för att felsöka innehållsleveransen.

* Kontrollera aktiviteten eller kampanjkoden noggrant. Ett skrivfel eller ett annat fel kan göra att det förväntade innehållet inte visas.
* Använd mboxTrace eller mboxDebug för att felsöka mbox.
* Använd Adobe Experience Cloud Debugger, ett lättanvänt verktyg som ger mycket av samma information som mboxDebug, för att felsöka mbox.

mboxDebug är särskilt användbart när du konfigurerar Target på sidan för att kontrollera att mbox utlöses och att cookien ställs in. Men den går inte in på den typ av detaljer som är användbar vid felsökning av innehållsleverans. Om aktiviteten inte visas på sidan eller om oönskat innehåll visas använder du mboxTrace för att undersöka och felsöka sidan i detalj.

## Hämta den auktoriseringstoken som ska användas med felsökningsverktyg {#section_BED130298E794D1FA229DB7C3358BA54}

Eftersom mboxTrace och mboxDebug kan visa kampanjdata och profildata för externa parter krävs en auktoriseringstoken. Auktoriseringstoken kan hämtas i [!DNL Target] användargränssnittet. Token gäller i sex timmar.

Så här hämtar du auktoriseringstoken:

1. Klicka på **[!UICONTROL Setup]** > **[!UICONTROL Implementation]**.
1. Markera **[!UICONTROL mbox.js]** eller **[!UICONTROL at.js]**.
1. Klicka på **[!UICONTROL Generate Authentication Token]**.

   ![Generera auktoriseringstoken](/help/c-activities/c-troubleshooting-activities/assets/generate-auth-token.png)

1. Lägg till den genererade variabeln som en parameter i URL-adressen för att aktivera ett av de avancerade felsökningsverktygen.

   ![Auktoriseringstoken](/help/c-activities/c-troubleshooting-activities/assets/gen-auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace gör att du kan ta emot spårningsinformation som är kopplad till svar på mbox. Spårningsinformationen återger resultatet av ett mbox-anrop (till exempel en konvertering eller ett intryck) och alla ytterligare data som kan hjälpa till att avgöra varför just det här resultatet har inträffat, till exempel en uppsättning tillgängliga grenar som urvalet gjordes bland i en kampanj. Använd den här informationen för att felsöka innehållsleverans.

Följande parametrar är tillgängliga:

| mboxTrace-alternativ | Resultat |
|--- |--- |
| `?mboxTrace=console` | Skriver ut som objekt i konsolloggen.<br>I stället för att öppna ett nytt webbläsarfönster eller skriva ut till konsolen som i mbox.js måste du granska nätverksbegäran och titta under Förhandsgranska (Chrome) eller Response (Firefox). |
| `?mboxTrace=json` | Skriver ut i konsolloggen som en literal JSON-sträng |
| `?mboxTrace=window` | Skriver ut i ett popup-fönster som en JSON-sträng |
| `?mboxTrace=disable` | Inaktiverar spårningssessionsläge |

**Exempel på mboxTrace Call**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

Utdata visar mycket detaljerad information om ditt innehåll. mboxTrace visar information om din kampanj eller aktivitet och profil. Det ger även en ögonblicksbild av profilen före körning och en ögonblicksbild av vad som ändrats efter körningen. Det visar också vilka kampanjer eller aktiviteter som utvärderats för varje plats.

En del av informationen innehåller matchade och omatchade segment- och mål-ID:n:

* **SegmentId**: ID:n för segment, antingen från det återanvändbara segmentbiblioteket eller anonyma som skapats för den aktuella kampanjen.
* **TargetId**: ID:n för mål, antingen från måluttrycksbiblioteket eller anonyma mål för alla segment från kampanjen.
* **Omatchad**: Begäran var inte berättigad i denna inbjudan för dessa segment eller mål.
* **Matchad**: Begäran kvalificerad för de angivna segmenten eller målen.

**Använda mboxTrace på rekommendationssidor**: Om du lägger till mboxTrace som en frågeparameter på sidor med rekommendationer ersätts designen Recommendations på sidan med ett mboxTrace-informationsfönster, som visar detaljerad information om dina rekommendationer, inklusive:

* Rekommendationer som returnerats jämfört med rekommendationer som begärts
* Nyckeln som används och om den genererar rekommendationer
* Villkorsgenererade rekommendationer jämfört med rekommendationer för säkerhetskopiering
* Villkorskonfiguration
* Undantag och inkluderingar som tillämpas
* Samlingsregler

Du behöver inte inkludera `=console`, `=json`eller `=window` i frågeparametern. När du är klar med informationen för mboxTrace lägger du till `=disable` och trycker **[!UICONTROL Enter]** för att återgå till det normala visningsläget.

Webbplatsens normala funktion och utseende påverkas inte av mboxTrace. Besökarna kommer att se din vanliga rekommendationsdesign.

## mboxDebug {#mboxdebug}

Om du vill använda mboxDebug lägger du till en mboxDebug-parameter i slutet av URL:en. Följande tabell innehåller information om mbox-relaterade URL-parametrar.

>[!NOTE]
>
>Vissa mboxDebug-parametrar är tillgängliga med eller utan autentisering.

| URL-parametrar | Syfte |
|--- |--- |
| `mboxDebug=1` | FelsökningOm du lägger till den här parametern till en URL med definierade kryssrutor öppnas ett popup-fönster med värdefull felsökningsinformation.<br> Cookie-information, PCid- och sessions-ID-värden skrivs ut och alla mbox-URL:er visas. Klicka på en mbox-URL för att visa svaret för den mbox. Mer information finns i [mbox_debug.pdf](/help/assets/mbox_debug.pdf). |
| `mboxDebug=x-cookie` | Ändra cookien |
| `mboxDisable=1` | Inaktivera kryssrutor på sidan |
| `mboxDebug=x-profile` | Visa profiler. |
| `mboxDebug=x-time` | Visa svarstid för varje mbox-begäran |
| `mboxOverride.browserIp=<Insert IP address>` | Testa<br>geotargetingTesta geolokalisering med den här URL-parametern. Ange en IP-adress som värde för det här attributet, och Test&amp;Target-målet utvärderar den IP-adressen så att den matchar alla geografiska mål och segmenteringar som angetts i en kampanj. |

>[!NOTE]
>
>Kontrollera att URL-fragmentet är efter frågesträngsparametrar. Allt efter det första `#` är en fragmentidentifierare och får felsökningsparametrarna att inte fungera korrekt.

## Adobe Experience Cloud Debugger {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger gör det snabbt och enkelt att förstå er målinriktning. Du kan snabbt visa bibliotekskonfigurationen, granska förfrågningar för att se till att dina anpassade parametrar skickas korrekt, aktivera konsolloggning och inaktivera alla Target-förfrågningar. Logga in i Experience Cloud så kan ni använda det kraftfulla spårningsverktyget för Mbox för att inspektera er aktivitet och målgruppskvalifikationer samt er besökarprofil.

Mer information finns i utbildningsvideorna nedan:

Mer detaljerad information finns i [Felsöka at.js med Adobe Experience Cloud-felsökaren](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md).

## Om target.js inte kan läsas in under leverans {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

Mbox.js skickar en cookie med namnet&quot;em-disabled&quot; till besökaren om target.js inte kan läsas in under leveransen. Denna cookie förhindrar att erbjudanden som skapats med Visual Experience Composer återges på webbplatsen. Besökare med denna cookie ser varken testinnehållet eller räknas in i aktivitetsrapporterna. Allt annat innehåll (från kampanjer i till exempel Target Classic) fortsätter att läsas in. Cookien har en livstid på 30 min från tidpunkten då inläsningen misslyckades.

## De viktigaste säljarna visas inte i Rekommendationer {#section_3920C857270A406C80BE6CBAC8221ECD}

Det går inte att använda *`SIteCatalyst: purchase`* mbox för trafikdata för inköpsalgoritmen. Använd *`orderConfirmPage`* mbox i stället.

## Kontrollera aktivitetsprioritet {#section_3D0DD07240F0465BAF655D0804100AED}

Formulärbaserade aktiviteter som skapats med [!DNL Target Standard/Premium] kan kollidera med aktiviteter som skapats i [!DNL Target Classic] användargränssnittet och som har samma prioritet och använder samma mbox.

## Anpassad kod ger inte det förväntade resultatet i Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target har inte längre stöd för IE 8.

## JavaScript-innehåll som levereras av den globala mbox läses inte in när mbox.js används. {#section_03EC9B9C410B4F52A7FCD81840311709}

Uppgradera till [!DNL mbox.js] version 58 eller senare.

Mbox.js version 58 och senare verkställer icke-JavaScript-innehåll för den globala mbox direkt efter att HTML- `BODY` -taggen finns. JavaScript-innehåll inuti `<script>` -taggar för den globala mbox körs efter att `DOMContentLoaded` händelsen har utlösts. Den här ordningen för innehållsleverans säkerställer att JavaScript-innehåll för den globala mbox levereras och återges korrekt.

## Målcookie hämtar inte uppsättning {#section_77AFEB541C0B495EB67E29A4475DF960}

Om platsen har en underdomän, till exempel [!DNL us.domain.com]men du behöver ha Target-cookien inställd [!DNL domain.com] (i stället för [!DNL us.domain.com]), måste du åsidosätta `cookieDomain` inställningen. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Målinnehållet flimrar eller visas inte om ett element också är en del av AEM-personaliseringen. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Om ett DOM-element är en del av Adobe Experience Manager-personalisering (AEM) och en Target-aktivitet kan målinnehållet flimra eller inte visas.

Du kan åtgärda detta genom att inaktivera AEM-personalisering på sidor där Target körs.

## Omdirigerings- och fjärrerbjudanden levereras inte på grund av en ogiltig URL. {#section_7D09043B687F43B39DAEDF17D00375AC}

Om omdirigerings- eller fjärrerbjudandet använder en ogiltig URL kanske det inte kan levereras.

Mbox-svar kan innehålla `/* invalid redirect offer URL */`

eller

För fjärrerbjudanden kan mbox-svaret innehålla `/* invalid remote offer URL */`

Du kan kontrollera mbox-svaret i webbläsaren eller med mboxTrace. Mer information om giltiga URL:er finns på [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) .

## Jag har inga skott på min sajt.

at.js utlöser inte Target-rutor om du använder en ogiltig doctype. at.js kräver dokumenttypen HTML 5.

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Lägg till märket ![för självstudiekursen om tillägg](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Grundläggande ![självstudiekursetikett för målfelsökning](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace ![Tutorial badge](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)