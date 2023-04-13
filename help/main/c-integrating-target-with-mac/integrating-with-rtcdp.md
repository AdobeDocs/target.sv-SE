---
keywords: Real-time Customer Data Platform;rtcdp;personalisering;målgrupper;adobe experience platform audiences;profile attributes
description: Lär dig använda [!DNL Target]/[!DNL Real-time Customer Data Platform] (RTCDP)-integrering för att ge mer omfattande kunddata och mer slagkraftig personalisering.
title: Hur integrerar jag? [!DNL Target] med [!DNL Real-time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: c14365b6d3296ab09d599ecb33239470a857efce
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 0%

---

# Integrera med Real-time Customer Data Platform

Inbyggt [!DNL Adobe Experience Platform], [!DNL Real-time Customer Data Platform] (RTCDP) hjälper företag att samla in kända och anonyma data från flera olika företagskällor för att skapa kundprofiler som kan användas för att leverera personaliserade kundupplevelser i alla kanaler och enheter i realtid.

Mer information om RTCDP finns i [Real-time Customer Data Platform - översikt](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank}.

## Använd målgrupper från [!DNL Adobe Experience Platform] {#aep}

Använda [målgrupper](/help/main/c-target/c-audiences/audiences.md) skapad i [!DNL Adobe Experience Platform] ge mer omfattande kunddata som leder till mer slagkraftig personalisering. The [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCDP), på [!DNL Adobe Experience Platform], hjälper företag att samla in kända och anonyma data från flera olika källor. Med den här processen kan ni skapa kundprofiler som kan användas för att leverera personaliserade kundupplevelser över alla kanaler och enheter i realtid.

Genom att ansluta [!DNL Target] till [!DNL Real-time Customer Data Platform]kan kunderna förbättra sin webbpersonalisering genom att låsa upp nya segment som tidigare inte var tillgängliga för [!DNL Target] för att möjliggöra millisekundpersonalisering i realtid på första sidan av en kunds webbbesök. Använda målgrupper och profilattribut som skapats i [!DNL Adobe Experience Platform] gör att du kan utöka de tillgängliga datapunkterna för bättre personalisering.

Denna integrering låser upp viktiga användningsfall med CDP i realtid:

* Personalisering med samma sida/nästa träff
* Personalisering av okända användare

### Viktiga funktioner

Viktiga funktioner:

* Direkt [!DNL Target] integrering med CDP i realtid/[!DNL Adobe Experience Platform] på kanten (tar bort beroendet av [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations Card] med styrning och policystyrning
* CDP-segment och attribut för delad profil i realtid

### CDP-profilattribut i realtid har begränsningar och överväganden

Tänk på följande:

* Attribut inom ett visst erbjudande måste komma från samma AEP-sandlåda. (Erbjudandet får med andra ord inte innehålla attribut från olika AEP-sandlådor.)
* Attribut inom ett visst erbjudande kan komma från olika källor. det vill säga [!DNL Target] och AEP-profilen. (Du kan med andra ord kombinera attribut oavsett om de kommer från [!DNL Target] eller från AEP-profilen.)
* När du definierar ett erbjudande kan du tilldela standardvärden för CDP-profilattribut i realtid om attributet inte har ett explicit värde. Om till exempel ett medgivande eller en styrningsprincip blockerar attributet som används i personaliseringstjänsten, kan standardvärdet användas i stället.
* När CDP-profilattribut för realtid delas används de i personaliseringsmodellerna Artificial Intelligence/Machine Learning för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] verksamhet.

>[!NOTE]
>
>Funktionen CDP-profilattribut i realtid är för närvarande tillgänglig i betaversioner för HTML och [JSON-erbjudanden](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Länkar till mer information

Mer information finns i följande avsnitt:

* [Versionsinformation om destinationer](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} i *Versionsinformation för Adobe Experience Platform*
* [Konfigurera personaliseringsmål för personalisering på samma sida och nästa sida](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} i *Översikt över destinationer* guide.
* [Anpassad personaliseringsanslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} i *Översikt över destinationer* guide
* [Adobe Target-anslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} i *Översikt över destinationer* guide
* [Konfigurera anpassningsmål för användning av samma sida och nästa sida](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} i *Översikt över destinationer* guide

### Användningsexempel för personalisering

Tabellen nedan visar vilka typer av användningsfall för personalisering (nästa session eller samma sida) som är tillgängliga när du använder [!DNL Adobe Experience Platform Web SDK] jämfört med att använda at.js:

| Implementering | Lösningar/användningsfall aktiverat |
| --- | --- |
| at.js | **Lösningar**:<ul><li>[!DNL Adobe Audience Manager] (AAM) och [!DNL Target]</li><li>[!DNL RTCDP] (Premium eller Ultimate) och [!DNL Target]</li><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM]och [!DNL Target]</li></ul>**Användningsfall**:<ul><li>Anpassa nästa session</li></ul> |
| [!DNL Platform Web SDK] eller [!DNL AEP Server-Side API] | **Lösningar**:<ul><li>[!DNL RTCDP] (valfri SKU) och [!DNL Target]</li></ul>**Använd skiftläge**:<ul><li>Anpassa nästa session</li><li>Personalisering på samma sida via Edge</li><li>Styrning som upprätthålls vid delning av segment</li></ul>**Lösningar**:<ul><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM]och [!DNL Target]</li></ul>**Använd skiftläge**:<ul><li>Anpassa nästa session</li><ul><li>[!DNL AAM] segment</li><li>Tredjepartssegment via [!DNL AAM]</li></ul><li>Personalisering på samma sida via Edge</li><ul><li>[!DNL RTCDP] segment</li><li>Styrning som upprätthålls vid delning av segment</li></ul> |
| Blandning av [!UICONTROL at.js] och [!DNL Platform Web SDK] | **Lösningar**:<ul><li>[!DNL RTCDP] (valfri SKU) och [!DNL Target]</li></ul>**Använd skiftläge**:<ul><li>Anpassa nästa session</li><ul><li>För alla sidor med [!UICONTROL at.js]</li></ul><li>Personalisering på samma sida</li><ul><li>För alla sidor med [!DNL Platform Web SDK]</li></ul></ul>**Lösningar**:<ul><li>[!DNL RTCDP] (valfri SKU), [!DNL AAM]och [!DNL Target]</li></ul>**Använd skiftläge**:<ul><li>Anpassa nästa session</li><ul><li>För alla sidor med [!UICONTROL at.js]</li><li>[!DNL AAM] segment</li><li>Tredjepartssegment via [!DNL AAM]</li></ul> |

### Utvärderingstid för segment

I följande tabell visas segmentutvärderingstiden för händelser som kommer från olika implementeringsscenarier:

| Scenario | Kantsegment (millisekundutvärdering) | Strömningssegment (minututvärdering) | Utvärdering av batchsegment |
| --- | --- | --- | --- |
| Händelser/data från [!DNL Adobe Experience Platform] SDK | Ja | Ja | Ej tillämpligt |
| Händelser från [!UICONTROL at.js] | Nej | Ja | Ej tillämpligt |
| Händelser från [!DNL Target Mobile] SDK | Nej | Ja | Ej tillämpligt |
| Händelser från batchöverföring | Nej | Nej | Ja |
| Händelser från offlinedata (ström) | Nej | Ja | Ja |

## Dela CDP-profilattribut i realtid med [!DNL Target] {#rtcdp-profile-attributes}

CDP-profilattribut i realtid kan delas med [!DNL Target] för användning i HTML och [JSON erbjuder](/help/main/c-experiences/c-manage-content/create-json-offer.md). (Observera att den här funktionen för närvarande är i betaversionen.)

Exempel: Som onlinemarkör vill du att AEP/Unified Profile ska dela attributvärden med [!DNL Target] för att tillhandahålla personalisering i realtid. Med CDP-profilattribut i realtid kan du visa AEP-attributets värde i en [!DNL Target] Erbjudande med tokenersättning. Du kan till exempel anpassa efter kundens favoritfärg med `${aep.profile.favoriteColor}`eller deras lojalitetsnivå och förmånspoängvärde med hjälp av tokens `${aep.loyalty.tier}` och `${aep.loyalty.points}`.

![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

Observera att det är valfritt att tilldela standardvärden.

## Videor och blogginlägg

I följande videofilmer och blogginlägg finns mer information om förbättrad personalisering med Target och RTCDP:

### Video: Nästa steg i personaliseringen med CDP och [!DNL Adobe Target]{#RTCDP}

Läs om hur ni personaliserar nästa träff med [!DNL Real-time Customer Data Platform] och [!DNL Adobe Target]. The [!DNL Adobe Target] mål in [!DNL Real-time CDP] låter dig använda [!DNL Experience Platform] segment i [!DNL Adobe Target] för samma sidpersonalisering och personalisering på nästa sida med stöd för styrning och integritet.

Mer information finns i [Nästa steg i personaliseringen med CDP och Adobe Target i realtid](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} i *Platform Tutorials* guide.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Adobe Target blogg och video:

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] och [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
