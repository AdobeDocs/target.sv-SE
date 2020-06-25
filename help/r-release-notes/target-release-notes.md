---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL Adobe Target-versionerna.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: d37cd2e93af576741dfd17f8e54dada06b8a64a3
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---


# Versionsinformation för Target (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 24 juni 2020**

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


## Target Standard/Premium 20.7.1 (21 juli 2020)

Den här versionen innehåller följande förbättringar:

### Stöd för aktiviteter i Analytics for Target (A4T) [!UICONTROL Auto-Target]

[!UICONTROL Auto-Target] nu stöder [Analytics för Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

Denna integrering använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar. Auto-Target levererar den mest skräddarsydda upplevelsen till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler.

Om du redan har [implementerat A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) för A/B Test-aktiviteter är allt klart!

### [!UICONTROL Administration] gränssnittsuppdatering för avsnitt

Vi skriver gradvis om hela [!DNL Target] användargränssnittet med en ny teknologi för att kunna erbjuda bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Det första avsnittet som uppdateras är [!UICONTROL Setup] avsnittet som har fått ett nytt namn [!UICONTROL Administration].

Som en del av den här uppdateringen kan du enkelt utföra många åtgärder med hjälp av sidorna i [!UICONTROL Administration] avsnittet, som:

* Hämta den senaste at.js-filen från [!UICONTROL Implementation] fliken (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**).
* Anpassa dina at.js-inställningar och granska enkelt dina ändringar (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**).
* Ändra utökade rapportinställningar, t.ex. standardvaluta och tidszon, IP-adresser som ska uteslutas från rapportering osv. (**[!UICONTROL Administration]** > **[!UICONTROL Reporting]**)
* Förhindra besökarens IP-adresser av sekretesskäl (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**)
* Visa den befintliga listan över användare per arbetsyta och deras roller innan du hanterar dem i Adobe Admin Console (**[!UICONTROL Administration]** > **[!UICONTROL Users]**).
* Sök och filtrera alla tabeller i [!UICONTROL Administration] avsnittet.

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
