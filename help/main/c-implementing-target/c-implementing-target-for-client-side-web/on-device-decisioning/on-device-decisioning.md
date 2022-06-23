---
keywords: implementering;javascript-bibliotek;js;atjs;on device decisioning;on device decisioning;at.js;on device;on device
description: Lär dig hur du utför enhetsbeslut med biblioteket at.js
title: Hur fungerar On-device Decisioning med JavaScript-biblioteket at.js?
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '3447'
ht-degree: 1%

---

# Enhetsbeslut för at.js

Från och med version 2.5.0 kan at.js fatta beslut på enheter. Med enhetsbaserad beslutsfattande kan du cachelagra [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) och [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) (XT) aktiviteter i webbläsaren som utför minnesbaserad beslutsfattande utan blockerande nätverksbegäran till [!DNL Adobe Target] Edge Network.

[!DNL Target] erbjuder även flexibiliteten att leverera den mest relevanta och aktuella upplevelsen från dina experimentella och HTML-drivna personaliseringsaktiviteter (Machine Learning) via ett live-serversamtal. Med andra ord, när prestanda är viktigast kan du välja att använda enhetsbeslut. Men när den mest relevanta, aktuella och ML-drivna upplevelsen behövs kan ett serveranrop göras istället.

## Vilka är fördelarna med beslut på enheter?

Fördelarna med beslut på enheter är bland annat:

* **Leverera blixtsnabba beslut och upplevelser.** Buckling och beslut utförs i minnet och i webbläsaren för att undvika blockering av nätverksbegäranden.
* **Förbättra programmets prestanda.** Kör experiment och leverera personalisering till kunder och användare utan att kompromissa med slutanvändarupplevelserna.
* **Förbättra Google Site Quality Score.** I och med att beslut fattas i minnet kan du förbättra Google Site Quality-poängen för ditt onlineföretag så att det blir lättare att hitta för kunderna.
* **Lär dig av realtidsanalyser.** Få insikter om aktivitetens resultat i realtid via [Analyser för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)-rapportering. Med A4T kan ni styra er strategi vid kritiska ögonblick.

## Funktioner som stöds

Adobe Target JS SDK ger kunderna flexibilitet att välja mellan prestanda och aktualitet för beslut. Med andra ord, om det viktigaste är att leverera det mest relevanta och engagerande personaliserade innehållet via maskininlärning, bör du ringa ett live-serversamtal. Men när prestanda är viktigare bör man fatta beslut på enheten och i minnet. Information om hur du väljer enheter finns i listan över funktioner som stöds:

* Typ av aktivitet
* Målgruppsanpassning
* Allokeringsmetod

Mer information finns i [Funktioner som stöds för beslut på enheten](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

## Hur fungerar beslut på enheter?

När du distribuerar och initierar at.js med enhetsspecifik beslutsfattande aktiverat, är en [regelartefakt](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/){target=_blank} som innehåller ditt enhetsbeslut för A/B- och XT-aktiviteter, målgrupper och resurser hämtas från närmaste Akamai CDN till besökaren och cachas lokalt i besökarens webbläsare. När en begäran görs från at.js för att hämta en upplevelse, bestäms vilken upplevelse som ska returneras i minnet utifrån de metadata som är kodade i den cachelagrade regelartefakten.

## Beslutsmetod

Med beslut på enheten [!DNL Target] introducerar en ny inställning med namnet [!UICONTROL Decisioning Method]. The [!UICONTROL Decisioning Method] anger hur at.js levererar era upplevelser. [!UICONTROL Decisioning Method] har tre värden:

* [!UICONTROL Server-side only]
* [!UICONTROL On-device only]
* [!UICONTROL Hybrid]

### Endast serversidan

[!UICONTROL Server-side only] är standardmetoden för beslut som anges i rutan när at.js 2.5.0+ implementeras och distribueras på dina webbegenskaper.

Använda [!UICONTROL server-side only] som standardkonfiguration innebär att alla beslut fattas på [!DNL Target] edge-nätverk, vilket innebär ett blockerande serveranrop. Den här metoden kan innebära inkrementell fördröjning, men ger även avsevärda fördelar, som att du kan använda Target maskininlärningsfunktioner som inkluderar [Recommendations](/help/main/c-recommendations/recommendations.md), [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP), och [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) verksamhet.

Dessutom kan ni förbättra era personaliserade upplevelser genom att använda Target-användarprofilen, som bevaras i olika sessioner och kanaler, och få ett kraftfullt resultat för ert företag.

Till sist [!UICONTROL server-side only] Med kan ni använda Adobe Experience Cloud och finjustera målgrupper som kan riktas mot genom Audience Manager och Adobe Analytics.

Följande diagram visar interaktionen mellan besökaren, webbläsaren, at.js 2.5.0+, och Adobe Target Edge-nätverket. Det här flödesdiagrammet fångar nya besökare och returnerar besökare.

![Endast serversidesflödesdiagram](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

Följande lista motsvarar siffrorna i diagrammet:

| Steg | Beskrivning |
| --- | --- |
| 1 | The [!DNL Experience Cloud Visitor ID] hämtas från [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>   At.js-biblioteket kan också läsas in asynkront med ett valfritt fördolt fragment som implementerats på sidan. |
| 3 | At.js-biblioteket döljer kroppen för att förhindra flimmer. |
| 4 | En sidinläsningsbegäran görs som innehåller alla konfigurerade parametrar, t.ex. (ECID, Kund-ID, Anpassade parametrar, Användarprofil osv.) |
| 5 | Profilskript körs och matas sedan in i profilarkivet.<br>Profilarkivet begär kvalificerade målgrupper från målgruppsbiblioteket (till exempel målgrupper som delas från [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]och så vidare.)<br>Kundattribut skickas till profilarkivet i en gruppbearbetning. |
| 6 | Profilarkivet används för att filtrera aktiviteter genom att kvalificera och klippa målgrupper. |
| 7 | Det resulterande innehållet väljs när upplevelsen bestäms från live [!DNL Target] verksamhet. |
| 8 | Med biblioteket at.js döljs motsvarande element på sidan som är kopplade till upplevelsen som måste återges. |
| 9 | I biblioteket at.js visas brödtexten så att resten av sidan kan läsas in så att besökaren kan se den. |
| 10 | At.js-biblioteket ändrar DOM för att återge upplevelsen från Target Edge Network. |
| 11 | Upplevelsen renderar för besökaren. |
| 12 | Hela webbsidan läses in. |
| 13 | [!DNL Analytics] data skickas till datainsamlingsservrar. |
| 14 | Måldata matchas mot [!DNL Analytics] data via SDID och bearbetas till [!DNL Analytics] rapporterar lagring. [!DNL Analytics] data kan sedan visas i båda [!DNL Analytics] och [!DNL Target] via [!UICONTROL Analytics for Target] (A4T)-rapporter. |

### Endast på enheten

[!UICONTROL On-Device only] är den beslutsmetod som måste anges i at.js 2.5.0+ när enhetsbeslut endast ska användas på hela webbsidor.

Enhetsbeslut kan leverera upplevelser och personaliseringsaktiviteter blixtsnabbt eftersom besluten fattas utifrån en cache-lagrad regelartefakt som innehåller alla aktiviteter som är kvalificerade för enhetsbeslut.

Mer information om vilka aktiviteter som är kvalificerade för enhetsbeslut finns i [Funktioner som stöds vid beslut på enheten](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

Den här beslutsmetoden bör endast användas om prestanda är mycket kritiskt för alla sidor som kräver beslut från [!DNL Target]. Tänk dessutom på att när du väljer den här beslutsmetoden ska du [!DNL Target] aktiviteter som inte är kvalificerade för enhetsbeslut kommer inte att levereras eller utföras. At.js-biblioteket 2.5.0+ är konfigurerat att endast söka efter den cachelagrade regelartefakten för att fatta beslut.

Följande diagram visar interaktionen mellan besökaren, webbläsaren, at.js 2.5.0+, och Akamai CDN. Akamai CDN cachar regelfelaktigheten vid besökarens första besök. Vid den första sidbesöket hos en ny besökare måste JSON-regelartefakten hämtas från Akamai CDN för att cachas lokalt i besökarens webbläsare. När JSON-regelartefakten har hämtats fattas beslutet omedelbart utan ett blockerande nätverksanrop. I följande flödesdiagram visas nya besökare.

![Flödesdiagram endast på enheten](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

Följande lista motsvarar siffrorna i diagrammet:

>[!NOTE]
>
>[!DNL Adobe Target] Administratörsservrar kvalificerar alla dina aktiviteter som är berättigade till enhetsbeslut, genererar JSON-regelartefakten och sprider den till Akamai CDN. Dina aktiviteter övervakas kontinuerligt för uppdateringar av en ny JSON-regelartefakt som ska spridas till Akamai CDN.

| Steg | Beskrivning |
| --- | --- |
| 1 | The [!DNL Experience Cloud Visitor ID] hämtas från [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>At.js-biblioteket kan också läsas in asynkront med ett valfritt fördolt fragment som implementerats på sidan. |
| 3 | At.js-biblioteket döljer kroppen för att förhindra flimmer. |
| 4 | I at.js-biblioteket görs en begäran om att hämta JSON-regelartefakten från närmaste Akamai CDN till besökaren. |
| 5 | Akamai CDN svarar med JSON-regelartefakten. |
| 6 | JSON-regelartefakten cachelagras lokalt i besökarens webbläsare. |
| 7 | I biblioteket at.js tolkas JSON-regelartefakten och beslutet att hämta upplevelsen verkställs och de testade elementen döljs. |
| 8 | I biblioteket at.js visas brödtexten så att resten av sidan kan läsas in så att besökaren kan se den. |
| 9 | At.js-biblioteket ändrar DOM för att återge upplevelsen från den cachelagrade JSON-regelartefakten. |
| 10 | Upplevelsen renderar för besökaren. |
| 11 | Hela webbsidan läses in. |
| 12 | [!DNL Analytics] data skickas till datainsamlingsservrar. Måldata matchas mot [!DNL Analytics] data via SDID och bearbetas till [!DNL Analytics] rapporterar lagring. [!DNL Analytics] data kan sedan visas i båda [!DNL Analytics] och [!DNL Target] via Analytics för Target-rapporter (A4T). |

I följande diagram visas interaktionen mellan besökaren, webbläsaren, at.js 2.5.0+, och den cachelagrade JSON-regelartefakten för besökarens efterföljande sidträff eller återbesök. Eftersom JSON-regelartefakten redan är cachelagrad och tillgänglig i webbläsaren, fattas beslutet omedelbart utan ett blockerande nätverksanrop. Det här flödesdiagrammet fångar efterföljande sidnavigering eller returnerar besökare.

![Flödesdiagram endast på enheten för efterföljande sidnavigering och återkommande besök](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

Följande lista motsvarar siffrorna i diagrammet:

>[!NOTE]
>
>[!DNL Adobe Target] Administratörsservrar kvalificerar alla dina aktiviteter som är berättigade till enhetsbeslut, genererar JSON-regelartefakten och sprider den till Akamai CDN. Dina aktiviteter övervakas kontinuerligt för uppdateringar av en ny JSON-regelartefakt som ska spridas till Akamai CDN.

| Steg | Beskrivning |
| --- | --- |
| 1 | The [!DNL Experience Cloud Visitor ID] hämtas från [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>At.js-biblioteket kan också läsas in asynkront med ett valfritt fördolt fragment som implementerats på sidan. |
| 3 | At.js-biblioteket döljer kroppen för att förhindra flimmer. |
| 4 | I biblioteket at.js tolkas JSON-regelartefakten och beslutet i minnet verkställs för att hämta upplevelsen. |
| 5 | De testade elementen är dolda. |
| 6 | I biblioteket at.js visas brödtexten så att resten av sidan kan läsas in så att besökaren kan se den. |
| 7 | At.js-biblioteket ändrar DOM för att återge upplevelsen från den cachelagrade JSON-regelartefakten. |
| 8 | Upplevelsen renderar för besökaren. |
| 9 | Hela webbsidan läses in. |
| 10 | [!DNL Analytics] data skickas till datainsamlingsservrar. Måldata matchas mot [!DNL Analytics] data via SDID och bearbetas till [!DNL Analytics] rapporterar lagring. [!DNL Analytics] data kan sedan visas i båda [!DNL Analytics] och [!DNL Target] via [!UICONTROL Analytics for Target] (A4T)-rapporter. |

### Hybrid

[!UICONTROL Hybrid] är den beslutsmetod som måste anges i at.js 2.5.0+ när både enhetsbeslut och aktiviteter som kräver ett nätverksanrop till Adobe Target Edge-nätverket måste utföras.

När du hanterar både enhetsspecifika och serverbaserade beslutsaktiviteter kan det vara lite komplicerat och omständligt att fundera på hur ni ska driftsätta och tillhandahålla [!DNL Target] på era sidor. Med hybridmetoden som beslutsmetod [!DNL Target] känner till när det måste ringa ett serveranrop till Adobe Target Edge-nätverket för aktiviteter som kräver körning på serversidan, och även när endast enhetsbeslut ska verkställas.

JSON-regelartefakten innehåller metadata som informerar at.js om en mbox har en aktivitet på serversidan som körs eller en beslutsaktivitet på enheten. Denna beslutsmetod säkerställer att aktiviteter som du avser att leverera snabbt genomförs via enhetsspecifika beslut och för aktiviteter som kräver mer kraftfull ML-driven personalisering utförs dessa aktiviteter via Adobe Target Edge-nätverket.

I följande diagram visas interaktionen mellan besökaren, webbläsaren, kl. 2.5.0+, Akamai CDN och Adobe Target Edge Network så att en ny besökare kan besöka din sida för första gången. Det här diagrammet visar att JSON-regelartefakten hämtas asynkront medan besluten fattas via Adobe Target Edge-nätverket.

På så sätt kan du vara säker på att artefaktens storlek, som kan innehålla många aktiviteter, inte påverkar beslutets fördröjning negativt. Om du hämtar JSON-reglerna synkront och fattar beslut efter detta kan det också få negativa effekter på fördröjningen och kan vara inkonsekvent. Därför är hybridmetoden en rekommendation om att alltid göra ett anrop på serversidan för beslut om en ny besökare, och eftersom JSON-regelartefakten cachas parallellt. För efterföljande sidbesök och återbesök görs besluten från cacheminnet och i minnet via JSON-regelartefakten.

![Hybrid-flödesdiagram för en förstagångsbesökare](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

Följande lista motsvarar siffrorna i diagrammet:

>[!NOTE]
>
>[!DNL Adobe Target] Administratörsservrar kvalificerar alla dina aktiviteter som är berättigade till enhetsbeslut, genererar JSON-regelartefakten och sprider den till Akamai CDN. Dina aktiviteter övervakas kontinuerligt för uppdateringar av en ny JSON-regelartefakt som ska spridas till Akamai CDN.

| Steg | Beskrivning |
| --- | --- |
| 1 | The [!DNL Experience Cloud Visitor ID] hämtas från [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>At.js-biblioteket kan också läsas in asynkront med ett valfritt fördolt fragment som implementerats på sidan. |
| 3 | At.js-biblioteket döljer kroppen för att förhindra flimmer. |
| 4 | En sidladdningsbegäran görs till Adobe Target Edge Network, inklusive alla konfigurerade parametrar som (ECID, Kund-ID, Anpassade parametrar, Användarprofil osv.). |
| 5 | Samtidigt begär at.js att JSON-regelartefakten ska hämtas från närmaste Akamai CDN till besökaren. |
| 6 | (Adobe Target Edge Network) Profilskript körs och matas sedan in i profilarkivet. Profilarkivet begär kvalificerade målgrupper från målgruppsbiblioteket (till exempel målgrupper som delas från [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]och så vidare.) |
| 7 | Akamai CDN svarar med JSON-regelartefakten. |
| 8 | Profilarkivet används för att filtrera aktiviteter genom att kvalificera och klippa målgrupper. |
| 9 | Det resulterande innehållet väljs när upplevelsen bestäms från live [!DNL Target] verksamhet. |
| 10 | Med biblioteket at.js döljs motsvarande element på sidan som är kopplade till upplevelsen som måste återges. |
| 11 | I biblioteket at.js visas brödtexten så att resten av sidan kan läsas in så att besökaren kan se den. |
| 12 | At.js-biblioteket ändrar DOM för att återge upplevelsen från Target Edge Network. |
| 13 | Upplevelsen renderar för besökaren. |
| 14 | Hela webbsidan läses in. |
| 15 | [!DNL Analytics] data skickas till datainsamlingsservrar. Måldata matchas mot [!DNL Analytics] data via SDID och bearbetas till [!DNL Analytics] rapporterar lagring. [!DNL Analytics] data kan sedan visas i båda [!DNL Analytics] och [!DNL Target] via [!UICONTROL Analytics for Target] (A4T)-rapporter. |

I följande diagram visas interaktionen mellan besökaren, webbläsaren, at.js 2.5.0+, och den cachelagrade JSON-regelartefakten för efterföljande sidnavigering eller ett returbesök. I det här diagrammet fokuserar du bara på det användningsfall som avgör om det är enheten som ska användas för den efterföljande sidnavigeringen eller det efterföljande besöket. Tänk på att beroende på vilka aktiviteter som är aktiva för vissa sidor kan ett anrop på serversidan göras för att köra beslut på serversidan.

![Hybridflödesdiagram för efterföljande sidnavigering och återkommande besök](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

Följande lista motsvarar siffrorna i diagrammet:

>[!NOTE]
>
>[!DNL Adobe Target] Administratörsservrar kvalificerar alla dina aktiviteter som är berättigade till enhetsbeslut, genererar JSON-regelartefakten och sprider den till Akamai CDN. Dina aktiviteter övervakas kontinuerligt för uppdateringar av en ny JSON-regelartefakt som ska spridas till Akamai CDN.

| Steg | Beskrivning |
| --- | --- |
| 1 | The [!DNL Experience Cloud Visitor ID] hämtas från [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>At.js-biblioteket kan också läsas in asynkront med ett valfritt fördolt fragment som implementerats på sidan. |
| 3 | At.js-biblioteket döljer kroppen för att förhindra flimmer. |
| 4 | En begäran görs för att hämta en upplevelse. |
| 5 | At.js-biblioteket bekräftar att JSON-regelartefakten redan har cache-lagrats och kör beslutet i minnet för att hämta upplevelsen. |
| 6 | De testade elementen är dolda. |
| 7 | I biblioteket at.js visas brödtexten så att resten av sidan kan läsas in så att besökaren kan se den. |
| 8 | At.js-biblioteket ändrar DOM för att återge upplevelsen från den cachelagrade JSON-regelartefakten. |
| 9 | Upplevelsen renderar för besökaren. |
| 10 | Hela webbsidan läses in. |
| 11 | [!DNL Analytics] data skickas till datainsamlingsservrar. Måldata matchas mot [!DNL Analytics] data via SDID och bearbetas till [!DNL Analytics] rapporterar lagring. [!DNL Analytics] data kan sedan visas i båda [!DNL Analytics] och [!DNL Target] via [!UICONTROL Analytics for Target] (A4T)-rapporter. |

## Hur aktiverar jag enhetsbeslut?

Enhetsbeslut är tillgängligt för alla [!DNL Target] kunder som använder At.js 2.5.0+.

Så här aktiverar du enhetsbeslut:

>[!NOTE]
>
>Du måste ha [!UICONTROL Admin] eller [!UICONTROL Approver] [användarroll](/help/main/administrating-target/c-user-management/user-management.md) om du vill aktivera eller inaktivera alternativet för beslut på enhet.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Account details]**.
1. Under **[!UICONTROL Account Details]**, för bilden **[!UICONTROL On-Device Decisioning]** växla till&quot;på&quot;-positionen.

   ![Växla mellan val på enheten](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   The &quot;[!UICONTROL Include all existing on-device decisioning qualified activities in the artifact]&quot;visas om du aktiverar enhetsbeslut.
1. (Villkorligt) Om du vill att alla aktiva Target-aktiviteter som är kvalificerade för enhetsbeslut automatiskt ska inkluderas i artefakten drar du skjutreglaget till&quot;on&quot;-positionen.

   Om du inte aktiverar det här alternativet måste du återskapa och aktivera alla enhetsspecifika beslutsaktiviteter så att de inkluderas i den genererade regelartefakten. Med andra ord, alla aktiviteter i live-läge innan du aktiverar [!UICONTROL On-Device Decisioning] toggle ingår inte i regelartefakten.

När du har aktiverat [!UICONTROL On-Device Decisioning] växla [!DNL Target] börjar generera och sprida [regelartefakter](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/){target=_blank} för klienten.

>[!IMPORTANT]
>
>Se till att du aktiverar växlingsknappen innan du initierar Adobe Target SDK för att använda enhetsbeslut. Regelartefakterna måste först generera och sprida till Akamai CDN:er för att beslut ska kunna fattas på enheten. Spridning kan ta fem till tio minuter innan den första regelartefakten genereras och sprids till Akamai CDN.

## Hur konfigurerar jag at.js 2.5.0+ att använda enhetsspecifik beslutsfattande?

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Account details]**.
1. Under **[!UICONTROL Implementation Methods]** > **[!UICONTROL Main Implementation Method]**, klicka **[!UICONTROL Edit]** bredvid din at.js-version (måste vara at.js 2.5.0 eller senare).

   ![Redigera inställningar för den huvudsakliga implementeringsmetoden](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >Innan du ändrar de här standardinställningarna bör du rådfråga Client Care så att du inte påverkar den aktuella implementeringen.

1. Välj önskad beslutsmetod:

   * [!UICONTROL Server-side only]
   * [!UICONTROL On-device only]
   * [!UICONTROL Hybrid]

   ![Redigera inställningspanelen at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### Globala inställningar

Du kan konfigurera ett standardvärde [!UICONTROL Decisioning Method] för alla [!DNL Target] beslut. De olika beslutsmetoderna är [!UICONTROL Server-side only], [!UICONTROL On-device only]och [!UICONTROL Hybrid]. Den valda beslutsmetoden i målgränssnittet är konfigurerad i `window.targetGlobalSettings` under `decisioningMethod` fält. Läs mer om `decisioningMethod` in [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

```javascript
<head> 
    <script type="text/javascript">

        window.targetGlobalSettings = { 
            clientCode: "yourClientCodeHere", 
            imsOrgId: "imsOrgId@AdobeOrg", 
            decisioningMethod: "on-device"

        }; 
    </script>

    <script type="text/javascript" src="at.js"></script> 
</head>
```

### Anpassad inställning

Om du anger `decisioningMethod` in `window.targetGlobalSettings`, men vill åsidosätta `decisioningMethod` för varje Adobe Target-beslut utifrån ditt användningsfall kan du utföra den här proceduren genom att ange `decisioningMethod` in At.js2.5.0+&#39;s [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/){target=_blank}-anrop.

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
});
```

>[!NOTE]
>
>Om du vill använda&quot;on-device&quot; eller&quot;hybrid&quot; som en beslutsmetod i getOffers()-anropet kontrollerar du att den globala inställningen har `decisioningMethod` som&quot;på enheten&quot; eller&quot;hybrid&quot;. At.js-biblioteket 2.5.0+ måste känna till om JSON-regelartefakten ska hämtas och cachelagras direkt efter att sidan har lästs in. Om beslutsmetoden för den globala inställningen är inställd på &quot;server-side&quot;, och &quot;on-device&quot; eller &quot;hybrid&quot;-beslutsmetoden skickas till getOffers()-anropet, skulle at.js 2.5.0+ inte ha JSON-regelartefakten cachelagrad för att köra dina enhetsbeslut.

### Cacheminne för felaktigheter

[!DNL Target] representerar aktiviteter som kvalificerar sig för enhetsbeslut som en artefakt som består av metadata, regler och villkor. Artefakten cachelagras på Akamai CDN. Under användarens första besök hämtar och cachelagrar användarens webbläsare den artefakt som representerar dina beslutsaktiviteter på enheten.

Vid efterföljande besök på webbplatsen kontrollerar webbläsaren automatiskt om en nyare version av artefakten måste hämtas. Den här kontrollen lägger till fördröjning. TTL för artefaktcache anger hur många minuter du inte vill att webbläsaren ska kontrollera om det finns en uppdaterad artefakt sedan den senaste slutförda hämtningen. Ju längre tidsram, desto bättre prestanda. Ju kortare tidsram, desto bättre dataaktualitet, men till priset av extra latens.

## Hur vet jag att en aktivitet är berättigad till enhetsbeslut?

När du har skapat en aktivitet som kan väljas på enheten, visas en etikett som [!UICONTROL On-Device Decisioning Eligible], visas i aktivitetens [!UICONTROL Overview] sida.

![Valbar etikett på aktivitetens översiktssida för val på enhet.](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

Den här etiketten betyder inte att aktiviteten alltid levereras via enhetsbeslut. Endast när at.js 2.5.0+ är konfigurerad att använda enhetsspecifik beslutsfattande körs den här aktiviteten på enheten. Om at.js 2.5.0+ inte är konfigurerad att använda på enheten kommer aktiviteten fortfarande att levereras via ett serveranrop som görs från at.js.

Du kan filtrera efter alla aktiviteter som är berättigade till enhetsbeslut på [!UICONTROL Activities] via [!UICONTROL On-Device Decisioning Eligible] filter.

![Berättigat filter på sidan Aktiviteter för val på enhet.](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>När du har skapat och aktiverat en aktivitet som är berättigad att fatta beslut på en enhet kan det ta fem till tio minuter innan den ingår i den regelartefakt som genereras och sprids till Akamai CDN-instansen.

## Sammanfattning av steg som säkerställer att mina beslutsaktiviteter på enheten levereras via At.js 2.5.0+?

1. Gå till Adobe Target-gränssnittet och navigera till **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!DNL Account Details]** för att aktivera **[!UICONTROL On-Device Decisioning]** växla.
1. Aktivera **&quot;[!UICONTROL Include all existing on-device decisioning qualified activities in the artifact]&quot;** växla.

   Den första genereringen av JSON-regelartefakter kan ta upp till 10 minuter.

1. Skapa och aktivera en [aktivitetstyp som stöds av enhetsbeslut](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/), och kontrollera att det är valbart att fatta beslut på enheten.
1. Ange **[!UICONTROL Decisioning Method]** till antingen **[!UICONTROL “Hybrid”]** eller **[!UICONTROL “On-device only”]** via användargränssnittet för at.js-inställningarna.
1. Ladda ned och driftsätt At.js 2.5.0+ på sidorna.
