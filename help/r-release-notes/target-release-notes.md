---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL Adobe Target-versionerna.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 058828bbf3f13704d9e941563b7dab5259be6809
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Versionsinformation för Target (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 23 juni 2020**

Information om den aktuella versionen finns i [Target Versionsinformation](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!NOTE]
>
>* **borttagning** av mbox.js: Den 30 augusti 2020 stöder inte Adobe Target längre mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.
   >
   >
* **Target-meddelanden**: På Target webbplats för information om kommande evenemang, som sessioner med Target SKill Builder, chats för utvecklare, webbinarier och Target Coffee Break. Mer information finns i [Target-meddelanden](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.6.1 (juli 2020, exakt datum TBD)

Den här versionen innehåller följande förbättringar:

### Stöd för aktiviteter i Analytics for Target (A4T) [!UICONTROL Auto-Target]

[!UICONTROL Auto-Target] nu stöder [Analytics för Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

Denna integrering använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar. Auto-Target levererar den mest skräddarsydda upplevelsen till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler.

Om du redan har [implementerat A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) för A/B Test-aktiviteter är allt klart!

### [!UICONTROL Administration] gränssnittsuppdatering för avsnitt

Vi har uppdaterat [!UICONTROL Administration] avsnittet (tidigare [!UICONTROL Admin]) och dess sidor för att göra arbetsflödena enklare och effektivare.

Högdagrarna är:

* **[!UICONTROL Visual Experience Composer]sida **: Med den här nya sidan (**[!UICONTROL Administration]**>**[!UICONTROL Visual Experience Composer]**) kan du:

   * Konfigurera allmänna inställningar för VEC (ange standard-URL, aktivera [!UICONTROL Enhanced Experience Composer], läsa in blandat innehåll och generera ögonblicksbilder av upplevelser i aktivitetsflödesdiagrammet)
   * Konfigurera mobila visningsportar
   * Konfigurera CSS-väljare

* **[!UICONTROL Reporting]sida **: På den här nya sidan (**[!UICONTROL Administration]**>**[!UICONTROL Reporting]**) kan du konfigurera allmänna inställningar för[!DNL Target]rapportering som gäller för hela ditt[!DNL Target]konto.

   Tillgängliga inställningar:

   * Den [!DNL Adobe Experience Cloud] lösning som ska användas för rapportering
   * Tidszonen som ska användas för rapportering
   * Valutan som ska användas för rapportering
   * IP-adresser som ska uteslutas från rapportering
   * Anger om en uppskattad ökning av intäkterna ska visas vid rapportering
   * Om finjusterade prioriteringar ska aktiveras

* Den föregående [!UICONTROL Hosts] sidan har delats upp i två nya sidor:

   * [!UICONTROL Hosts]
   * [!UICONTROL Environments]

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
