---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;sökmotoroptimering;sökmotoroptimering;seo;edge clusters, central clusters;at.js;mbox.js;
description: Lär dig hur [!DNL Adobe Target] fungerar, inklusive information om JavaScript-bibliotek (AEP Web SDK at.js), strategier för användning av serversamtal, användning, Adobe datacenter, SEO-testning och bots.
title: Hur fungerar  [!DNL Target] ?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 85edad5c3adb3a7b01ee6d1eaf2c30c7596d5f92
workflow-type: tm+mt
source-wordcount: '2214'
ht-degree: 0%

---

# Så här fungerar [!DNL Adobe Target]

Lär dig hur [!DNL Adobe Target] fungerar, inklusive information om JavaScript-bibliotek ([!DNL Adobe Experience Platform Web SDK] och at.js). I den här artikeln beskrivs också de olika aktivitetstyper som du kan skapa, [!DNL Target] strategier för användningsinventering, [!DNL Target] Edge Network, SEO och robotidentifiering.

Några viktiga punkter:

* **JavaScript Libraries**: Läs mer om [!DNL Target] JavaScript-biblioteken: [!DNL Adobe Experience Platform Web SDK] och at.js.
* **Strategier för användning av serveranrop**: Lär dig hur [!DNL Target] räknar olika serveranrop, inklusive slutpunkter, en mbox, batchmbox, körning, förhämtning och meddelandeanrop.
* **Edge Network**: Upptäck hur [!DNL Target] interagerar med [!DNL Adobe Experience Platform Edge Network].
* **Skyddad användarupplevelse**: Lär dig hur [!DNL Adobe] säkerställer tillgänglighet och prestanda för målinfrastrukturen.
* **SEO-riktlinjer**: Följ bästa praxis för att justera [!DNL Target]-aktiviteter med SEO-riktlinjer.
* **Punkttrafik**: Lär dig hur Target hanterar robottrafik för att undvika skevningstester och personaliseringsalgoritmer.

## [!DNL Adobe Target] JavaScript-bibliotek {#libraries}

Målet kan integreras med webbplatser med [!DNL Experience Platform Web SDK] eller at.js:

* **[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}**: Med det här JavaScript-biblioteket på klientsidan kan [!DNL Adobe Experience Cloud]-kunder interagera med olika tjänster via [!DNL Experience Platform Edge Network]. [!DNL Adobe] rekommenderar att nya [!DNL Target]-kunder implementerar [!DNL Experience Platform Web SDK].
* **[at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/how-to-deployatjs){target=_blank}**: Det här implementeringsbiblioteket för [!DNL Target] förbättrar sidinläsningstiderna för webbimplementeringar och erbjuder bättre alternativ för enkelsidiga program. Uppdateras ofta med nya funktioner, [!DNL Adobe] rekommenderar att alla [ at.js-användare uppdaterar till den senaste versionen ](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

>[!NOTE]
>
>mbox.js-biblioteket är en äldre implementering för [!DNL Target] och stöds inte längre efter den 31 mars 2021. Uppgradera till [!UICONTROL Experience Platform Web SDK] (standard) eller den senaste versionen av at.js.

Referera [!UICONTROL Experience Platform Web SDK] eller at.js på alla sidor på webbplatsen. Lägg till exempel till ett av dessa bibliotek i det globala sidhuvudet. Du kan också använda [taggar i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/tags/home){target=_blank} för att implementera [!DNL Target].

Följande resurser innehåller detaljerad information som kan hjälpa dig att implementera [!DNL Experience Platform Web SDK] eller at.js:

* [[!DNL Adobe Experience Platform Web SDK] tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html){target=_blank}
* [Implementera [!DNL Target] med [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

Varje gång en besökare begär en sida som är optimerad för [!DNL Target] skickas en realtidsbegäran till målsystemet för att fastställa vilket innehåll som ska användas. Denna begäran görs och utförs varje gång en sida läses in, styrs av marknadsförarstyrda aktiviteter och upplevelser. Innehållet riktar sig till enskilda webbplatsbesökare, vilket maximerar svarsfrekvenserna, förvärvsfrekvensen och intäkterna. Personaliserat innehåll säkerställer att besökarna svarar, interagerar eller gör inköp.

I [!DNL Target] är varje element på sidan en del av en upplevelse, som kan innehålla flera element.

Vilket innehåll som visas beror på vilken typ av aktivitet du skapar:

### [!UICONTROL A/B Test]

I ett grundläggande A/B-test väljs innehåll slumpmässigt från de tilldelade upplevelserna. Du kan ange procentvärden för trafikallokering för varje upplevelse. Inledningsvis kan trafiken fördelas ojämnt på grund av slumpmässig uppdelning, men den utjämnas i takt med att trafiken ökar. För två upplevelser väljs till exempel startupplevelsen slumpmässigt. Låg trafik kan skeva besökarprocenten mot en upplevelse, men den här situationen balanserar ut mot mer trafik.

Ange procentmål för varje upplevelse. Ett slumpmässigt tal genereras för att välja vilken upplevelse som ska visas. Även om de resulterande procentsatserna kanske inte matchar målen exakt, leder högre trafik till en närmare delning av målmålen.

1. En kund begär en sida från servern som visas i webbläsaren.
1. En cookie från första part är inställd i kundens webbläsare för att lagra beteendet.
1. Sidan anropar målsystemet.
1. Innehållet visas baserat på aktivitetsreglerna.

Mer information finns i [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] identifierar den vinnande upplevelsen bland två eller fler alternativ. Sedan omfördelas automatiskt mer trafik till vinnaren och antalet konverteringar ökar allt eftersom testet fortsätter att köras och lära sig mer.

Mer information finns i [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

### [!UICONTROL Auto-Target] (AT)

[!UICONTROL Auto-Target] använder avancerad maskininlärning för att välja bland flera högpresterande, marknadsföringsdefinierade upplevelser. [!UICONTROL Auto-Target] levererar den mest anpassade upplevelsen till varje besökare baserat på enskilda kundprofiler och beteendet hos tidigare besökare med liknande profiler. Använd [!UICONTROL Auto-Target] för att anpassa innehåll och driva konverteringar.

Mer information finns i [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP) kombinerar erbjudanden eller meddelanden och använder avancerad maskininlärning för att matcha olika variationer för varje besökare. AP personaliserar innehåll baserat på individuella kundprofiler för att lyfta.

Mer information finns i [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### [!UICONTROL Experience Targeting] (XT)

[!UICONTROL Experience Targeting] (XT) levererar innehåll till specifika målgrupper baserat på marknadsföringsdefinierade regler och kriterier. XT är värdefull när det gäller att definiera regler för specifika upplevelser eller innehåll som riktar sig till en viss målgrupp. Flera regler kan anges i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper. När besökarna visar din webbplats utvärderar XT dem för att avgöra om de uppfyller kriterierna. Om de är kvalificerade anmäler de sig till aktiviteten och ser upplevelsen som är utformad för dem. Ni kan skapa upplevelser för flera målgrupper inom en enda aktivitet.

Mer information finns i [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4).

### [!UICONTROL Multivariate Test] (MVT)

[!UICONTROL Multivariate Testing] (MVT) jämför kombinationer av erbjudanden i sidelement för att avgöra vilken kombination som fungerar bäst för en viss målgrupp. MVT hjälper till att identifiera vilket element som mest påverkar aktivitetens framgång.

Mer information finns i [Multivariate Test](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499).

### [!UICONTROL Recommendations]

[!UICONTROL Recommendations]-aktiviteter visar automatiskt produkter eller innehåll som kan intressera kunder baserat på deras tidigare aktivitet eller andra algoritmer. Rekommendationer hjälper kunderna att hänvisa till relevanta objekt som de annars kanske inte hittar.

Mer information finns i [Rekommendationer](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

<!--
## How [!DNL Target] counts server-call usage {#usage}

[!DNL Target] counts only server calls that provide value to customers. The following table shows how [!DNL Target] counts endpoints, single mbox, batch mbox calls, execute, prefetch, and notification calls.

The following information helps you understand the counting strategy used for [!DNL Target] server calls, as shown in the table below:

* **Count Once**: Counts once per API call.
* **Count the Number of mboxes**: Counts the number of mboxes under the array in the payload of a single API call.
* **Ignore**: Is not counted at all.
* **Count the Number of Views (Once)**: Counts the number of views under the array in the payload. In a typical implementation, a view notification has only one view under the notifications array, making this equivalent to counting once in most implementations.

|Endpoint|Fetch type|Options|Counting strategy|
|--- |--- |--- |-- |
|`rest//v1/mbox`|Single|[!UICONTROL execute]|Count once|
|`rest/v2/batchmbox`|Batch|[!UICONTROL execute]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch]|Ignore|
||Batch|[!UICONTROL notifications]|Count the number of mboxes|
|`/ubox/[raw\|image\|page]`|Single|[!UICONTROL execute]|Count once|
|`rest/v1/delivery`<p>`/rest/v1/target-upstream`|Single|[!UICONTROL execute] > [!UICONTROL pageLoad]|Count once|
||Single|[!UICONTROL prefetch] > [!UICONTROL pageLoad]|Ignore|
||Single|[!UICONTROL prefetch] > [!UICONTROL views]|Ignore|
||Batch|[!UICONTROL execute] > [!UICONTROL mboxes]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch] > [!UICONTROL mboxes]|Ignore|
||Batch|[!UICONTROL notifications] > [!UICONTROL views]|Count the number of views (once)|
||Batch|[!UICONTROL notifications] > [!UICONTROL pageLoad]|Count once|
||Batch|[!UICONTROL notifications] > type ([!UICONTROL conversions])|Count once|
||Batch|[!UICONTROL notifications] > [!UICONTROL mboxes]|Count the number of mboxes|

-->

## Edge Network {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

En Edge är en geografiskt spridd serverarkitektur som ger optimal svarstid för besökare som begär innehåll, oavsett var de befinner sig.

För att förbättra svarstiderna är [!DNL Target] Edge värd endast för aktivitetslogik, cachelagrade profiler och erbjudandeinformation.

Aktivitets- och innehållsdatabaser, [!DNL Analytics] data, API:er och marknadsföringsanvändargränssnitt finns i [!DNL Adobe] Central Clusters. Uppdateringar skickas till [!DNL Target]-kanterna, som automatiskt synkroniseras med Central Clusters för att kontinuerligt uppdatera cachelagrade aktivitetsdata. Alla :1-modelleringar lagras också på varje kant, vilket gör att komplexa begäranden kan bearbetas lokalt.

Varje Edge-kluster innehåller all information som behövs för att svara på förfrågningar om besökarinnehåll och spåra analysdata. Besöksförfrågningar dirigeras till närmaste Edge-kluster.

Mer information finns i rapporten [Adobe Target Security Overview](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

[!DNL Target] ligger hos datacenter världen över som ägs av Adobe och som hyrs av Adobe.

De centrala klusterplatserna lagrar både datainsamling och databearbetningscentra. Edge klusterplatser innehåller endast datainsamlingscentraler. Varje rapportsvit tilldelas ett specifikt databehandlingscenter.

Data om kundwebbplatsaktivitet samlas in av närmaste sju Edge-kluster. Dessa data dirigeras sedan till en i förväg bestämd central klusterdestination (Oregon, Dublin eller Singapore) för bearbetning. Data för besökarprofilen lagras i det Edge-kluster som ligger närmast besökaren. Edge klusterplatser omfattar de centrala klusterplatserna samt Virginia, Mumbai, Sydney och Tokyo.

I stället för att bearbeta alla riktade begäranden från en enda plats hanteras förfrågningar av det Edge-kluster som ligger närmast besökaren. Den här metoden minskar effekten av nätverks- och internetresor.

![Karta som visar de olika typerna av målservrar](/help/main/c-intro/assets/target-servers.png)

[!DNL Target] Centralkluster, som finns på Amazon Web Services (AWS), innehåller:

* Oregon, USA
* Dublin, Irland
* Republiken Singapore

[!DNL Target] Edge Clusters, som finns på AWS, innehåller:

* Mumbai, Indien
* Tokyo, Japan
* Virginia, USA
* Oregon, USA
* Sydney, Australien
* Dublin, Irland
* Republiken Singapore

Tjänsten [!DNL Target Recommendations] finns i ett [!DNL Adobe]-datacenter i Oregon.

>[!IMPORTANT]
>
>[!DNL Target] saknar för närvarande ett Edge-kluster i Kina, vilket begränsar besökarprestanda för [!DNL Target]-kunder i regionen. Brandväggen och frånvaron av Edge Clusters kan påverka webbplatsupplevelserna, vilket ger långsam återgivning och sidladdningstider. Dessutom kan marknadsförarna uppleva fördröjning när de använder redigeringsgränssnittet för [!DNL Target].

Du kan tillåtslista [!DNL Target] Edge Clusters om du vill. Mer information finns i [tillåtslista målkantnoder](https://experienceleague.adobe.com/en/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}.

## Skyddad användarupplevelse {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] ser till att målinfrastrukturen är så tillförlitlig som möjligt och att dess prestanda är så tillförlitliga som möjligt. Kommunikationsstörningar mellan en besökares webbläsare och [!DNL Adobe] servrar kan dock störa innehållsleveransen.

För att skydda mot avbrott i tjänsten och anslutningsproblem ställs alla platser in på att inkludera standardinnehåll (definieras av klienten). Det här standardinnehållet visas om besökarens webbläsare inte kan ansluta till [!DNL Target].

Inga ändringar görs på sidan om besökarens webbläsare inte kan ansluta inom en angiven tidsgräns (standard: 15 sekunder). Om den här tidsgränsen nås visas standardplatsinnehåll.

[!DNL Adobe] skyddar användarupplevelsen genom att optimera och skydda prestanda.

* [!DNL Adobe] garanterar prestandatester baserat på branschstandarder, som garanteras av [!UICONTROL Adobe Service Level Agreement].
* Edge Network ger snabb leverans av data.
* [!UICONTROL Adobe] använder en metod med flera nivåer för att skydda sina program, vilket ger högsta tillgänglighet och tillförlitlighet för kunderna.
* [!DNL Target] Consulting erbjuder implementeringshjälp och fortlöpande produktsupport.

## SEO-testning (Search Engine Optimization) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] följer riktlinjerna för sökmotor för testning. [!DNL Google] uppmuntrar till användartestning och säger att A/B och [!UICONTROL Multivariate Testing] inte skadar rangordningar för organisk sökmotor om vissa riktlinjer följs.

[!DNL Adobe Target] följer riktlinjerna för sökmotor för testning.

Mer information finns i följande Google-resurser:

* [Webbplatstestning och Google Search](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentera och svepa in](https://support.google.com/analytics/answer/12979939?hl)


Riktlinjer presenterades i ett [blogginlägg från Google Webmaster Central](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Även om inlägget är från 2012 är det fortfarande [!DNL Google]s senaste programsats i ärendet, och riktlinjerna är fortfarande relevanta.

* **Ingen insvepning**: Vid insvepning visas en uppsättning innehåll för användare och en annan uppsättning för sökmotorbotar genom att du specifikt identifierar botar och matar in dem med olika innehåll.

  [!DNL Target] har konfigurerats för att behandla sökmotorobjekt på samma sätt som andra användare. Därför kan botar inkluderas i aktiviteter om de väljs slumpmässigt och&quot;se&quot; testvariationerna.

* **Använd rel=&quot;canonical&quot;**: Ibland krävs olika URL:er för variationer för ett A/B-test. I dessa fall ska alla variationer innehålla en rel=&quot;canonical&quot;-tagg som refererar till den ursprungliga (kontroll) URL:en. Om [!DNL Adobe] till exempel testar sin hemsida med olika URL:er för varje variation, ska följande kanoniska tagg för hemsidan placeras i taggen `<head>` för varje variation:

  `<link rel="canonical" href="https://www.adobe.com" />`

* **Använd 302 (tillfälliga) omdirigeringar**: När separata URL:er används för variantsidor i ett test rekommenderar [!DNL Google] att du använder en 302-omdirigering för att dirigera trafik till testvarianterna. Omdirigeringen till 302 informerar sökmotorer om att omdirigeringen är tillfällig och aktiv endast medan testet körs.

  En 302-omdirigering är en omdirigering på serversidan, medan [!DNL Target] och de flesta optimeringsleverantörer använder funktioner på klientsidan. Därför är [!DNL Target] inte helt kompatibel med [!DNL Google]s rekommendationer för omdirigeringar. Detta påverkar dock endast en liten del av testerna. Standardmetoden för att köra tester via [!DNL Target] innebär att ändra innehåll inom en enda URL, vilket eliminerar behovet av omdirigeringar. I de fall där flera URL:er krävs för testvariationer använder [!DNL Target] JavaScript `window.location`-kommandot, som inte anger om omdirigeringen är 301 eller 302.

  [!DNL Adobe] söker aktivt efter lösningar som är helt förenliga med riktlinjerna för sökmotorer. För klienter som behöver separata URL:er för testning anser [!DNL Adobe] att korrekt implementering av kanoniska taggar minskar de associerade riskerna.

* **Kör försök bara så länge som krävs**: [!DNL Adobe] definierar &quot;så länge som krävs&quot; som den tid som krävs för att uppnå statistisk signifikans. [!DNL Target] erbjuder bästa praxis och [!DNL Adobe Target] [Beräkna provstorlek](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) för att avgöra när testet har nått den här punkten. [!DNL Adobe] rekommenderar att du införlivar den hårdkodade implementeringen av vinnande tester i ditt testarbetsflöde och tilldelar lämpliga resurser.

  Vi rekommenderar inte att [!DNL Target] används för att&quot;publicera&quot; vinnande tester som en permanent lösning. Om det vinnande testet publiceras för 100 % av användarna hela tiden kan det här tillvägagångssättet användas tillfälligt medan det vinnande testet hårdkodas.

  Tänk på vad ditt test har ändrats. Mindre uppdateringar, t.ex. knappfärger, påverkar inte den organiska rankningen. Textändringar bör dock vara hårdkodade.

  Tänk också på tillgängligheten för sidan som du testar. Om sidan inte är tillgänglig för sökmotorer och aldrig var avsedd att rangordnas i organiska sökningar, gäller inte dessa överväganden. Ett exempel är en dedikerad landningssida för en e-postkampanj.

Google uppger att om du följer dessa riktlinjer&quot;bör testerna få liten eller ingen effekt på webbplatsen i sökresultaten&quot;.

Förutom dessa riktlinjer ger Google även ytterligare en vägledning i dokumentationen till verktyget Innehållsexperiment:

* &quot;Variantsidorna ska bibehålla innehållets anda på originalsidorna. Dessa variationer bör inte ändra innebörden av eller användarens allmänna uppfattning av det ursprungliga innehållet.&quot;

Google anger som exempel att om en webbplats originalsida läses in med nyckelord som inte relaterar till de kombinationer som visas för användarna, kan vi ta bort den webbplatsen från vårt index.

[!UICONTROL Adobe] anser att det skulle vara svårt att oavsiktligt ändra innebörden av det ursprungliga innehållet i testvariationer. [!UICONTROL Adobe] rekommenderar dock att du är medveten om nyckelordsteman på en sida och underhåller dessa teman. Ändringar av sidinnehåll, särskilt när du lägger till eller tar bort relevanta nyckelord, kan leda till att URL:en rangordnas vid organisk sökning. [!DNL Adobe] rekommenderar att du samarbetar med SEO-partnern som en del av testprotokollet.

## Bots {#bots}

[!DNL Target] använder [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/)-måttet isRobot för att identifiera kända botar baserat på den användaragentsträng som skickas i begärandehuvudet.

>[!NOTE]
>
> För [!DNL Server-Side]-begäranden ges det värde som skickas i [Request&#39;s &quot;Context&quot; node](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) företräde framför User Agent-strängen för robotidentifiering.

Trafik som identifieras som robotgenererad betjänas fortfarande. Bots behandlas som vanliga användare för att säkerställa att [!DNL Target] följer SEO-riktlinjerna. Robottrafiken kan dock förvränga A/B-tester eller personaliseringsalgoritmer om de behandlas som vanliga användare. Därför behandlas känd robottrafik i din [!DNL Target]-aktivitet på ett annat sätt. Borttagning av robottrafik ger en exaktare mätning av användaraktivitet.

[!DNL Target] gör inte följande för känd robottrafik:

* Skapa eller hämta en besökarprofil
* Logga profilattribut eller kör profilskript
* Slå upp [!DNL Adobe Audience Manager] (AAM) segment (om tillämpligt)
* Använd robottrafik i modellering eller för att leverera anpassat innehåll för [!UICONTROL Recommendations], [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] eller [!UICONTROL Auto-Allocate] aktiviteter
* Logga ett aktivitetsbesök för rapportering
* Loggdata som ska skickas till plattformen [!DNL Adobe Experience Cloud]

För känd robottrafik gäller inte [!UICONTROL Analytics for Target] (A4T): [!DNL Target]

* Skicka händelser till [!DNL Analytics]

`client_side` returnerar inte för känd robottrafik när [!DNL Target]-loggning används:

* `tnta payload`
