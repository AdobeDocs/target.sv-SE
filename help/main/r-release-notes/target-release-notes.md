---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: a708699926bd6cc89adc5c72d88be1ca4f0f0495
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 22 oktober 2024**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Adobe Experience Platform Web SDK] `__view__` scopeoptimering (22 oktober 2024)

Mellan den 22 juli 2024 och den 15 augusti 2024 optimerade [!DNL Target]-teamet `__view__`-omfattningen och ökade noggrannheten för aktivitetsindikering, besök och besökarrapportering. Optimeringen syftar till att automatiskt samla in rapporteringsdata för automatiskt återgivna annonser och bör vara genomskinlig för de flesta konton.

Den här optimeringen kommer att vara aktiverad för alla nya [!DNL Adobe Experience Platform Web SDK]-kunder. Optimeringen har dock inaktiverats för kunder som migrerat från at.js och inte följt implementeringsstegen nedan. Vi uppmanar dessa kunder att granska sina implementeringar senast den 3 februari 2025. Efter detta datum kommer vi att aktivera optimering för alla kunder. Underlåtenhet att granska och justera implementeringar innan dess kan påverka rapporter, vilket anges nedan. Kontakta [!DNL Adobe Customer Care] om du behöver bekräfta om implementeringen påverkas eller om du behöver mer tid för att justera implementeringen.

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

## [!DNL Target Standard/Premium] 24.10.2 (21 oktober 2024)

Den här versionen innehåller följande korrigeringar:

* Ett problem som förhindrade [!UICONTROL Recommendations] aktiviteter från att läsas in i [!UICONTROL Compose]- och [!UICONTROL Browse]-lägen har korrigerats. (TGT-50709)
* Ett problem med det nya [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper]-tillägget ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) som orsakade en omdirigering från [!UICONTROL Visual Experience Composer] (VEC) till [!UICONTROL Activities Library] har korrigerats efter att du klickat på Avbryt. Före den här korrigeringen behövde kunderna uppdatera [!UICONTROL Activities Library] innan de kunde skapa nya aktiviteter. (TGT-49980)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
