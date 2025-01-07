---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar,aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f3090ad7ab1c3d15de496039e76bb5ec0b02886f
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## [!UICONTROL Offers Library] uppdatering av användargränssnittet (9 januari 2025)

För att förbättra användarupplevelsen för [!DNL Adobe Target]-användare uppdaterar den här versionen användargränssnittet för [!UICONTROL Offers Library]. Med det senaste [!DNL Adobe Spectrum]-designsystemet standardiserar den här uppdateringen inkonsekventa designmönster och introducerar nya förbättringar, bland annat följande:

* **Hantering av masserbjudanden**: Markera och ta bort eller flytta flera erbjudanden samtidigt.

* **[!UICONTROL Code Editor]uppgraderingar**: Uppdaterade HTML- och JSON-redigerare med syntaxmarkering och radnumrering.

* **Förbättrade kort för erbjudanden**: Förbättrade kort för snabb information och detaljer för enklare åtkomst till information.

* **Beständig sökning och filter**: Lägger till alternativ för beständig sökning och filtrering för sessioner.

Från och med 9 januari 2025 får alla [!DNL Target]-kunder tillgång till det nya användargränssnittet, med möjlighet att vid behov växla tillbaka till den aktuella versionen av användargränssnittet.

Mer information finns i [Erbjudanden](/help/main/c-experiences/c-manage-content/manage-content.md) och underartiklarna i det här avsnittet.

Här är ett kort videoklipp som visar förändringarna i den här versionen:

![Erbjuder gränssnittsuppdateringsvideo](/help/main/r-release-notes/assets/offers-video-v2.gif)

## [!DNL Adobe Experience Platform Web SDK] `__view__` scopeoptimering (22 oktober 2024)

Mellan den 22 juli 2024 och den 15 augusti 2024 optimerade [!DNL Target]-teamet `__view__`-omfattningen och ökade noggrannheten för aktivitetsindikering, besök och besökarrapportering. Optimeringen syftar till att automatiskt samla in rapporteringsdata för automatiskt återgivna annonser och bör vara genomskinlig för de flesta konton.

Den här optimeringen kommer att vara aktiverad för alla nya [!DNL Adobe Experience Platform Web SDK]-kunder. Optimeringen har dock inaktiverats för kunder som migrerat från at.js och inte följt implementeringsstegen nedan. Vi uppmanar dessa kunder att granska sina implementeringar senast den 3 februari 2025. Efter detta datum kommer vi att aktivera optimering för alla kunder. Underlåtenhet att granska och justera implementeringar innan dess kan påverka rapporter, vilket anges nedan. Kontakta [!DNL Adobe Customer Care] om du behöver bekräfta om implementeringen påverkas eller om du behöver mer tid för att justera implementeringen.

>[!IMPORTANT]
>
>Om du inte kan slutföra implementeringsgranskningen och åtgärda eventuella problem före 3 februari 2025 kan du begära en förlängning på en gång i sex månader. Se till att din ansökan har skickats in senast den 31 januari 2025. Adobe granskar och fattar beslut om din begäran.

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

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Produktuppdatering för Adobe Prioritet](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
