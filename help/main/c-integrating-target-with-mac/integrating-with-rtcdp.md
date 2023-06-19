---
keywords: Real-time Customer Data Platform;rtcdp;personalisering;målgrupper;adobe experience platform audiences;profile attributes
description: Lär dig använda [!DNL Target]/[!DNL Real-Time Customer Data Platform] (RTCDP)-integrering för att ge mer omfattande kunddata och mer slagkraftig personalisering.
title: Hur integrerar jag? [!DNL Target] med [!DNL Real-Time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: fedef4bfa5fdcc757dc1bd5e0d3577a85896c918
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 0%

---

# Integrera med [!DNL Real-Time Customer Data Platform]

Inbyggt [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP) hjälper företag att samla in kända och anonyma uppgifter från olika källor. Med RTCDP kan ni skapa kundprofiler som kan användas för att leverera personaliserade kundupplevelser över alla kanaler och enheter i realtid.

Mer information om RTCDP finns i [Real-time Customer Data Platform - översikt](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank}.

## Viktiga funktioner

Viktiga funktioner:

* Direkt [!DNL Target] integrering med Real-Time CDP/[!DNL Adobe Experience Platform] på kanten (tar bort beroendet av [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations Card] med styrning och policystyrning
* CDP-segment och attribut för delad profil i realtid

## Implementeringsscenarier

I följande avsnitt visas vilken typ av användningsfall för personalisering (nästa session eller samma sida) som är tillgänglig när olika implementeringsmetoder används:

### at.js-implementering

| Lösningar | Användningsfall aktiverat |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) och [!DNL Target]</li><li>[!DNL RTCDP] (Premium eller Ultimate) och [!DNL Target]</li><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM]och [!DNL Target]</li></ul> | Anpassa nästa session |

### [!DNL Adobe Experience Platform Web SDK] eller [!DNL Experience Platform Server-Side API] implementering

| Lösningar | Användningsfall aktiverat |
| --- | --- |
| <ul><li>[!DNL RTCDP] (valfri SKU) och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><li>Personalisering på samma sida via Edge</li><li>Styrning som upprätthålls vid delning av segment</li></ul> |
| <ul><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM]och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><ul><li>[!DNL AAM] segment</li><li>Tredjepartssegment via [!DNL AAM]</li></ul><li>Personalisering på samma sida via Edge</li><ul><li>[!DNL RTCDP] segment</li><li>Styrning som upprätthålls vid delning av segment</li></ul> |

### Blandning av [!UICONTROL at.js] och [!DNL Platform Web SDK] implementering

| Lösningar | Användningsfall aktiverat |
| --- | --- |
| <ul><li>[!DNL RTCDP] (valfri SKU) och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><ul><li>För alla sidor med [!UICONTROL at.js]</li></ul><li>Personalisering på samma sida</li><ul><li>För alla sidor med [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM]och [!DNL Target]</li></ul> | <ul><li>Anpassa nästa session</li><ul><li>För alla sidor med [!UICONTROL at.js]</li><li>[!DNL AAM] segment</li><li>Tredjepartssegment via [!DNL AAM]</li></ul> |

## Utvärderingstid för segment

I följande tabell visas segmentutvärderingstiden för händelser som kommer från olika implementeringsscenarier:

| Scenario | Kantsegment (millisekundutvärdering) | Strömningssegment (minututvärdering) | Utvärdering av batchsegment |
| --- | --- | --- | --- |
| Händelser/data från [!DNL Adobe Experience Platform] SDK | Ja | Ja | Ej tillämpligt |
| Händelser från [!UICONTROL at.js] | Nej | Ja | Ej tillämpligt |
| Händelser från [!DNL Target Mobile] SDK | Nej | Ja | Ej tillämpligt |
| Händelser från batchöverföring | Nej | Nej | Ja |
| Händelser från offlinedata (ström) | Nej | Ja | Ja |

## Använd målgrupper från [!DNL Adobe Experience Platform] {#aep}

Använda [målgrupper](/help/main/c-target/c-audiences/audiences.md) skapad i [!DNL Adobe Experience Platform] ge mer omfattande kunddata som leder till mer slagkraftig personalisering. The [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCDP), på [!DNL Adobe Experience Platform], hjälper företag att samla in kända och anonyma data från flera olika källor. Med den här processen kan ni skapa kundprofiler som kan användas för att leverera personaliserade kundupplevelser över alla kanaler och enheter i realtid.

Genom att ansluta [!DNL Target] till [!DNL Real-Time Customer Data Platform], kan kunderna förbättra sin webbpersonalisering. Tack vare den här integreringen kan du låsa upp nya segment som tidigare inte var tillgängliga för [!DNL Target] för att möjliggöra millisekundpersonalisering i realtid på första sidan av en kunds webbbesök. Använda målgrupper och profilattribut som skapats i [!DNL Adobe Experience Platform] gör att du kan utöka de tillgängliga datapunkterna för bättre personalisering.

Integreringen låser upp viktiga användningsexempel med Real-Time CDP:

* Personalisering med samma sida/nästa träff
* Personalisering av okända användare

## Dela Real-Time CDP-profilattribut med [!DNL Target] {#rtcdp-profile-attributes}

Real-Time CDP-profilattribut kan delas med [!DNL Target] för användning i HTML och [JSON erbjuder](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Begränsningar och överväganden för Real-Time CDP-profilattribut

Tänk på följande:

* Attribut inom ett visst erbjudande måste komma från samma [!UICONTROL Experience Platform] sandlåda. (Erbjudandet får med andra ord inte innehålla attribut från olika [!UICONTROL Experience Platform] sandlådor.)
* Attribut inom ett visst erbjudande kan komma från olika källor. det vill säga [!DNL Target] och [!UICONTROL Experience Platform] profil. (Du kan med andra ord kombinera attribut oavsett om de kommer från [!DNL Target] eller från [!UICONTROL Experience Platform] profil.)
* När du definierar ett erbjudande kan du tilldela standardvärden för [!UICONTROL Real-Time CDP Profile Attributes], om attributet inte har ett explicit värde. Om till exempel ett medgivande eller en styrningsprincip blockerar attributet som används i personaliseringstjänsten, kan standardvärdet användas i stället.

### JSON-exempel

Som onlinemarkör vill du att AEP/Unified Profile ska dela attributvärden med [!DNL Target] för personalisering i realtid. Genom att använda [!UICONTROL Real-Time CDP Profile Attributes]kan du visa värdet för [!UICONTROL Experience Platform] attribut i en [!DNL Target] Erbjudande med tokenersättning. Du kan till exempel anpassa efter kundens favoritfärg med `${aep.profile.favoriteColor}`eller deras lojalitetsnivå och förmånspoängvärde med hjälp av tokens `${aep.loyalty.tier}` och `${aep.loyalty.points}`.

Skapa ett JSON-erbjudande om att dela AEP/Unified Profile-attribut med [!DNL Target]:

1. while [skapa ett JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md), från **[!UICONTROL Select a source]** lista, välj **[!UICONTROL Adobe Experience Platform]**.
1. Från **[!UICONTROL Select a profile sandbox name]** väljer du önskad sandlåda.
1. Från **[!UICONTROL Select a profile attribute]** väljer du de attribut du vill använda.
1. (Valfritt) Från **[!UICONTROL Insert a default value]** väljer du önskade värden.
1. Klicka på **[!UICONTROL Add]**.

I följande bild visas två profilattribut: `loyalty.tier` och `loyalty.points` har lagts till i JSON-erbjudandet.

![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Länkar till mer information

Mer information finns i följande avsnitt:

* [Versionsinformation om destinationer](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} i *Versionsinformation för Adobe Experience Platform*
* [Konfigurera personaliseringsmål för personalisering på samma sida och nästa sida](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} i *Översikt över destinationer* guide.
* [Adobe Target-anslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} i *Översikt över destinationer* guide
* [Mappningsattribut](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=en#map-attributes){target=_blank} i *Översikt över destinationer* guide.
* [Aktivera målgrupper för att kanalisera personaliseringsmål](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.htm){target=_blank} i *Översikt över destinationer* guide.
* [Personalisering på samma sida och nästa sida via [!DNL Adobe Target] och anpassade destinationer för personalisering](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=en#same-next-page-personalization){target=_blank} under Vanliga frågor och svar i dialogrutan *Översikt över destinationer* guide.

## Videor och blogginlägg {#videos-blogs}

I följande videofilmer och blogginlägg finns mer information om förbättrad personalisering med Target och RTCDP:

### Video: Nästa steg i personaliseringen med Real-Time CDP och [!DNL Adobe Target]{#RTCDP}

Läs om hur ni personaliserar nästa träff med [!DNL Real-Time Customer Data Platform] och [!DNL Adobe Target]. The [!DNL Adobe Target] mål in [!DNL Real-Time CDP] låter dig använda [!DNL Experience Platform] segment i [!DNL Adobe Target] för samma sidpersonalisering och personalisering på nästa sida med stöd för styrning och integritet.

Mer information finns i [Nästa steg i personaliseringen med Real-Time CDP och Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} i *Platform Tutorials* guide.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Video: Konfigurera [!DNL Adobe Target] mål in [!DNL Real-Time Customer Data Platform]

Lär dig hur du konfigurerar [!DNL Adobe Target] mål in [!DNL Real-Time Customer Data Platform] för att börja skicka segment och profilattribut från [!DNL Real-Time CDP] till [!DNL Target].

>[!VIDEO](https://video.tv.adobe.com/v/3418799/?learn=on)

### Video: Aktivera segment och profilattribut

Lär dig hur du aktiverar segment och profilattribut från [!DNL Adobe Real-Time Customer Data Platform] till [!DNL Adobe Target] för att visa personaliserat innehåll i realtid på webbplatser, i mobilappar och andra digitala resurser.

>[!VIDEO](https://video.tv.adobe.com/v/3419036/?learn=on)

### Video: Använd [!DNL Real-Time CDP] segment i [!DNL Target]

Lär dig använda [!DNL Real-Time Customer Data Platform] segment i [!DNL Adobe Target] för att leverera personaliserade upplevelser på er webbplats och i era mobilappar.

>[!VIDEO](https://video.tv.adobe.com/v/3419149/?learn=on)

### Video: Använd [!DNL Real-Time CDP] profilattribut i [!DNL Adobe Target]

Lär dig använda [!DNL Adobe Real-Time Customer Data Platform] profilattribut i [!DNL Adobe Target] för att leverera personaliserade upplevelser på er webbplats och i era mobilappar.

>[!VIDEO](https://video.tv.adobe.com/v/3419318/?learn=on)

### [!DNL Adobe Target] blogg och video: Förbättrad personalisering på samma sida

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] och [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
