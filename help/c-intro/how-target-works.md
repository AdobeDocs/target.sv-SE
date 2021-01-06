---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;seo;search engine optimization;edge clusters, central clusters;at.js;mbox.js;
description: Information om hur Adobe Target fungerar, inklusive information om Adobe Experience Platform Web SDK, Target JavaScript-biblioteken (at.js och mbox.js) och de olika aktivitetstyper som du kan skapa i Target.
title: Så här fungerar Adobe Target
feature: Overview
translation-type: tm+mt
source-git-commit: 1b426e0b2004e729ba75d218a9b6ccd5195449cd
workflow-type: tm+mt
source-wordcount: '2530'
ht-degree: 1%

---


# Så här fungerar Adobe Target

Information om hur [!DNL Adobe Target] fungerar, inklusive information om [!DNL Adobe Experience Platform Web SDK], JavaScript-biblioteken [!DNL Target] (at.js och mbox.js) och de olika aktivitetstyper som du kan skapa med Target.

## SDK:er för målplattformen och JavaScript-bibliotek {#libraries}

Adobe Target kan integreras med webbplatser via [!DNL AEP Web SDK]- eller JavaScript-biblioteken:

* **Adobe Experience Platform Web SDK:** The  [AEP Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) SDKär ett nytt JavaScript-bibliotek på klientsidan som gör det möjligt  [!DNL Adobe Experience Cloud] för kunder att interagera med de olika tjänsterna i  [!DNL Experience Cloud] (inklusive  [!DNL Target]) via  [!DNL Adobe Experience Platform] Edge Network. Se [Målöversikt](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) för [!DNL Target]-specifik information.
* **at.js:** The  [at.js ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) library är det nya implementeringsbiblioteket för Target. at.js-biblioteket ger bättre sidladdningstider för webbimplementeringar och ger bättre implementeringsalternativ för enkelsidiga program. at.js är det rekommenderade implementeringsbiblioteket och uppdateras ofta med nya funktioner. Vi rekommenderar att alla kunder implementerar eller migrerar till den [senaste versionen av at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).
* **mbox.js:** The  [mbox.js ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) libraryis the legacy implementation library for Target. Biblioteket mbox.js stöds fram till 31 mars 2021, men det kommer inte att finnas några funktionsuppdateringar.

>[!IMPORTANT]
>
>Alla kunder bör migrera till [!DNL AEP Web SDK] eller till den senaste versionen av at.js. Mer information finns i [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) eller [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

Du måste referera till [!DNL AEP Web SDK] eller at.js på alla sidor på webbplatsen. Du kan till exempel lägga till en av dessa i det globala sidhuvudet. Du kan också överväga att använda [Adobe Platform Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html).

Följande resurser hjälper dig att implementera AEP Web SDK eller at.js:

* [Adobe Experience Platform Web SDK-tillägg](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Implementera mål med Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

Varje gång en besökare begär en sida som har optimerats för [!DNL Target] skickas en begäran till målsystemet för att avgöra vilket innehåll som ska användas för en besökare. Den här processen sker i realtid, varje gång en sida läses in, görs en begäran om innehållet och utförs av systemet. Innehållet styrs av reglerna för marknadsföringsstyrda aktiviteter och upplevelser och är riktat till den enskilda besökaren. Innehållet utnyttjas av besökarna på webbplatsen som mest sannolikt reagerar på, interagerar med och i slutändan köper för att maximera svarsfrekvensen, kundvärvningsfrekvensen och intäkterna.

I [!DNL Target] är varje element på sidan en del av en upplevelse för hela sidan. Varje upplevelse kan innehålla flera element på sidan.

Det innehåll som visas för besökarna beror på vilken typ av aktivitet du skapar:

### A/B-test

Mer information finns i [Skapa ett A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

Innehållet som visas i ett grundläggande A/B-test väljs slumpmässigt bland de resurser som du tilldelar till aktiviteten, enligt de procentsatser som du väljer för varje upplevelse. Som ett resultat av denna slumpmässiga uppdelning av trafiken kan det ta en hel del inledande trafik innan procentandelarna ens tar slut. Om du till exempel skapar två upplevelser väljs startupplevelsen slumpmässigt. Om trafiken är liten är det möjligt att andelen besökare kan skevas mot en upplevelse. När trafiken ökar bör procentsatserna bli mer lika.

Du kan ange procentvärden för varje upplevelse. I det här fallet genereras ett slumpmässigt tal och det talet används för att välja vilken upplevelse som ska visas. De resulterande procentsatserna kanske inte matchar de angivna målen exakt, men mer trafik innebär att upplevelserna ska delas närmare målmålen.

1. En kund begär en sida från servern och den visas i webbläsaren.
2. En cookie från första part ställs in i kundens webbläsare för att lagra kundens beteende.
3. Sidan anropar målsystemet.
4. Innehåll visas baserat på reglerna för din aktivitet.

### Automatisk allokering

Mer information finns i [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

Med Automatisk allokering identifieras en vinnare av två eller flera upplevelser och mer trafik omfördelas automatiskt till den vinnande upplevelsen för att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.

### Automatiskt mål (AT)

Mer information finns i [Automatisk målkatalog](/help/c-activities/auto-target/auto-target-to-optimize.md).

Auto-Target använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser och levererar den mest skräddarsydda upplevelsen till varje besökare baserat på deras individuella kundprofil och beteendet hos tidigare besökare med liknande profiler, för att personalisera innehåll och driva konverteringar.

### Automated Personalization (AP)

Mer information finns i [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

Automated Personalization (AP) kombinerar erbjudanden och meddelanden och använder avancerad maskininlärning för att matcha olika erbjudandevariationer för varje enskild besökare baserat på deras individuella kundprofil, för att anpassa innehåll och driva lyft.

### Experience Targeting (XT)

[Experience Targeting](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)

Experience Targeting (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.

Experience Targeting, inklusive geolokalisering, är värdefullt för att definiera regler som riktar en viss upplevelse eller innehåll till en viss målgrupp. Flera regler kan definieras i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper. När besökarna visar webbplatsen utvärderar Experience Targeting (XT) dem för att avgöra om de uppfyller de kriterier som du anger. Om de uppfyller kriterierna anger de aktiviteten och den upplevelse som är utformad för att kvalificera målgrupper visas. Ni kan skapa upplevelser för flera målgrupper inom en enda aktivitet.

### Multivariata tester (MVT)

Mer information finns i [Multivariate Test](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499).

Med multivariata tester (MVT) jämförs kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp och det element som har störst påverkan på aktivitetens framgång identifieras.

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

Data för kundwebbplatsaktivitet samlas in av de närmaste sju Edge-kluster och dirigeras till en kunds förbestämda mål för Central Cluster (en av tre platser: Oregon, Dublin, Singapore) för beredning. Besökarprofildata lagras på det Edge Cluster-område som ligger närmast besökaren (platserna är bland annat Central Cluster-platserna och Virginia, Amsterdam, Sydney, Tokyo och Hong Kong).

I stället för att svara på alla förfrågningar om målinriktning från en enda plats behandlas förfrågningar av det Edge-kluster som ligger närmast besökaren, vilket minskar effekten av nätverks-/Internetresetid.

![Karta över typer av målservrar](/help/c-intro/assets/target-servers.png)

Target Central Clusters, som finns på Amazon Web Services (AWS), finns i:

* Oregon, USA
* Dublin, Irland
* Republiken Singapore

Edge-målkluster, som finns på AWS, finns i:

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
>[!DNL Adobe Target] för närvarande inte har något Edge Cluster i Kina och slutanvändarnas prestanda kommer att fortsätta vara begränsade för  [!DNL Target] kunder i Kina. På grund av brandväggen och bristen på Edge Clusters i landet går det långsamt att återge webbplatser med [!DNL Target] och sidinläsningen påverkas. Marknadsförarna kan även uppleva fördröjning när de använder [!DNL Target]-redigeringsgränssnittet.

Om du vill kan du tillåtslista Kluster för målkant. Mer information finns i [tillåtslista målkantnoder](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Skyddad användarupplevelse {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe ser till att infrastrukturen för målinriktning blir så tillförlitlig som möjligt och att den fungerar så bra som möjligt. Men om kommunikationen bryts ned mellan slutanvändarens webbläsare och Adobe:s servrar kan det orsaka avbrott i innehållsleveransen.

För att skydda mot tjänstavbrott och anslutningsproblem ställs alla platser in på att inkludera standardinnehåll (som definieras av klienten), som visas om användarens webbläsare inte kan ansluta till [!DNL Target].

Inga ändringar görs på sidan om användarens webbläsare inte kan ansluta inom en angiven tidsgräns (som standard: 15 sekunder). Om den här tidsgränsen nås visas standardplatsinnehåll.

Adobe skyddar användarupplevelsen genom att optimera och skydda prestanda.

* Adobe garanterar prestandatester baserade på branschstandarder, som garanteras genom Adobe servicenivåavtalet.
* Edge Network ger snabb leverans av data.
* Adobe har en strategi där flera nivåer används för att säkra sina tillämpningar, vilket ger högsta möjliga tillgänglighet och tillförlitlighet för kunderna.
* [!DNL Target] Konsulttjänster ger implementeringshjälp och fortlöpande produktsupport.

## SEO-vänlig testning {#concept_C0C865663CAB4251B66A1F250FD25E6A} (Search Engine Optimization)

[!DNL Adobe Target] anpassar sig till riktlinjer för sökmotorer vid testning.

Google uppmuntrar till användartestning och har i sin dokumentation angett att A/B- och multivariata tester inte kommer att skada den organiska sökmotorns rankning så länge några enkla riktlinjer följs.

Mer information finns i följande Google-resurser:

* [Webbplatstestning och Google Search](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentera och insvepning](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

Riktlinjer presenterades i ett [Google Webmaster Central-blogg](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)-inlägg. Även om inlägget är från 2012 är det fortfarande Googles senaste uttalande i frågan och riktlinjerna är fortfarande relevanta.

* **Ingen insvepning**  - Insvepning visar en uppsättning innehåll för dina användare och en annan uppsättning innehåll för sökmotorbotar genom att identifiera dem specifikt och avsiktligt mata dem med olika innehåll.

   Målet, som en plattform, har konfigurerats för att behandla sökmotorobjekt på samma sätt som andra användare. Detta innebär att bottarna kan inkluderas i tester som du kör, om de väljs slumpmässigt, och att&quot;se&quot; testvariationerna.

* **Använd rel=&quot;canonical&quot;** - Ibland måste ett A/B-test ställas in med olika URL:er för variationerna. I dessa fall ska alla variationer innehålla en `rel="canonical"`-tagg som refererar till den ursprungliga (kontroll) URL:en. Om Adobe till exempel testade sin hemsida med olika URL:er för varje variant, skulle följande kanoniska tagg för hemsidan anges i `<head>`-taggen för var och en av varianterna:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Använd 302 (tillfälliga) omdirigeringar**  - I de fall där separata URL:er används för variationssidorna i ett test rekommenderar Google att du använder en 302-omdirigering för att dirigera trafik till testvarianterna. Detta anger för sökmotorerna att omdirigeringen är tillfällig och endast är aktiv så länge som testet körs.

   En 302-omdirigering är en omdirigering på serversidan och Target, tillsammans med de flesta optimeringsleverantörer, använder funktioner på klientsidan. Därför är detta ett område där Target inte helt följer Googles rekommendationer. Detta påverkar dock endast en liten del av testerna. Standardmetoden för att köra tester via Target kräver att innehållet ändras inom en enda URL, så inga omdirigeringar behövs. Det finns tillfällen när kunderna måste använda flera URL:er för att representera sina testvariationer. I de här instanserna använder Target JavaScript-kommandot `window.location` för att instruera användare att testa variationer, vilket inte uttryckligen anger om omdirigeringen är 301 eller 302.

   Även om vi fortsätter att leta efter användbara lösningar som helt överensstämmer med riktlinjerna för sökmotorer, är vi övertygade om att en korrekt implementering av de kanoniska taggarna som nämns ovan minskar riskerna med detta tillvägagångssätt för de klienter som måste använda separata URL:er för testning.

* **Kör experiment bara så länge det behövs**  - Vi anser att &quot;så länge det behövs&quot; är så lång tid som det krävs för att uppnå statistisk signifikans. Målet [innehåller bästa praxis](https://docs.adobe.com/content/target-microsite/testcalculator.html) för att avgöra när testet har nått den här punkten. Vi rekommenderar att du införlivar den hårdkodade implementeringen av vinnande tester i testarbetsflödet och avsätter lämpliga resurser.

   Att använda Target-plattformen för att&quot;publicera&quot; vinnande tester rekommenderas inte som en permanent lösning, men så länge som det vinnande testet publiceras för 100 % av användarna 100 % av tiden kan det här tillvägagångssättet användas medan processen för att hårdkoda det vinnande testet slutförs.

   Det är också viktigt att tänka på vad ditt test har ändrats. Om du uppdaterar färgen på knappar eller andra mindre objekt som inte är textbaserade på sidan påverkas inte den organiska rankningen. Ändringar av text bör dock vara hårdkodade.

   Det är också viktigt att tänka på tillgängligheten för sidan som du testar. Om sidan inte är tillgänglig för sökmotorerna och aldrig har utformats för att rangordnas i organiska sökningar, till exempel en särskild landningssida för en e-postkampanj, gäller inget av det ovanstående.

Google säger att om du följer dessa riktlinjer&quot;bör testerna få liten eller ingen effekt på din webbplats i sökresultaten&quot;.

Förutom dessa riktlinjer ger Google även ytterligare en vägledning i dokumentationen till verktyget Content Experiments:

* &quot;Variantsidorna ska bibehålla innehållets anda på originalsidorna. Dessa variationer bör inte ändra innebörden av eller användarens allmänna uppfattning av det ursprungliga innehållet.&quot;

Google visar som exempel att&quot;om en webbplats originalsida läses in med nyckelord som inte relaterar till kombinationerna som visas för användarna, kan vi ta bort den webbplatsen från vårt index.&quot;

Vi anser att det skulle vara svårt att oavsiktligt ändra innebörden i det ursprungliga innehållet i testvariationer, men vi rekommenderar att du är medveten om nyckelordsteman på en sida och behåller dessa teman. Ändringar av sidinnehåll, särskilt när du lägger till eller tar bort relevanta nyckelord, kan leda till att URL:en rangordnas vid organisk sökning. Vi rekommenderar att du samarbetar med din SEO-partner som en del av testprotokollet.

## Börjar {#bots}

Adobe Target använder [DeviceAtlas](https://deviceatlas.com/) för att identifiera kända fel. Trafik som identifieras som genererad av en robot betjänas fortfarande, precis som en vanlig användare, för att säkerställa att den överensstämmer med riktlinjerna för SEO. Om du använder robottrafik kan du skeva A/B-tester eller personaliseringsalgoritmer om de behandlas som vanliga användare. Om en känd robot upptäcks i din Target-aktivitet behandlas trafiken därför något annorlunda. Att ta bort robottrafik ger en mer exakt mätning av användaraktivitet.

För känd robottrafik gäller följande:

* Skapa eller hämta en besökarprofil
* Logga alla profilattribut eller kör profilskript
* Slå upp Adobe Audience Manager-segment (AAM) (om tillämpligt)
* Använd robottrafik för att modellera och leverera personaliserat innehåll för aktiviteter i Recommendations, Auto Target, Automated Personalization eller Auto Allocate
* Logga ett aktivitetsbesök för rapportering
* Loggdata som ska skickas till Adobe Experience Cloud-plattformen
