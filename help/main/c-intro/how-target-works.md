---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;sökmotoroptimering;sökmotoroptimering;seo;edge clusters, central clusters;at.js;mbox.js;
description: Se hur Adobe [!DNL Target] verk, inklusive information om [!DNL Target] JavaScript-bibliotek (at.js och Experience Platform Web SDK), Adobe datacenter och SEO-testning.
title: Hur [!DNL Target] Arbeta?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '2555'
ht-degree: 0%

---

# How Adobe [!DNL Target] verk

Lär dig mer [!DNL Adobe Target] verk, inklusive information om [!DNL Adobe Experience Platform Web SDK] och JavaScript-bibliotek (at.js och mbox.js). I den här artikeln beskrivs även de olika aktivitetstyper som du kan skapa med [!DNL Target]. Du kan även lära dig mer om [!DNL Target] edge network, Search Engine Optimization (SEO), and how [!DNL Target] identifierar botar.

## [!DNL Target] SDK:er och JavaScript-bibliotek för plattformar {#libraries}

[!DNL Target] integreras med webbplatser med [!DNL Experience Platform Web SDK] eller JavaScript-bibliotek:

* **Adobe Experience Platform Web SDK:** The [Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} är ett nytt JavaScript-bibliotek på klientsidan. Experience Platform Web SDK ger kunder som [!DNL Adobe Experience Cloud] interagerar med de olika tjänsterna i [!DNL Experience Cloud] (inklusive [!DNL Target]){target=_blank} via [!DNL Experience Platform] Edge Network. Adobe rekommenderar alla nya [!DNL Target] kunder implementerar [!DNL Experience Platform Web SDK].
* **at.js:** at.js-biblioteket är ett implementeringsbibliotek för [!DNL Target]. at.js-biblioteket ger bättre sidladdningstider för webbimplementeringar och ger bättre implementeringsalternativ för enkelsidiga program. at.js uppdateras ofta med nya funktioner. Adobe rekommenderar att alla kunder som använder at.js uppdaterar sina implementeringar till [senaste versionen av at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.
* **mbox.js:** mbox.js-biblioteket är det äldre implementeringsbiblioteket för [!DNL Target]. Biblioteket mbox.js stöds inte längre efter den 31 mars 2021.

Referera till [!DNL Experience Platform Web SDK] eller at.js på alla sidor på webbplatsen. Du kan till exempel lägga till ett av dessa bibliotek i det globala sidhuvudet. Du kan också överväga att använda [taggar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) implementera [!DNL Target].

Följande resurser innehåller detaljerad information som kan hjälpa dig att implementera Experience Platform Web SDK eller at.js:

* [Adobe Experience Platform Web SDK-tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=en)
* [Implementera [!DNL Target] använda Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/)

Varje gång en besökare begär en sida som har optimerats för [!DNL Target]skickas en begäran till målinriktningssystemet. Begäran hjälper till att avgöra vilket innehåll som ska användas för besökaren. Den här processen utförs i realtid. Varje gång en sida läses in görs en begäran om innehållet och utförs av systemet. Innehållet styrs av reglerna för marknadsföringsstyrda aktiviteter och upplevelser och är riktat till den enskilda besökaren. Innehållet får det att varje besökare mest sannolikt svarar på, interagerar med eller till slut köper. Personaliserat innehåll hjälper till att maximera svarsfrekvenser, förvärvsfrekvens och intäkter.

I [!DNL Target], är varje element på sidan en del av en upplevelse för hela sidan. Varje upplevelse kan innehålla flera element på sidan.

Det innehåll som visas för besökarna beror på vilken typ av aktivitet du skapar:

### [!UICONTROL A/B Test]

Innehållet som visas i ett grundläggande A/B-test väljs slumpmässigt bland de upplevelser som du tilldelar aktiviteten. Du kan tilldela procentvärden för trafikallokering för varje upplevelse. Som ett resultat av denna slumpmässiga uppdelning av trafiken kan det ta en betydande del av den inledande trafiken innan procentsatserna blir ojämnade. Om du till exempel skapar två upplevelser väljs startupplevelsen slumpmässigt. Om trafiken är liten är det möjligt att andelen besökare kan skevas mot en upplevelse. När trafiken ökar utjämnas procentsatserna.

Du kan ange procentvärden för varje upplevelse. I det här fallet genereras ett slumpmässigt tal och det talet används för att välja vilken upplevelse som ska visas. De resulterande procentsatserna kanske inte matchar de angivna målen exakt, men mer trafik innebär att upplevelserna ska delas närmare målmålen.

1. En kund begär en sida från servern och den visas i webbläsaren.
1. En cookie från första part är inställd i kundens webbläsare för att lagra kundens beteende.
1. Sidan anropar målsystemet.
1. Innehåll visas baserat på reglerna för din aktivitet.

Se [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) för mer information.

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] identifierar en vinnare bland två eller flera upplevelser. [!UICONTROL Auto-Allocate] allokerar automatiskt om mer trafik till den vinnande upplevelsen, vilket bidrar till att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.

Se [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) för mer information.

### [!UICONTROL Auto-Target] (AT)

Auto-Target använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser. Auto-Target är den mest skräddarsydda upplevelsen för varje besökare. Leveransen av upplevelsen baseras på enskilda kundprofiler och beteendet hos tidigare besökare med liknande profiler. Använd Automatiskt mål för att anpassa innehåll och driva konverteringar.

Se [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) för mer information.

### [!UICONTROL Automated Personalization] (AP)

Automated Personalization (AP) kombinerar erbjudanden och meddelanden och använder avancerad maskininlärning för att matcha olika erbjudandevarianter för varje besökare. Leveransen av upplevelser bygger på individuella kundprofiler för att personalisera innehåll och driva på lyft.

Se [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) för mer information.

### [!UICONTROL Experience Targeting] (XT)

Experience Targeting (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.

Experience Targeting, inklusive geolokalisering, är värdefullt för att definiera regler som riktar en viss upplevelse eller innehåll till en viss målgrupp. Flera regler kan definieras i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper. När besökarna visar webbplatsen utvärderar Experience Targeting (XT) dem för att avgöra om de uppfyller de kriterier som du anger. Om de uppfyller kriterierna anger de aktiviteten och den upplevelse som är utformad för att kvalificera målgrupper visas. Ni kan skapa upplevelser för flera målgrupper inom en enda aktivitet.

Se [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) för mer information.

### [!UICONTROL Multivariate Test] (MVT)

Multivariate Testing (MVT) jämför kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp. MVT hjälper till att identifiera vilket element som mest påverkar aktivitetens framgång.

Se [Multivariata tester](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) för mer information.

### [!UICONTROL Recommendations]

Recommendations-aktiviteter visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter eller andra algoritmer. Recommendations hjälper kunderna att hänvisa till relevanta saker som de annars kanske inte känner till.

Se [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) för mer information.

## Edge Network {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

En&quot;Edge&quot; är en geografiskt fördelad serverarkitektur som ger optimal svarstid för besökare som behöver innehåll, oavsett var i världen de befinner sig.

För att förbättra svarstiderna [!DNL Target] Kanterna har bara aktivitetslogik, cachelagrade profiler och erbjudandeinformation som värd.

Aktivitets- och innehållsdatabaser, [!DNL Analytics] data, API:er och marknadsföringsanvändargränssnitt finns i Adobe’s Central Clusters. Uppdateringar skickas sedan till [!DNL Target] Kanter. Central Clusters och Edge Clusters synkroniseras automatiskt för att kontinuerligt uppdatera cachade aktivitetsdata. Alla 1:1-modelleringar lagras också på varje kant, så dessa mer komplexa begäranden kan också bearbetas på kanten.

Varje Edge Cluster har all information som krävs för att besvara besökarens innehållsförfrågan och spåra analysdata på begäran. Besöksförfrågningar dirigeras till närmaste Edge-kluster.

Mer information finns i [Adobe Target - säkerhetsöversikt](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf) rapport.

The [!DNL Target] lösningen finns på datacenter som ägs av Adobe och som hyrs ut av Adobe över hela världen.

Platserna för centrala kluster innehåller både en datainsamlingscentral och en datacentral. Edge Cluster-platser innehåller bara ett datainsamlingscenter. Varje rapportsvit tilldelas ett specifikt databehandlingscenter.

Data om kundwebbplatsaktivitet samlas in av de närmaste sju Edge-kluster. Dessa data dirigeras till en kunds förbestämda mål för centrala kluster (en av tre platser: Oregon, Dublin, Singapore) för beredning. Data för besökarprofilen lagras på det Edge-kluster som ligger närmast besökaren. Bland Edge-klusterplatserna finns Central Cluster-platserna och Virginia, Mumbai, Sydney och Tokyo.

I stället för att svara på alla målförfrågningar från en enda plats, behandlas förfrågningar av det Edge-kluster som ligger närmast besökaren. Denna process bidrar till att minska effekten av restiden mellan nätverk och Internet.

![Karta som visar de olika typerna av målservrar](/help/main/c-intro/assets/target-servers.png)

[!DNL Target] Centrala kluster, som finns på Amazon Web Services (AWS), innehåller:

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

The [!DNL Target Recommendations] är värd för en tjänst [!DNL Adobe] datacenter i Oregon.

>[!IMPORTANT]
>
>[!DNL Adobe Target] för närvarande inte har något Edge Cluster i Kina och besökarens prestanda är begränsad för [!DNL Target] kunder i Kina. På grund av brandväggen och bristen på Edge Clusters i landet, är webbplatsernas upplevelser [!DNL Target] kan påverkas. Upplevelserna kan ta lång tid att återge och sidinläsningen kan påverkas. Marknadsförarna kan även uppleva fördröjning när de använder [!DNL Target] redigeringsgränssnitt.

Du kan tillåtslista [!DNL Target] Edge Clusters, om du vill. Mer information finns i [tillåtelselista: Hörnkantsnoder](https://developer.adobe.com/target/before-implement/privacy/allowlist-edges/){target=_blank}.

## Skyddad användarupplevelse {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe ser till att infrastrukturen för målinriktning blir så tillförlitlig som möjligt och att den fungerar så bra som möjligt. Men om kommunikationen bryts ned mellan besökarens webbläsare och Adobe:s servrar kan det orsaka avbrott i innehållsleveransen.

För att skydda mot avbrott i tjänsten och anslutningsproblem ställs alla platser in på att inkludera standardinnehåll (definieras av klienten). Det här standardinnehållet visas om användarens webbläsare inte kan ansluta till [!DNL Target].

Inga ändringar görs på sidan om användarens webbläsare inte kan ansluta inom en angiven tidsgräns (som standard: 15 sekunder). Om den här tidsgränsen nås visas standardplatsinnehåll.

Adobe skyddar användarupplevelsen genom att optimera och skydda prestanda.

* Adobe garanterar prestandatester baserade på branschstandarder som garanteras av Adobe Service Level Agreement.
* Edge Network ger snabb leverans av data.
* Adobe har en strategi där flera nivåer används för att säkra sina tillämpningar, vilket ger högsta möjliga tillgänglighet och tillförlitlighet för kunderna.
* [!DNL Target] Konsulttjänster ger implementeringshjälp och fortlöpande produktsupport.

## SEO-testning (Search Engine Optimization) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] anpassar sig till riktlinjer för sökmotorer vid testning.

Google uppmuntrar användare att testa. Google anger i sin dokumentation att A/B och Multivariate Testing inte skadar rangordningar för organiska sökmotorer om du följer vissa riktlinjer.

Mer information finns i följande Google-resurser:

* [Webbplatstestning och Google Search](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentera och insvepning](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

Riktlinjer presenterades i en [Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html) publicera. Även om posten är från 2012 är den fortfarande Google senaste uttalande om ärendet och riktlinjerna är fortfarande relevanta.

* **Ingen insvepning**: Insvepning visar en uppsättning innehåll för användarna och en annan uppsättning innehåll för sökmotorrobotar. Insvepning åstadkoms genom att man specifikt identifierar botar och målmedvetet matar in olika innehåll.

   [!DNL Target], som en plattform, har konfigurerats för att behandla sökmotorobjekt på samma sätt som andra användare. Detta innebär att botar kan inkluderas i aktiviteter om de väljs slumpmässigt och&quot;se&quot; testvariationerna.

* **Använd rel=&quot;canonical&quot;**: Ibland måste ett A/B-test konfigureras med olika URL:er för variationerna. I dessa fall bör alla variationer innehålla en `rel="canonical"` -tagg som refererar till den ursprungliga (kontroll) URL-adressen. Anta till exempel att Adobe testar sin hemsida med olika URL:er för varje variant. Följande kanoniska tagg för hemsidan finns i `<head>` tagg för varje variant:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Använd 302 (tillfälliga) omdirigeringar**: I de fall där separata URL:er används för variationssidorna i ett test rekommenderar Google att man använder en 302-omdirigering för att dirigera trafik till testvariationerna. Omdirigeringen 302 meddelar sökmotorerna att omdirigeringen är tillfällig och endast är aktiv så länge som testet körs.

   En 302-omdirigering är en omdirigering på serversidan, och [!DNL Target], tillsammans med de flesta optimeringsleverantörer, använder funktioner på klientsidan. Därför är omdirigering ett område där [!DNL Target] följer inte Google rekommendationer fullt ut. Detta tillvägagångssätt påverkar dock endast en liten del av testerna. Standardmetoden för att köra tester genom [!DNL Target] anropar ändring av innehåll inom en enda URL, så ingen omdirigering behövs. Det finns tillfällen när klienter måste använda flera URL:er för att representera testvariationerna. I dessa fall [!DNL Target] använder JavaScript `window.location` -kommando. Det här kommandot instruerar användare att testa variationer, vilket inte uttryckligen anger om omdirigeringen är 301 eller 302.

   Adobe fortsätter att leta efter användbara lösningar som helt överensstämmer med riktlinjerna för sökmotorer. För de kunder som måste använda separata URL:er för testning är Adobe säker på att en korrekt implementering av de kanoniska taggarna minskar riskerna med den här metoden.

* **Kör bara experimenten så länge det behövs**: Adobe anser att &quot;så länge det behövs&quot; är så lång som det behövs för att uppnå statistisk signifikans. [!DNL Target] [ger bästa praxis](https://experienceleague.adobe.com/tools/calculator/testcalculator.html) för att avgöra när testet har nått denna punkt. Adobe rekommenderar att du inkluderar den hårdkodade implementeringen av vinnande tester i ditt testarbetsflöde och tilldelar lämpliga resurser.

   Använda [!DNL Target] att&quot;publicera&quot; vinnande tester rekommenderas inte som en permanent lösning. Om det vinnande testet publiceras för 100 % av användarna 100 % av tiden kan det här tillvägagångssättet användas medan processen med att hårdkoda det vinnande testet slutförs.

   Det är också viktigt att tänka på vad ditt test har ändrats. Om du bara uppdaterar färgen på knappar eller andra mindre objekt som inte är textbaserade på sidan påverkas inte den organiska rankningen. Ändringar av text bör dock vara hårdkodade.

   Det är också viktigt att tänka på tillgängligheten för sidan som du testar. Om sidan inte är tillgänglig för sökmotorer och inte har utformats för att rangordnas i organiska sökningar, gäller inget av ovanstående. Ett exempel är en dedikerad landningssida för en e-postkampanj.

Google uppger att om du följer dessa riktlinjer&quot;bör testerna få liten eller ingen effekt på webbplatsen i sökresultaten&quot;.

Förutom dessa riktlinjer ger Google även ytterligare en vägledning i dokumentationen till verktyget Innehållsexperiment:

* &quot;Variantsidorna ska bibehålla innehållets anda på originalsidorna. Dessa variationer bör inte ändra innebörden av eller användarens allmänna uppfattning av det ursprungliga innehållet.&quot;

Google anger som exempel att om en webbplats originalsida läses in med nyckelord som inte relaterar till de kombinationer som visas för användarna, kan vi ta bort den webbplatsen från vårt index.

Adobe anser att det skulle vara svårt att oavsiktligt ändra innebörden av det ursprungliga innehållet i testvariationerna. Adobe rekommenderar dock att du är medveten om nyckelordsteman på en sida och underhåller dessa teman. Ändringar av sidinnehåll, särskilt när du lägger till eller tar bort relevanta nyckelord, kan leda till att URL:en rangordnas vid organisk sökning. Adobe rekommenderar att du samarbetar med din SEO-partner som en del av testprotokollet.

## Bots {#bots}

Adobe [!DNL Target] använder [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) metrisk &quot;isRobot&quot; för att identifiera kända bots baserat på användaragentsträngen som skickades i begärandehuvudet.

>[!NOTE]
>
> För [!DNL Server-Side] begäran, det värde som skickas i [Begärans kontextnod](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) har företräde framför användaragentsträngen för robotidentifiering.

Trafik som identifieras som genererad av en robot betjänas fortfarande av innehåll. Boxar behandlas som vanliga användare för att säkerställa att [!DNL Target] är i linje med SEO:s riktlinjer. Om du använder robottrafik kan du skeva A/B-tester eller personaliseringsalgoritmer om de behandlas som vanliga användare. Om en känd robot upptäcks i [!DNL Target] trafiken behandlas något annorlunda. Att ta bort robottrafik ger en mer exakt mätning av användaraktivitet.

Särskilt för känd robottrafik [!DNL Target] inte:

* Skapa eller hämta en besökarprofil
* Logga alla profilattribut eller kör profilskript
* Slå upp Adobe Audience Manager-segment (AAM) (om tillämpligt)
* Använd robottrafik för att modellera och leverera personaliserat innehåll för Recommendations, Auto-Target, Automated Personalization eller [!UICONTROL Auto-Allocate] verksamhet
* Logga ett aktivitetsbesök för rapportering
* Loggdata som ska skickas till [!DNL Adobe Experience Cloud] plattform
