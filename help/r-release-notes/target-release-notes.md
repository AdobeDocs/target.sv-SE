---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL Adobe Target-versionerna.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 6ca8aa18c8b9deca1345f09db3a1f85b13840c28
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---


# Versionsinformation för mål (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 5 augusti 2020**

Information om den aktuella versionen finns i [Versionsinformation](release-notes.md)för mål. Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!IMPORTANT]
>
>* **Adobe igen utsedd till ledare i Gartners Magic Quadrant for Personalization Engines**: Adobe utnämndes ännu en gång till ledare i den tredje årsrapporten Gartner Magic Quadrant for Personalization Engines, 2020. Gartner Magic Quadrant for Personalization Engines utvärderade leverantörer i 15 olika kategorier: fullständighet i synen och förmågan att genomföra. [Läs om det på Adobe-bloggen](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **borttagning** av mbox.js: 30 augusti 2020 stöder inte Adobe Target längre mbox.js-biblioteket. Efter den 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKomplett Builder: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig från Adobe.
   >
   >
* **Målmeddelanden**: På sidan med målmeddelanden hittar du information om kommande evenemang, bland annat om sessioner i Target SKill Builder, chats för utvecklare, webbinarier och sessioner med Target Coffee Break. Mer information finns i [Målmeddelanden](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.9.1 (2 september 2020)

Målversionen innehåller följande nya funktioner eller förbättringar:

| Funktion/förbättring | Beskrivning |
| --- | --- |
| Analyser för Target-stöd (A4T) för [!UICONTROL Auto-Target] aktiviteter | [!UICONTROL Auto-Target] aktiviteter kommer att stödja [!UICONTROL Analytics for Target] (A4T).<br>Tack vare den här integreringen kan ni använda den [!UICONTROL Auto-Target] avancerade maskininlärningen för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar, samtidigt som ni använder [!UICONTROL Adobe Analytics] målvärden och/eller [!DNL Adobe Analytics] rapporterings- och analysfunktioner. [!UICONTROL Auto-Target] levererar den mest skräddarsydda upplevelsen till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler.<br>Om du redan har [implementerat A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) för användning med [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate]och [!UICONTROL Experience Targeting] aktiviteter är allt klart! |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
