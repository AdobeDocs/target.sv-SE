---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;sökmotoroptimering;sökmotoroptimering;seo;edge clusters, central clusters;at.js;mbox.js;
description: Lär dig hur [!DNL Adobe Target] fungerar, inklusive information om JavaScript-bibliotek (AEP Web SDK at.js), datacenter i Adobe, SEO-testning och bots.
title: Hur fungerar  [!DNL Target] ?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '2465'
ht-degree: 0%

---

# Så här fungerar [!DNL Adobe Target]

Lär dig hur [!DNL Adobe Target] fungerar, inklusive information om JavaScript-biblioteken ([!DNL Adobe Experience Platform Web SDK] och at.js). I den här artikeln presenteras även de olika aktivitetstyper som du kan skapa med [!DNL Target]. Du kan också lära dig mer om gränsnätverket [!DNL Target], sökmotoroptimering (SEO) och hur [!DNL Target] identifierar robotar.

## [!DNL Adobe Target] JavaScript-bibliotek {#libraries}

[!DNL Target] integreras med webbplatser med [!DNL Experience Platform Web SDK] eller at.js:

* **[!DNL Adobe Experience Platform Web SDK]:** [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} är ett nytt JavaScript-bibliotek på klientsidan. Med [!DNL Experience Platform Web SDK] kan kunder i [!DNL Adobe Experience Cloud] interagera med de olika tjänsterna i [!DNL Experience Cloud] (inklusive [!DNL Target]) via Edge Network [!DNL Experience Platform]. [!DNL Adobe] rekommenderar att alla nya [!DNL Target]-kunder implementerar [!DNL Experience Platform Web SDK].
* **at.js:** at.js-biblioteket är ett implementeringsbibliotek för [!DNL Target]. at.js-biblioteket ger bättre sidladdningstider för webbimplementeringar och ger bättre implementeringsalternativ för enkelsidiga program. at.js uppdateras ofta med nya funktioner. [!DNL Adobe] rekommenderar att alla kunder som använder at.js uppdaterar sina implementeringar till den [senaste versionen av at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

>[!NOTE]
>
>mbox.js-biblioteket är ett äldre implementeringsbibliotek för [!DNL Target]. Biblioteket mbox.js stöds inte längre efter den 31 mars 2021. Uppgradera till Experience Platform Web SDK (rekommenderas) eller till den senaste versionen av at.js.

Referera [!DNL Experience Platform Web SDK] eller at.js på alla sidor på din webbplats. Du kan till exempel lägga till ett av dessa bibliotek i det globala sidhuvudet. Du kan också överväga att använda [taggar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) för att implementera [!DNL Target].

Följande resurser innehåller detaljerad information som kan hjälpa dig att implementera [!DNL Experience Platform Web SDK] eller at.js:

* [[!DNL Adobe Experience Platform Web SDK] extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html){target=_blank}
* [Implementera [!DNL Target] med [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html){target=_blank}

Varje gång en besökare begär en sida som har optimerats för [!DNL Target] skickas en begäran till målsystemet. Begäran hjälper till att avgöra vilket innehåll som ska användas för besökaren. Den här processen utförs i realtid. Varje gång en sida läses in görs en begäran om innehållet och utförs av systemet. Innehållet styrs av reglerna för marknadsföringsstyrda aktiviteter och upplevelser och är riktat till den enskilda besökaren. Innehållet får det att varje besökare mest sannolikt svarar på, interagerar med eller till slut köper. Personaliserat innehåll hjälper till att maximera svarsfrekvenser, förvärvsfrekvens och intäkter.

I [!DNL Target] är varje element på sidan en del av en upplevelse för hela sidan. Varje upplevelse kan innehålla flera element på sidan.

Det innehåll som visas för besökarna beror på vilken typ av aktivitet du skapar:

### [!UICONTROL A/B Test]

Innehållet som visas i ett grundläggande A/B-test väljs slumpmässigt bland de upplevelser som du tilldelar aktiviteten. Du kan tilldela procentvärden för trafikallokering för varje upplevelse. Som ett resultat av denna slumpmässiga uppdelning av trafiken kan det ta en betydande del av den inledande trafiken innan procentsatserna blir ojämnade. Om du till exempel skapar två upplevelser väljs startupplevelsen slumpmässigt. Om trafiken är liten är det möjligt att andelen besökare kan skevas mot en upplevelse. När trafiken ökar utjämnas procentsatserna.

Du kan ange procentvärden för varje upplevelse. I det här fallet genereras ett slumpmässigt tal och det talet används för att välja vilken upplevelse som ska visas. De resulterande procentsatserna kanske inte matchar de angivna målen exakt, men mer trafik innebär att upplevelserna ska delas närmare målmålen.

1. En kund begär en sida från servern och den visas i webbläsaren.
1. En cookie från första part är inställd i kundens webbläsare för att lagra kundens beteende.
1. Sidan anropar målsystemet.
1. Innehåll visas baserat på reglerna för din aktivitet.

Mer information finns i [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] identifierar en vinnare bland två eller flera upplevelser. [!UICONTROL Auto-Allocate] omfördelar automatiskt mer trafik till den vinnande upplevelsen, vilket bidrar till att öka konverteringarna medan testet fortsätter att köras och lära sig mer.

Mer information finns i [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

### [!UICONTROL Auto-Target] (AT)

[!UICONTROL Auto-Target] använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser. [!UICONTROL Auto-Target] är den mest anpassade upplevelsen för varje besökare. Leveransen av upplevelsen baseras på enskilda kundprofiler och beteendet hos tidigare besökare med liknande profiler. Använd [!UICONTROL Auto-Target] för att anpassa innehåll och driva konverteringar.

Mer information finns i [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP) kombinerar erbjudanden eller meddelanden och använder avancerad maskininlärning för att matcha olika erbjudandevariationer för varje besökare. Leveransen av upplevelser bygger på individuella kundprofiler för att personalisera innehåll och driva på lyft.

Mer information finns i [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### [!UICONTROL Experience Targeting] (XT)

[!UICONTROL Experience Targeting] (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.

[!UICONTROL Experience Targeting], inklusive geolokalisering, är värdefullt för att definiera regler som riktar en viss upplevelse eller innehåll till en viss målgrupp. Flera regler kan definieras i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper. När besökarna visar din webbplats utvärderar [!UICONTROL Experience Targeting] (XT) dem för att avgöra om de uppfyller de villkor du angett. Om de uppfyller kriterierna anger de aktiviteten och den upplevelse som är utformad för att kvalificera målgrupper visas. Ni kan skapa upplevelser för flera målgrupper inom en enda aktivitet.

Mer information finns i [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4).

### [!UICONTROL Multivariate Test] (MVT)

[!UICONTROL Multivariate Testing] (MVT) jämför kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp. MVT hjälper till att identifiera vilket element som mest påverkar aktivitetens framgång.

Mer information finns i [Multivariate Test](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499).

### [!UICONTROL Recommendations]

[!UICONTROL Recommendations]-aktiviteter visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktivitet eller andra algoritmer. Recommendations hjälper kunderna att hänvisa till relevanta objekt som de annars kanske inte känner till.

Mer information finns i [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

## Edge Network {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

En&quot;Edge&quot; är en geografiskt spridd serverarkitektur som ger optimal svarstid för besökare som begär innehåll, oavsett var i världen de befinner sig.

För att förbättra svarstiderna är [!DNL Target] Edge värd endast för aktivitetslogik, cachelagrade profiler och erbjudandeinformation.

Aktivitets- och innehållsdatabaser, [!DNL Analytics] data, API:er och marknadsföringsanvändargränssnitt finns i Adobe Central Clusters. Uppdateringar skickas sedan till [!DNL Target]-kanterna. Centrala kluster och Edge Clusters synkroniseras automatiskt för att kontinuerligt uppdatera cachelagrade aktivitetsdata. Alla 1:1-modelleringar lagras också på varje kant, så dessa mer komplexa begäranden kan också bearbetas på kanten.

Varje Edge Cluster har all information som krävs för att besvara besökarens begäran om innehåll och spåra analysdata på begäran. Besöksförfrågningar dirigeras till närmaste Edge-kluster.

Mer information finns i rapporten [Adobe Target Security Overview](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

[!DNL Target]-lösningen finns på datacenter som ägs av Adobe och som hyrs av Adobe över hela världen.

Platserna för centrala kluster innehåller både en datainsamlingscentral och en datacentral. Edge klusterplatser innehåller bara ett datainsamlingscenter. Varje rapportsvit tilldelas ett specifikt databehandlingscenter.

Data om kundwebbplatsaktivitet samlas in av de närmaste sju Edge Clusters. Dessa data är avsedda för en kunds förbestämda mål för centrala kluster (en av tre platser: Oregon, Dublin, Singapore) för behandling. Data för besökarprofilen lagras i det Edge-kluster som ligger närmast besökaren. Edge klusterplatser är bland annat Centralklusterplatser och Virginia, Mumbai, Sydney och Tokyo.

I stället för att svara på alla målförfrågningar från en enda plats, behandlas förfrågningar av det Edge-kluster som ligger närmast besökaren. Denna process bidrar till att minska effekten av restiden mellan nätverk och Internet.

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
>[!DNL Adobe Target] har för närvarande inget Edge-kluster i Kina och besökarens prestanda är begränsat för [!DNL Target]-kunder i Kina. På grund av brandväggen och bristen på Edge Clusters i landet kan upplevelserna på webbplatser med [!DNL Target] som distribuerats påverkas. Upplevelserna kan ta lång tid att återge och sidinläsningen kan påverkas. Marknadsförarna kan även uppleva fördröjning när de använder [!DNL Target]-redigeringsgränssnittet.

Du kan tillåtslista [!DNL Target] Edge Clusters om du vill. Mer information finns i [tillåtslista målkantnoder](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank}.

## Skyddad användarupplevelse {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] ser till att tillgängligheten och prestandan för målinriktningsinfrastrukturen är så tillförlitlig som möjligt. Ett kommunikationsavbrott mellan en besökares webbläsare och [!DNL Adobe] servrar kan dock orsaka avbrott i innehållsleveransen.

För att skydda mot avbrott i tjänsten och anslutningsproblem ställs alla platser in på att inkludera standardinnehåll (definieras av klienten). Standardinnehållet visas om användarens webbläsare inte kan ansluta till [!DNL Target].

Inga ändringar görs på sidan om användarens webbläsare inte kan ansluta inom en angiven tidsgräns (som standard: 15 sekunder). Om den här tidsgränsen nås visas standardplatsinnehåll.

[!DNL Adobe] skyddar användarupplevelsen genom att optimera och skydda prestanda.

* [!DNL Adobe] säkerställer prestandatester baserat på branschstandarder som garanteras av Adobes serviceavtal.
* Edge Network levererar data i rätt tid.
* [!UICONTROL Adobe] använder en metod med flera nivåer för att skydda sina program så att kunderna får högsta möjliga tillgänglighet och tillförlitlighet.
* [!DNL Target] Consulting erbjuder implementeringshjälp och fortlöpande produktsupport.

## SEO-testning (Search Engine Optimization) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] följer riktlinjerna för sökmotor för testning.

Google uppmuntrar användare att testa. Google anger i sin dokumentation att A/B och [!UICONTROL Multivariate Testing] inte skadar rangordningar för organisk sökmotor om du följer vissa riktlinjer.

Mer information finns i följande Google-resurser:

* [Webbplatstestning och Google Search](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentera och svepa in](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

Riktlinjer presenterades i ett [blogginlägg från Google Webmaster Central](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Även om posten är från 2012 är den fortfarande Google senaste uttalande om ärendet och riktlinjerna är fortfarande relevanta.

* **Ingen insvepning**: Vid insvepning visas en uppsättning innehåll för dina användare och en annan uppsättning innehåll för sökmotorbotar. Insvepning åstadkoms genom att man specifikt identifierar botar och målmedvetet matar in olika innehåll.

  [!DNL Target], som en plattform, har konfigurerats för att behandla sökmotorrobotar på samma sätt som andra användare. Detta innebär att botar kan inkluderas i aktiviteter om de väljs slumpmässigt och&quot;se&quot; testvariationerna.

* **Använd rel=&quot;canonical&quot;**: Ibland måste ett A/B-test konfigureras med olika URL:er för variationerna. I de här instanserna ska alla variationer innehålla en `rel="canonical"`-tagg som refererar till den ursprungliga (kontroll) URL:en. Anta till exempel att [!DNL Adobe] testar sin hemsida med olika URL:er för varje variation. Följande kanoniska tagg för hemsidan finns i taggen `<head>` för varje variant:

  `<link rel="canonical" href="https://www.adobe.com" />`

* **Använd 302 (tillfälliga) omdirigeringar**: I de fall där separata URL:er används för variantsidorna i ett test rekommenderar Google att du använder en 302-omdirigering för att dirigera trafik till testvarianterna. Omdirigeringen 302 meddelar sökmotorerna att omdirigeringen är tillfällig och endast är aktiv så länge som testet körs.

  En 302-omdirigering är en omdirigering på serversidan, och [!DNL Target], tillsammans med de flesta optimeringsleverantörer, använder funktioner på klientsidan. Omdirigering är därför ett område där [!DNL Target] inte är helt kompatibelt med Google rekommendationer. Detta tillvägagångssätt påverkar dock endast en liten del av testerna. Standardmetoden för att köra tester genom [!DNL Target] kräver att innehållet ändras inom en enda URL, så inga omdirigeringar behövs. Det finns tillfällen när klienterna måste använda flera URL:er för att representera testvariationerna. I de här instanserna använder [!DNL Target] JavaScript `window.location`-kommandot. Det här kommandot instruerar användare att testa variationer, vilket inte uttryckligen anger om omdirigeringen är 301 eller 302.

  [!DNL Adobe] fortsätter att söka efter lämpliga lösningar som är helt anpassade efter riktlinjerna för sökmotorer. För de klienter som måste använda separata URL:er för testning är [!DNL Adobe] säker på att korrekt implementering av kanoniska taggar minskar riskerna som är associerade med det här tillvägagångssättet.

* **Kör försök bara så länge som det behövs**: [!DNL Adobe] tror att &quot;så länge det behövs&quot; är så lång som det krävs för att uppnå statistisk signifikans. [!DNL Target] innehåller bästa praxis och [!DNL Adobe Target] [Beräkna provstorlek](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) för att avgöra när testet har nått den här punkten. [!DNL Adobe] rekommenderar att du inkluderar den hårdkodade implementeringen av vinnande tester i ditt testarbetsflöde och tilldelar lämpliga resurser.

  Du bör inte använda plattformen [!DNL Target] för att&quot;publicera&quot; vinnande tester som en permanent lösning. Om det vinnande testet publiceras för 100 % av användarna 100 % av tiden kan det här tillvägagångssättet användas medan processen med att hårdkoda det vinnande testet slutförs.

  Det är också viktigt att tänka på vad ditt test har ändrats. Om du bara uppdaterar färgen på knappar eller andra mindre objekt som inte är textbaserade på sidan påverkas inte den organiska rankningen. Ändringar av text bör dock vara hårdkodade.

  Det är också viktigt att tänka på tillgängligheten för sidan som du testar. Om sidan inte är tillgänglig för sökmotorer och inte har utformats för att rangordnas i organiska sökningar, gäller inget av ovanstående. Ett exempel är en dedikerad landningssida för en e-postkampanj.

Google uppger att om du följer dessa riktlinjer&quot;bör testerna få liten eller ingen effekt på webbplatsen i sökresultaten&quot;.

Förutom dessa riktlinjer ger Google även ytterligare en vägledning i dokumentationen till verktyget Innehållsexperiment:

* &quot;Variantsidorna ska bibehålla innehållets anda på originalsidorna. Dessa variationer bör inte ändra innebörden av eller användarens allmänna uppfattning av det ursprungliga innehållet.&quot;

Google anger som exempel att om en webbplats originalsida läses in med nyckelord som inte relaterar till de kombinationer som visas för användarna, kan vi ta bort den webbplatsen från vårt index.

[!UICONTROL Adobe] anser att det skulle vara svårt att oavsiktligt ändra innebörden av det ursprungliga innehållet i testvariationer. [!UICONTROL Adobe] rekommenderar dock att du är medveten om nyckelordsteman på en sida och underhåller dessa teman. Ändringar av sidinnehåll, särskilt när du lägger till eller tar bort relevanta nyckelord, kan leda till att URL:en rangordnas vid organisk sökning. [!DNL Adobe] rekommenderar att du samarbetar med SEO-partnern som en del av testprotokollet.

## Bots {#bots}

Adobe [!DNL Target] använder [ DeviceAtlas ](https://deviceatlas.com/device-data/user-agent-tester/)-måttet isRobot för att identifiera kända botar baserat på användaragentsträngen som skickas i begärandehuvudet.

>[!NOTE]
>
> För [!DNL Server-Side]-begäranden ges det värde som skickas i [Request&#39;s &quot;Context&quot; node](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) företräde framför User Agent-strängen för robotidentifiering.

Trafik som identifieras som genererad av en robot betjänas fortfarande av innehåll. Bots behandlas som en vanlig användare för att säkerställa att [!DNL Target] följer riktlinjerna för SEO. Om du använder robottrafik kan du skeva A/B-tester eller personaliseringsalgoritmer om de behandlas som vanliga användare. Om en känd robot upptäcks i din [!DNL Target]-aktivitet behandlas trafiken därför något annorlunda. Att ta bort robottrafik ger en mer exakt mätning av användaraktivitet.

För känd robottrafik [!DNL Target] gäller följande:

* Skapa eller hämta en besökarprofil
* Logga alla profilattribut eller kör profilskript
* Slå upp [!DNL Adobe Audience Manager] (AAM) segment (om tillämpligt)
* Använd robottrafik vid modellering och betjäning av anpassat innehåll för [!UICONTROL Recommendations]-, [!UICONTROL Auto-Target]-, [!UICONTROL Automated Personalization]- eller [!UICONTROL Auto-Allocate]-aktiviteter
* Logga ett aktivitetsbesök för rapportering
* Loggdata som ska skickas till plattformen [!DNL Adobe Experience Cloud]

För känd robottrafik när [!UICONTROL Analytics for Target] (A4T) används gör [!DNL Target] inte:

* Skicka händelser till [!DNL Analytics]

[!DNL Target] returnerar inte för känd robottrafik när client_side-loggning används:

* talnyttolast
