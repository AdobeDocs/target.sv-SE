---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: cc0bf794e366f304b52db309d4e3a66292d7ea32
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 27 augusti 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Informationen i den här artikeln uppdateras ofta, särskilt före releaser.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.8.4 (1 september 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**[!UICONTROL Activities]**

+++Se detaljer
* **Kunder kunde inte kopiera aktivitets- eller dokumentnamn från[!UICONTROL Activity Overview]**: Tidigare kunde kunderna inte kopiera namnet på en aktivitet eller det associerade erbjudandet/dokumentet direkt från [!UICONTROL Activity Overview] i den uppdaterade processen för att skapa aktiviteter. Den här begränsningen påverkar användbarheten, särskilt på mindre skärmar. Kunderna kan nu enkelt kopiera både aktivitets- och dokumentnamn utan temporära lösningar. (TGT-51850)
* **Proaktiv inmatning av förvaltade [!DNL Target] kunddata när aktiviteter skapades**: Förbättrade processen för att skapa aktivitet genom att aktivera proaktiv insamling av rapporter, innehåll och skärmbilder från [!DNL Target]-kunder. Den här förbättringen åtgärdar luckor i data som identifierats i befintliga användningsfall och hjälper till att få exaktare insikter under aktiviteten och experimentera med inställningarna. (TGT-52415)

+++

**[!UICONTROL Recommendations]**

+++Se detaljer
* **Produktlistan var inte synlig i dialogrutan [!UICONTROL View Collection]:** Tidigare kunde kunderna inte se produktlistan när de visade en samling på fliken [!UICONTROL Recommendations]. Dialogrutan [!UICONTROL View Collection] visar nu de associerade produkterna korrekt, vilket förbättrar genomskinlighet och användbarhet i det uppdaterade gränssnittet för rekommendationer. (TGT-50531)
* **Korrigerade ett problem som orsakade skiftlägeskänslig filtrering i [!UICONTROL Product Catalog Search] avancerad sökning**: Den avancerade sökfiltreringen på [!UICONTROL Product Catalog Search]-sidan ignorerar nu skiftlägeskänslighet, vilket överensstämmer med beteendet hos både backend- och GraphQL-tjänster. Denna uppdatering ger enhetliga och korrekta förslagsresultat för kunder oavsett textindrag. (TGT-53585)

+++

**[!UICONTROL Reports]**

+++Se detaljer
* **Rapporterna kunde inte läsas in för målgruppen på skrivbordet på grund av ett ogiltigt målgruppsnamnfel**: Kunderna påträffade ett GraphQL-fel när de försökte visa rapporter för en målgrupp i processen att skapa aktiviteter. Systemet returnerade meddelandet&quot;Ogiltigt målgruppsnamn: XXXXX&quot;, vilket förhindrar åtkomst till rapportdata. Rapporterna läses nu in korrekt för datormålgruppen. (TGT-53371)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Se detaljer
* **Det gick inte att klicka på Acceptera cookies med [!UICONTROL Enhanced Experience Composer] (EEC) eftersom en funktion saknas**: Kunder rapporterade att försök att acceptera cookies via EEC resulterade i ett konsolfel: `handleclickAcceptAllButton is not defined`. Funktionen för godkännande av cookies fungerar nu som förväntat och ger en smidigare upplevelse när aktiviteter skapas i det uppdaterade användargränssnittet. (TGT-52794)
* **Det nya EEG-gränssnittet kunde inte läsa in vissa sidor som tidigare hade stöd i det gamla användargränssnittet**: Kunder rapporterade att det nya EEG-gränssnittet inte kunde läsa in vissa sidor som var tillgängliga i det gamla användargränssnittet trots att det fanns kod för iframe-busting på webbplatsen. Den uppdaterade processen för att skapa aktivitet har nu stöd för inläsning av dessa sidor och återställer kompatibilitet för arbetsflöden som skapar aktiviteter. (TGT-53061)
* **VEC visade en tom vita skärm när upplevelser redigerades**: Kunder från en viss klientorganisation rapporterade att VEC-skärmen blev tom när de försökte redigera upplevelser i den uppdaterade VEC-webbplatsen. Problemet påverkade både nyskapade och äldre aktiviteter och förhindrar kontinuitet i arbetsflödet. VEC läses nu in korrekt, vilket gör att kunderna kan redigera upplevelser utan avbrott. (TGT-53547)
* **VEC kraschade och visade en tom skärm vid inläsning av vissa aktiviteter**: Kunder från en viss klientorganisation rapporterade att VEC inte kunde läsa in specifika aktiviteter. Experience Editor fastnade fortfarande i&quot;Använda initiala ändringar&quot; innan det kraschade och en tom skärm visades. Konsolfel indikerade ett fel vid läsning av odefinierade egenskaper. Redigeraren läser nu in de aktiviteter som påverkas utan fel i den uppdaterade VEC:n. (TGT-53548)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
