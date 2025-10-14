---
keywords: Real-Time Customer Data Platform;rtcdp;personalisering;målgrupper;adobe experience platform audiences;profile attributes
description: Lär dig hur du använder integreringen  [!DNL Target]/[!DNL Real-Time Customer Data Platform]  (RTCDP) för att tillhandahålla mer omfattande kunddata och mer slagkraftig personalisering.
title: Hur integrerar jag [!DNL Target] med  [!DNL Real-Time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 4104b6cb67347205c0143c9dea46dd483a8266ce
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 0%

---

# Integrera med [!DNL Real-Time Customer Data Platform]

[!DNL Adobe Experience Platform] (RTCDP) som bygger på [!DNL Real-Time Customer Data Platform] hjälper företag att samla in kända och anonyma data från flera olika företagskällor. Med RTCDP kan ni skapa kundprofiler som kan användas för att leverera personaliserade kundupplevelser i alla kanaler och enheter i realtid.

Mer information om RTCDP finns i [Real-Time Customer Data Platform - översikt](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=sv-SE){target=_blank}.

## Viktiga funktioner

Viktiga funktioner:

* Direkt [!DNL Target]-integrering med Real-Time CDP/[!DNL Adobe Experience Platform] på Edge (tar bort beroendet av [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations Card] med styrning och policytillämpning
* CDP-segment och attribut för delad profil i realtid

## Implementeringsscenarier

I följande avsnitt visas vilken typ av användningsfall för personalisering (nästa session eller samma sida) som är tillgänglig när olika implementeringsmetoder används:

### at.js-implementering

| Lösningar | Användningsfall aktiverat |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) och [!DNL Target]</li><li>[!DNL RTCDP] (Premium eller Ultimate) och [!DNL Target]</li><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM] och [!DNL Target]</li></ul> | Anpassa nästa session |

### Implementering av [!DNL Adobe Experience Platform Web SDK] eller [!DNL Experience Platform Server-Side API]

| Lösningar | Användningsfall aktiverat |
| --- | --- |
| <ul><li>[!DNL RTCDP] (valfri SKU) och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><li>Personalisering på samma sida via Edge</li><li>Styrning som upprätthålls vid delning av segment</li></ul> |
| <ul><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM] och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><ul><li>[!DNL AAM] segment</li><li>Tredjepartssegment via [!DNL AAM]</li></ul><li>Personalisering på samma sida via Edge</li><ul><li>[!DNL RTCDP] segment</li><li>Styrning som upprätthålls vid delning av segment</li></ul> |

### Blandning av implementering av [!UICONTROL at.js] och [!DNL Platform Web SDK]

| Lösningar | Användningsfall aktiverat |
| --- | --- |
| <ul><li>[!DNL RTCDP] (valfri SKU) och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><ul><li>För alla sidor med [!UICONTROL at.js]</li></ul><li>Personalisering på samma sida</li><ul><li>För alla sidor med [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM] och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><ul><li>För alla sidor med [!UICONTROL at.js]</li><li>[!DNL AAM] segment</li><li>Tredjepartssegment via [!DNL AAM]</li></ul> |

## Utvärderingstid för segment

I följande tabell visas segmentutvärderingstiden för händelser som kommer från olika implementeringsscenarier:

| Scenario | Edge segment (millisekundutvärdering) | Strömningssegment (minututvärdering) | Utvärdering av batchsegment |
| --- | --- | --- | --- |
| Händelser/data från [!DNL Adobe Experience Platform] SDK:er | Ja | Ja | Ej tillämpligt |
| Händelser från [!UICONTROL at.js] | Nej | Ja | Ej tillämpligt |
| Händelser från [!DNL Target Mobile] SDK:er | Nej | Ja | Ej tillämpligt |
| Händelser från batchöverföring | Nej | Nej | Ja |
| Händelser från offlinedata (ström) | Nej | Ja | Ja |

## Använd målgrupper från [!DNL Adobe Experience Platform] {#aep}

Om du använder [målgrupper](/help/main/c-target/c-audiences/audiences.md) som skapats i [!DNL Adobe Experience Platform] får du mer omfattande kunddata som leder till mer slagkraftig personalisering. [Real-Time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=sv-SE){target=_blank} (RTCDP), som bygger på [!DNL Adobe Experience Platform], hjälper företag att samla in kända och anonyma data från flera olika företagskällor. Med den här processen kan ni skapa kundprofiler som kan användas för att leverera personaliserade kundupplevelser över alla kanaler och enheter i realtid.

Genom att ansluta [!DNL Target] till [!DNL Real-Time Customer Data Platform] kan kunderna berika sin webbpersonalisering. Med den här integreringen kan du låsa upp nya segment som tidigare inte var tillgängliga för [!DNL Target] för att aktivera millisekundanpassning i realtid på den första sidan av en kunds webbbesök. Genom att använda målgrupper och profilattribut som skapats i [!DNL Adobe Experience Platform] kan du utöka de tillgängliga datapunkterna för bättre personalisering.

Integreringen låser upp viktiga användningsexempel med Real-Time CDP:

* Personalisering med samma sida/nästa träff
* Personalisering av okända användare

## Dela Real-Time CDP-profilattribut med [!DNL Target] {#rtcdp-profile-attributes}

Real-Time CDP-profilattribut kan delas med [!DNL Target] för användning i HTML-erbjudanden och [JSON-erbjudanden](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Begränsningar och överväganden för Real-Time CDP-profilattribut {#limitations}

Tänk på följande:

* Attribut inom ett visst erbjudande måste komma från samma [!UICONTROL Experience Platform]-sandlåda. (Erbjudandet kan med andra ord inte innehålla attribut från olika [!UICONTROL Experience Platform]-sandlådor.)
* Attribut inom ett visst erbjudande kan komma från olika källor, nämligen [!DNL Target]-profilen och [!UICONTROL Experience Platform]-profilen. (Du kan med andra ord kombinera attribut oavsett om de kommer från [!DNL Target] eller från profilen [!UICONTROL Experience Platform].)
* När du definierar ett erbjudande kan du tilldela standardvärden för [!UICONTROL Real-Time CDP Profile Attributes] om attributet inte har ett explicit värde. Om till exempel ett medgivande eller en styrningsprincip blockerar attributet som används i personaliseringstjänsten, kan standardvärdet användas i stället.
* [!DNL Target] stöder bara datatypen &quot;string&quot; för profilattribut för [!DNL Adobe Experience Platform] som ska användas i erbjudanden. Attributen för typerna &quot;Map&quot; och &quot;Array&quot; stöds ännu inte.

### JSON-exempel

Som onlinemarkör vill du att AEP/Unified Profile ska dela attributvärden med [!DNL Target] för att tillhandahålla personalisering i realtid. Genom att använda [!UICONTROL Real-Time CDP Profile Attributes] kan du visa värdet för attributet [!UICONTROL Experience Platform] i ett [!DNL Target]-erbjudande med tokenersättning. Du kan till exempel anpassa efter en kunds favoritfärg med hjälp av `${aep.profile.favoriteColor}` eller deras lojalitetsnivå och lojalitetspunktsvärde med hjälp av token `${aep.loyalty.tier}` och `${aep.loyalty.points}`.

Så här skapar du ett JSON-erbjudande om att dela AEP/Unified Profile-attribut med [!DNL Target]:

1. Välj [&#x200B; i listan &#x200B;](/help/main/c-experiences/c-manage-content/create-json-offer.md) när du **[!UICONTROL Select a source]** skapar ett JSON-erbjudande **[!UICONTROL Adobe Experience Platform]**.
1. Välj önskad sandlåda i listan **[!UICONTROL Select a profile sandbox name]**.
1. Välj önskade attribut i listan **[!UICONTROL Select a profile attribute]**.
1. (Valfritt) Välj önskade värden i listan **[!UICONTROL Insert a default value]**.
1. Klicka på **[!UICONTROL Add]**.

Följande bild visar att två profilattribut: `loyalty.tier` och `loyalty.points` har lagts till i JSON-erbjudandet.

![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Länkar till mer information

Mer information finns i följande avsnitt:

* [Destinationsversionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE#destinations){target=_blank} i *Adobe Experience Platform versionsinformation*
* [Konfigurera anpassningsmål för samma sida och nästa sida-anpassning](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=sv-SE){target=_blank} i guiden *Destinationsöversikt*.
* [Adobe Target-anslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html?lang=sv-SE){target=_blank} i guiden *Destinationsöversikt*
* [Mappa attribut](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=sv-SE#map-attributes){target=_blank} i guiden *Målöversikt*.
* [Aktivera målgrupper för kantanpassningsmål](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.html?lang=sv-SE){target=_blank} i guiden *Målöversikt*.
* [Anpassa samma sida och nästa sida via  [!DNL Adobe Target] och anpassade Personalization-mål](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=sv-SE#same-next-page-personalization){target=_blank} under Vanliga frågor och svar i guiden *Översikt över destinationer*.

## Videor och blogginlägg {#videos-blogs}

I följande videofilmer och blogginlägg finns mer information om förbättrad personalisering med Target och RTCDP:

### Video: Nästa träffad personalisering med Real-Time CDP och [!DNL Adobe Target]{#RTCDP}

Lär dig hur du kan personalisera nästa träff med [!DNL Real-Time Customer Data Platform] och [!DNL Adobe Target]. Med [!DNL Adobe Target]-destinationen i [!DNL Real-Time CDP] kan du använda [!DNL Experience Platform]-segment i [!DNL Adobe Target] för samma sidanpassning och nästa sidanpassning med stöd för styrning och sekretess.

Mer information finns i [Nästa-träffs-personalisering med Real-Time CDP och Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=sv-SE){target=_blank} i handboken *Platform Tutorials*.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Video: Konfigurera [!DNL Adobe Target]-målet i [!DNL Real-Time Customer Data Platform]

Lär dig hur du konfigurerar [!DNL Adobe Target]-målet i [!DNL Real-Time Customer Data Platform] så att du kan börja skicka segment och profilattribut från [!DNL Real-Time CDP] till [!DNL Target].

>[!VIDEO](https://video.tv.adobe.com/v/3449797/?learn=on&captions=swe)

### Video: Aktivera segment och profilattribut

Lär dig hur du aktiverar segment och profilattribut från [!DNL Adobe Real-Time Customer Data Platform] till [!DNL Adobe Target] för att visa personaliserat innehåll i realtid på dina webbplatser, mobilappar och andra digitala egenskaper.

>[!VIDEO](https://video.tv.adobe.com/v/3447359/?learn=on&captions=swe)

### Video: Använd [!DNL Real-Time CDP] segment i [!DNL Target]

Lär dig hur du använder [!DNL Real-Time Customer Data Platform] segment i [!DNL Adobe Target] för att leverera personaliserade upplevelser på din webbplats och i dina mobilappar.

>[!VIDEO](https://video.tv.adobe.com/v/3446831/?learn=on&captions=swe)

### Video: Använd [!DNL Real-Time CDP]-profilattribut i [!DNL Adobe Target]

Lär dig hur du använder [!DNL Adobe Real-Time Customer Data Platform]-profilattribut i [!DNL Adobe Target] för att leverera personaliserade upplevelser på din webbplats och i dina mobilappar.

>[!VIDEO](https://video.tv.adobe.com/v/3451897/?learn=on&captions=swe)

### [!DNL Adobe Target] blogg och video: Förbättrad personalisering för samma sida

[[!DNL Adobe] presenterar Personalization (samma sida) med  [!DNL Adobe Target] och [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
