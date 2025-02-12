---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 35699792dac84c93775aab9dde46d62c988e2838
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 12 februari 2025**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## Target Standard/Premium 25.2.1 (12 februari 2025)

Den här versionen innehåller följande uppdateringar:

* [!UICONTROL Activities] uppdatering av användargränssnittet
* [!DNL Recommendations] uppdatering av användargränssnittet

### [!UICONTROL Activities] uppdatering av användargränssnittet

I takt med att moderniseringen av användargränssnittet i [!DNL Adobe Target] fortsätter är vi glada att kunna meddela att det uppdaterade [!UICONTROL Activities]-användargränssnittet är allmänt tillgängligt.

>[!NOTE]
>
>Från och med den 12 februari får kunderna gradvis tillgång till det nya [!UICONTROL Activities]-gränssnittet. För att säkerställa en sömlös driftsättning för alla kunder kommer den här versionen att distribueras i kontrollerade faser. I det första steget uppgraderas den första gruppen med [!DNL Target] kunder till det nya [!UICONTROL Activities]-gränssnittet. Efterföljande steg kommer att uppgradera de återstående kunderna.

Uppdateringen är baserad på det senaste [!DNL Adobe Spectrum]-designsystemet och standardiserar tidigare inkonsekventa designmönster, samtidigt som nya förbättringar läggs till, till exempel:

* [Omdesignad rapportering](/help/main/administrating-target/reporting.md) för bättre insikter i aktivitetsresultat
* [[!UICONTROL Updated Change Log]](/help/main/c-activities/change-log.md)-sidan hämtar nu information från [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} för realtidsinsikter
* [Anpassningsbara listvyer](/help/main/c-activities/activities.md) för bättre flexibilitet i olika teambehov
* [Förbättrade snabbinformations- och detaljskärmar](/help/main/c-activities/activities.md) för enklare åtkomst till information
* [Alternativ för beständig sökning och filtrering](/help/main/c-activities/activities.md)
* Fullt [har omskapats [!UICONTROL Visual Editing Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) med stöd för de senaste säkerhetsuppdateringarna från webbläsarproviders och ett modernt användargränssnitt

  Mer information om hur den uppdaterade VEC skiljer sig från den tidigare versionen finns i [Ändringar i Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)

* [Uppdaterat [!DNL Chrome] tillägg](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) som stöder manifest V3 för ökad säkerhet och förbättrat stöd för cookies från första part

![Aktivitetsuppdatering](/help/main/r-release-notes/assets/activities-refresh.png)

### [!DNL Recommendations] uppdatering av användargränssnittet

I takt med att moderniseringen av användargränssnittet i [!DNL Adobe Target] fortsätter är vi glada att kunna meddela att det uppdaterade [!DNL Recommendations]-användargränssnittet är allmänt tillgängligt.

>[!NOTE]
>
>Från och med den 12 februari får kunderna gradvis tillgång till det nya [!UICONTROL Recommendations]-gränssnittet. För att säkerställa en sömlös driftsättning för alla kunder kommer den här versionen att distribueras i kontrollerade faser. I det första steget uppgraderas den första gruppen med [!DNL Target] kunder till det nya [!UICONTROL Activities]-gränssnittet. Efterföljande steg kommer att uppgradera de återstående kunderna.

Uppdateringen är baserad på det senaste [!DNL Adobe Spectrum]-designsystemet och standardiserar tidigare inkonsekventa designmönster, samtidigt som nya förbättringar läggs till, till exempel:

* [produktkatalogsökningen](/help/main/c-recommendations/c-products/catalog-search.md) innehåller nu en uppdaterad databas som tillåter synkronisering i realtid av produkter
* [!UICONTROL Recommendations] objekt ([!UICONTROL Criteria], [!UICONTROL Designs], [!UICONTROL Collections] och [!UICONTROL Exclusions]) [ som skapats över API är nu tillgängliga i gränssnittet ](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md)
* [Rekommendationsinställningar](/help/main/administrating-target/recommendations-settings.md) har konsoliderats under avsnittet [!UICONTROL Administration]
* Anpassningsbara listvyer för bättre flexibilitet i olika teambehov
* Uppdaterade HTML- och JSON-kodredigerare med [syntaxmarkering och radnumrering](/help/main/c-experiences/c-manage-content/create-json-offer.md)
* Förbättrad snabbinformation och detaljskärmar för enklare åtkomst till information
* Alternativ för beständig sökning och filtrering

![Uppdatering av gränssnittet Rekommendationer](/help/main/r-release-notes/assets/recs-ui-refresh.png)

## Target Standard/Premium 25.1.1 (9 januari 2025)

Den här versionen innehåller följande uppdateringar:

### [!UICONTROL Offers Library] uppdatering av användargränssnittet

För att förbättra användarupplevelsen för [!DNL Adobe Target]-användare uppdaterar den här versionen användargränssnittet för [!UICONTROL Offers Library].

>[!NOTE]
>
>För att säkerställa en sömlös driftsättning för alla kunder kommer den här versionen att distribueras i kontrollerade faser. Den första fasen uppgraderade den första gruppen av Target-kunder till det nya gränssnittet för erbjudanden. Efterföljande steg kommer att uppgradera de återstående kunderna.

Med det senaste [!DNL Adobe Spectrum]-designsystemet standardiserar den här uppdateringen inkonsekventa designmönster och introducerar nya förbättringar, bland annat följande:

* **Hantering av masserbjudanden**: Markera och ta bort eller flytta flera erbjudanden samtidigt.

* **[!UICONTROL Code Editor]uppgraderingar**: Uppdaterade HTML- och JSON-redigerare med syntaxmarkering och radnumrering.

* **Förbättrade kort för erbjudanden**: Förbättrade kort för snabb information och detaljer för enklare åtkomst till information.

* **Beständig sökning och filter**: Lägger till alternativ för beständig sökning och filtrering för sessioner.

Mer information finns i [Erbjudanden](/help/main/c-experiences/c-manage-content/manage-content.md) och underartiklarna i det här avsnittet.

Här är ett kort videoklipp som visar förändringarna i den här versionen:

![Erbjuder gränssnittsuppdateringsvideo](/help/main/r-release-notes/assets/offers-video-v2.gif)

## [!DNL Adobe Experience Platform Web SDK] `__view__` scopeoptimering (22 oktober 2024)

Mellan den 22 juli 2024 och den 15 augusti 2024 optimerade [!DNL Target]-teamet `__view__`-omfattningen och ökade noggrannheten för aktivitetsindikering, besök och besökarrapportering. Optimeringen syftar till att automatiskt samla in rapporteringsdata för automatiskt återgivna annonser och bör vara genomskinlig för de flesta konton.

Den här optimeringen kommer att vara aktiverad för alla nya [!DNL Adobe Experience Platform Web SDK]-kunder. Optimeringen har dock inaktiverats för kunder som migrerat från at.js och inte följt implementeringsstegen nedan. Vi uppmanar dessa kunder att granska sina implementeringar senast den 3 februari 2025. Efter detta datum kommer vi att aktivera optimering för alla kunder. Underlåtenhet att granska och justera implementeringar innan dess kan påverka rapporter, vilket anges nedan. Kontakta [!DNL Adobe Customer Care] om du behöver bekräfta om implementeringen påverkas eller om du behöver mer tid för att justera implementeringen.

>[!IMPORTANT]
>
>Om du inte kan slutföra implementeringsgranskningen och åtgärda eventuella problem före 3 februari 2025 kan du begära en förlängning på en gång i sex månader. Se till att din ansökan har skickats in senast den 31 januari 2025. Adobe granskar och fattar beslut om din ansökan.

Om du vill dra nytta av den här optimeringen vid manuell förslagsåtergivning granskar du [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} för att kontrollera att du skickar meddelanden efter manuell återgivning eller när du använder metoden `applyPropositions` (eller motsvarande [!DNL Launch]-åtgärd som en hjälpreda) för att återge upplevelser.

De vanligaste scenarierna när upplevelser återges manuellt är:

* Använda JSON-erbjudanden
* Använda ett anpassat beslutsområde i en aktivitet som skapats i [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)
* Använder inte `renderDecisions: true` vid hämtning av en aktivitet som skapats med [!UICONTROL Form-Based Experience Composer] som använder det globala `__view__`-omfånget

Om meddelanden inte implementeras enligt [Återge anpassat innehåll](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} i guiden *Datainsamling* kan rapportdata saknas i [!DNL Target] och i [Analytics for Target reporting](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). I vissa scenarier kanske du märker en felaktig trafikdelning eftersom rapportdata inte hämtas. Eller, i andra scenarier, rapportera samma händelse upprepade gånger.

Beroende på implementeringen kan du kontrollera om [!DNL Analytics] och A4T har någon inverkan på rapporteringen.

[!DNL Platform Web SDK] har stöd för två implementeringstyper för återgivning av upplevelser och personaliseringar:

* **Ett samtal för personalisering och mätning.**

  Inledningsvis rekommenderades att metoden med ett anrop för [!DNL Platform Web SDK] är inaktuell till förmån för metoden med delat anrop. Adobe rekommenderar alla nya implementeringar att använda den nya metoden för delad anrop och rekommenderar att befintliga kunder också övergår till metoden delad anrop.

  Om du fortsätter att använda metoden med ett samtal kan du se följande oväntade ändringar i dina [!DNL Analytics]-rapporter:

   * En nedgång i studsar.
   * A4T och [!UICONTROL Page View] träffar inte ihop, vilket gör det svårt att utföra vissa indelningar och korrelationer i A4T-rapporter med hjälp av [!DNL Analytics] eVars och events.

* **Dela anrop (kallas även för sidans övre och nedre del).**

  Den här implementeringstypen är den nya [implementeringsmetoden för delat anrop](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} som rekommenderas av [!DNL Adobe]. Med den här metoden påverkar inte den nya optimeringen [!DNL Analytics]- eller A4T-rapporter.

Kontakta [Adobe kundtjänst](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C) om du har frågor. (KB-2179)

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
