---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;sökmotoroptimering;seo;edge clusters, central clusters;at.js;mbox.js;
description: Läs om hur Adobe Target fungerar, inklusive information om Target JavaScript-bibliotek (at.js och AEP Web SDK), Adobe datacenter och SEO-testning.
title: Hur fungerar Target?
feature: Översikt
translation-type: tm+mt
source-git-commit: 8853551d2266836f4fe662c0882ba2af669d5a62
workflow-type: tm+mt
source-wordcount: '2592'
ht-degree: 0%

---


# Så här fungerar Adobe Target

Lär dig hur [!DNL Adobe Target] fungerar, inklusive information om [!DNL Adobe Experience Platform Web SDK]- och JavaScript-biblioteken (at.js och mbox.js). I den här artikeln beskrivs även de olika aktivitetstyper som du kan skapa med Target. Du kan också lära dig mer om gränsnätverket, sökmotoroptimering (SEO) och hur Target identifierar botar.

## SDK:er för målplattformen och JavaScript-bibliotek {#libraries}

[!DNL Adobe Target] integreras med webbplatser med hjälp av  [!DNL AEP Web SDK] eller JavaScript-bibliotek:

* **Adobe Experience Platform Web SDK:** The  [AEP Web ](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) SDKär ett nytt JavaScript-bibliotek på klientsidan. Med AEP Web SDK kan kunder med [!DNL Adobe Experience Cloud] interagera med de olika tjänsterna i [!DNL Experience Cloud] (inklusive [!DNL Target]) via [!DNL AEP] Edge Network. Adobe rekommenderar att alla nya [!DNL Target]-kunder implementerar [!DNL AEP Web SDK].
* **at.js:** Biblioteket  [at.js ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) är ett implementeringsbibliotek för  [!DNL Target]. at.js-biblioteket ger bättre sidladdningstider för webbimplementeringar och ger bättre implementeringsalternativ för enkelsidiga program. at.js uppdateras ofta med nya funktioner. Adobe rekommenderar att alla kunder som använder at.js uppdaterar sina implementeringar till den [senaste versionen av at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).
* **mbox.js:** The  [mbox.js ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) libraryis the legacy implementation library for Target. Biblioteket mbox.js stöds fram till 31 mars 2021, men det kommer inte att finnas några funktionsuppdateringar.

>[!IMPORTANT]
>
>Alla kunder bör migrera till [!DNL AEP Web SDK] eller till den senaste versionen av at.js. Mer information finns i [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) eller [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

Referera till [!DNL AEP Web SDK] eller at.js på alla sidor på webbplatsen. Du kan till exempel lägga till ett av dessa bibliotek i det globala sidhuvudet. Du kan också överväga att använda [Adobe Platform Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html) för att implementera [!DNL Target].

Följande resurser innehåller detaljerad information som kan hjälpa dig att implementera AEP Web SDK eller at.js:

* [Adobe Experience Platform Web SDK-tillägg](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Implementera mål med Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

Varje gång en besökare begär en sida som har optimerats för [!DNL Target] skickas en begäran till målsystemet. Begäran hjälper till att avgöra vilket innehåll som ska användas för besökaren. Den här processen utförs i realtid. Varje gång en sida läses in görs en begäran om innehållet och utförs av systemet. Innehållet styrs av reglerna för marknadsföringsstyrda aktiviteter och upplevelser och är riktat till den enskilda besökaren. Innehållet får det att varje besökare mest sannolikt svarar på, interagerar med och slutligen köper. Personaliserat innehåll bidrar till att maximera svarsfrekvenser, förvärvsfrekvens och intäkter.

I [!DNL Target] är varje element på sidan en del av en upplevelse för hela sidan. Varje upplevelse kan innehålla flera element på sidan.

Det innehåll som visas för besökarna beror på vilken typ av aktivitet du skapar:

### A/B-test

Mer information finns i [Skapa ett A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

Innehållet som visas i ett grundläggande A/B-test väljs slumpmässigt bland de upplevelser som du tilldelar aktiviteten. Du kan tilldela procentvärden för trafikallokering för varje upplevelse. Som ett resultat av denna slumpmässiga uppdelning av trafiken kan det ta en betydande del av den inledande trafiken innan procentsatserna blir ojämnade. Om du till exempel skapar två upplevelser väljs startupplevelsen slumpmässigt. Om trafiken är liten är det möjligt att andelen besökare kan skevas mot en upplevelse. När trafiken ökar utjämnas procentsatserna.

Du kan ange procentvärden för varje upplevelse. I det här fallet genereras ett slumpmässigt tal och det talet används för att välja vilken upplevelse som ska visas. De resulterande procentsatserna kanske inte matchar de angivna målen exakt, men mer trafik innebär att upplevelserna ska delas närmare målmålen.

1. En kund begär en sida från servern och den visas i webbläsaren.
2. En cookie från första part ställs in i kundens webbläsare för att lagra kundens beteende.
3. Sidan anropar målsystemet.
4. Innehåll visas baserat på reglerna för din aktivitet.

### Automatisk allokering

Mer information finns i [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

Automatisk tilldelning identifierar en vinnare bland två eller flera upplevelser. Automatisk allokering omfördelar automatiskt mer trafik till den vinnande upplevelsen för att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.

### Automatiskt mål (AT)

Mer information finns i [Automatisk målkatalog](/help/c-activities/auto-target/auto-target-to-optimize.md).

Auto-Target använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser. Auto-Target är den mest skräddarsydda upplevelsen för varje besökare. Leveransen av upplevelsen baseras på enskilda kundprofiler och beteendet hos tidigare besökare med liknande profiler. Använd Automatiskt mål för att anpassa innehåll och driva konverteringar.

### Automated Personalization (AP)

Mer information finns i [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

Automated Personalization (AP) kombinerar erbjudanden och meddelanden och använder avancerad maskininlärning för att matcha olika erbjudandevarianter för varje besökare. Leveransen av upplevelser bygger på individuella kundprofiler för att personalisera innehåll och driva på lyft.

### Experience Targeting (XT)

[Experience Targeting](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)

Experience Targeting (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.

Experience Targeting, inklusive geolokalisering, är värdefullt för att definiera regler som riktar en viss upplevelse eller innehåll till en viss målgrupp. Flera regler kan definieras i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper. När besökarna visar webbplatsen utvärderar Experience Targeting (XT) dem för att avgöra om de uppfyller de kriterier som du anger. Om de uppfyller kriterierna anger de aktiviteten och den upplevelse som är utformad för att kvalificera målgrupper visas. Ni kan skapa upplevelser för flera målgrupper inom en enda aktivitet.

### Multivariata tester (MVT)

Mer information finns i [Multivariate Test](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499).

Multivariate Testing (MVT) jämför kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp. MVT hjälper till att identifiera vilket element som mest påverkar aktivitetens framgång.

### Recommendations

Mer information finns i [Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

Recommendations-aktiviteter visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter eller andra algoritmer. Recommendations hjälper kunderna att hänvisa till relevanta saker som de annars kanske inte känner till.

## Edge-nätverket {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

En&quot;Edge&quot; är en geografiskt fördelad serverarkitektur som ger optimala svarstider för slutanvändare som behöver innehåll, oavsett var de befinner sig i världen.

För att förbättra svarstiderna är Target Edges värd endast för aktivitetslogik, cachelagrade profiler och erbjudandeinformation.

Aktivitets- och innehållsdatabaser, [!DNL Analytics]-data, API:er och marknadsföringsanvändargränssnitt finns i Adobe centrala kluster. Uppdateringar skickas sedan till målkanterna. Central Clusters och Edge Clusters synkroniseras automatiskt för att kontinuerligt uppdatera cachade aktivitetsdata. Alla 1:1-modelleringar lagras också på varje kant, så dessa mer komplexa begäranden kan också bearbetas på kanten.

Varje Edge Cluster har all information som krävs för att svara på användarens begäran om innehåll och spåra analysdata på begäran. Användarförfrågningar dirigeras till närmaste Edge-kluster.

Mer information finns i [Adobe Target Security Overview](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf) white paper.

[!DNL Adobe Target]-lösningen finns på datacenter som ägs av Adobe och som hyrs av Adobe över hela världen.

Platserna för centrala kluster innehåller både en datainsamlingscentral och en datacentral. Edge Cluster-platser innehåller bara ett datainsamlingscenter. Varje rapportsvit tilldelas ett specifikt databehandlingscenter.

Data om kundwebbplatsaktivitet samlas in av de närmaste sju Edge-kluster. Dessa data dirigeras till en kunds förbestämda mål för centrala kluster (en av tre platser: Oregon, Dublin, Singapore) för beredning. Data för besökarprofilen lagras på det Edge-kluster som ligger närmast besökaren. Bland Edge-klusterplatserna finns Central Cluster-platserna och Virginia, Amsterdam, Sydney, Tokyo och Hong Kong.

I stället för att svara på alla målförfrågningar från en enda plats, behandlas förfrågningar av det Edge-kluster som ligger närmast besökaren. Den här processen bidrar till att minska effekten av restiden mellan nätverk och Internet.

![Karta över typer av målservrar](/help/c-intro/assets/target-servers.png)

Bland målgrupperna är Amazon Web Services (AWS):

* Oregon, USA
* Dublin, Irland
* Republiken Singapore

Edge-målkluster, som finns på AWS:

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
>[!DNL Adobe Target] för närvarande inte har något Edge Cluster i Kina och slutanvändarnas prestanda är fortfarande begränsade för  [!DNL Target] kunder i Kina. På grund av brandväggen och bristen på Edge Clusters i landet kan upplevelserna på webbplatser med [!DNL Target] som distribuerats påverkas. Upplevelserna kan ta lång tid att återge och sidinläsningen kan påverkas. Marknadsförarna kan även uppleva fördröjning när de använder [!DNL Target]-redigeringsgränssnittet.

Om du vill kan du tillåtslista Kluster för målkant. Mer information finns i [tillåtslista målkantnoder](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Skyddad användarupplevelse {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe ser till att infrastrukturen för målinriktning blir så tillförlitlig som möjligt och att den fungerar så bra som möjligt. Men om kommunikationen bryts ned mellan slutanvändarens webbläsare och Adobe:s servrar kan det orsaka avbrott i innehållsleveransen.

För att skydda mot avbrott i tjänsten och anslutningsproblem ställs alla platser in på att inkludera standardinnehåll (definieras av klienten). Det här standardinnehållet visas om användarens webbläsare inte kan ansluta till [!DNL Target].

Inga ändringar görs på sidan om användarens webbläsare inte kan ansluta inom en angiven tidsgräns (som standard: 15 sekunder). Om den här tidsgränsen nås visas standardplatsinnehåll.

Adobe skyddar användarupplevelsen genom att optimera och skydda prestanda.

* Adobe garanterar prestandatester baserade på branschstandarder, som garanteras genom Adobe servicenivåavtalet.
* Edge Network ger snabb leverans av data.
* Adobe har en strategi där flera nivåer används för att säkra sina tillämpningar, vilket ger högsta möjliga tillgänglighet och tillförlitlighet för kunderna.
* [!DNL Target] Konsulttjänster ger implementeringshjälp och fortlöpande produktsupport.

## SEO-vänlig testning {#concept_C0C865663CAB4251B66A1F250FD25E6A} (Search Engine Optimization)

[!DNL Adobe Target] anpassar sig till riktlinjer för sökmotorer vid testning.

Google uppmuntrar till testning. Google anger i sin dokumentation att A/B och Multivariate Testing inte skadar rangordningar för organiska sökmotorer om du följer vissa riktlinjer.

Mer information finns i följande Google-resurser:

* [Webbplatstestning och Google Search](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentera och insvepning](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

Riktlinjer presenterades i ett [Google Webmaster Central-blogg](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)-inlägg. Även om inlägget är från 2012 är det fortfarande Googles senaste uttalande i frågan och riktlinjerna är fortfarande relevanta.

* **Ingen insvepning**: Insvepning visar en uppsättning innehåll för användarna och en annan uppsättning innehåll för sökmotorrobotar. Insvepning åstadkoms genom att man specifikt identifierar botar och målmedvetet matar in olika innehåll.

   Målet, som en plattform, har konfigurerats för att behandla sökmotorobjekt på samma sätt som andra användare. Detta innebär att botar kan inkluderas i aktiviteter om de väljs slumpmässigt och&quot;se&quot; testvariationerna.

* **Använd rel=&quot;canonical&quot;**: Ibland måste ett A/B-test konfigureras med olika URL:er för variationerna. I dessa fall ska alla variationer innehålla en `rel="canonical"`-tagg som refererar till den ursprungliga (kontroll) URL:en. Anta till exempel att Adobe testar sin hemsida med olika URL:er för varje variant. Följande kanoniska tagg för hemsidan finns i taggen `<head>` för var och en av varianterna:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Använd 302 (tillfälliga) omdirigeringar**: I de fall där separata URL:er används för variationssidorna i ett test rekommenderar Google att en 302-omdirigering används för att dirigera trafik till testvarianterna. Omdirigeringen 302 meddelar sökmotorerna att omdirigeringen är tillfällig och endast är aktiv så länge som testet körs.

   En 302-omdirigering är en omdirigering på serversidan och Target, tillsammans med de flesta optimeringsleverantörer, använder funktioner på klientsidan. Därför är detta ett område där Target inte helt följer Googles rekommendationer. Detta tillvägagångssätt påverkar dock endast en liten del av testerna. Standardmetoden för att köra tester via Target kräver att innehållet ändras inom en enda URL, så inga omdirigeringar behövs. Det finns tillfällen när klienter måste använda flera URL:er för att representera testvariationerna. I dessa instanser använder Target JavaScript-kommandot `window.location`. Det här kommandot instruerar användare att testa variationer, vilket inte uttryckligen anger om omdirigeringen är 301 eller 302.

   Adobe fortsätter att leta efter användbara lösningar som helt överensstämmer med riktlinjerna för sökmotorer. För de kunder som måste använda separata URL:er för testning är Adobe säker på att en korrekt implementering av de kanoniska taggarna minskar riskerna med den här metoden.

* **Kör endast experiment så länge det behövs**: Adobe anser att &quot;så länge det behövs&quot; är så lång som det behövs för att uppnå statistisk signifikans. Målet [innehåller bästa praxis](https://docs.adobe.com/content/target-microsite/testcalculator.html) för att avgöra när testet har nått den här punkten. Adobe rekommenderar att du inkluderar den hårdkodade implementeringen av vinnande tester i ditt testarbetsflöde och tilldelar lämpliga resurser.

   Att använda Target-plattformen för att&quot;publicera&quot; vinnande tester rekommenderas inte som en permanent lösning. Om det vinnande testet publiceras för 100 % av användarna 100 % av tiden kan det här tillvägagångssättet användas medan processen med att hårdkoda det vinnande testet slutförs.

   Det är också viktigt att tänka på vad ditt test har ändrats. Om du bara uppdaterar färgen på knappar eller andra mindre objekt som inte är textbaserade på sidan påverkas inte den organiska rankningen. Ändringar av text bör dock vara hårdkodade.

   Det är också viktigt att tänka på tillgängligheten för sidan som du testar. Om sidan inte är tillgänglig för sökmotorer och inte har utformats för att rangordnas i organiska sökningar, gäller inget av ovanstående. Ett exempel är en dedikerad landningssida för en e-postkampanj.

Google säger att om du följer dessa riktlinjer&quot;bör testerna få liten eller ingen effekt på din webbplats i sökresultaten&quot;.

Förutom dessa riktlinjer ger Google även ytterligare en vägledning i dokumentationen till verktyget Content Experiments:

* &quot;Variantsidorna ska bibehålla innehållets anda på originalsidorna. Dessa variationer bör inte ändra innebörden av eller användarens allmänna uppfattning av det ursprungliga innehållet.&quot;

Google visar som exempel att&quot;om en webbplats originalsida läses in med nyckelord som inte relaterar till kombinationerna som visas för användarna, kan vi ta bort den webbplatsen från vårt index.&quot;

Adobe anser att det skulle vara svårt att oavsiktligt ändra innebörden av det ursprungliga innehållet i testvariationerna. Adobe rekommenderar dock att du är medveten om nyckelordsteman på en sida och underhåller dessa teman. Ändringar av sidinnehåll, särskilt när du lägger till eller tar bort relevanta nyckelord, kan leda till att URL:en rangordnas vid organisk sökning. Adobe rekommenderar att du samarbetar med din SEO-partner som en del av testprotokollet.

## Börjar {#bots}

Adobe Target använder måttet [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) &quot;isRobot&quot; för att identifiera kända botar baserat på användaragentsträngen som skickas i begärandehuvudet.

>[!NOTE]
>
> För [!DNL Server-Side]-begäranden ges det värde som skickas i [begärans kontextnod](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) företräde framför användaragentsträngen för identifiering av robotar.

Trafik som identifieras som genererad av en robot betjänas fortfarande av innehåll. Bots behandlas som en vanlig användare för att säkerställa att Target är i linje med riktlinjerna för SEO. Om du använder robottrafik kan du skeva A/B-tester eller personaliseringsalgoritmer om de behandlas som vanliga användare. Om en känd robot upptäcks i din Target-aktivitet behandlas trafiken därför något annorlunda. Att ta bort robottrafik ger en mer exakt mätning av användaraktivitet.

För känd robottrafik gäller följande:

* Skapa eller hämta en besökarprofil
* Logga alla profilattribut eller kör profilskript
* Slå upp Adobe Audience Manager-segment (AAM) (om tillämpligt)
* Använd robottrafik för att modellera och leverera personaliserat innehåll för aktiviteter i Recommendations, Auto Target, Automated Personalization eller Auto Allocate
* Logga ett aktivitetsbesök för rapportering
* Loggdata som ska skickas till Adobe Experience Cloud-plattformen
