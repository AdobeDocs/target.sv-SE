---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL-versionerna av Adobe Target.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 68d49d4cdfd76fdea9c1e004adfaf7e6044d22bb
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---


# Versionsinformation för mål (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 4 juni 2020**

Information om den aktuella versionen finns i [Versionsinformation](release-notes.md)för mål. Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!NOTE]
>
>* **borttagning** av mbox.js: 30 augusti 2020 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Se *Adobe Target SKompetensverktyg: Utvecklarchatt: migrera Adobe Target mbox.js till at.js* nedan för mer information.
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.
   >
   >
* **Målmeddelanden**: På sidan med målmeddelanden hittar du information om kommande evenemang, bland annat om sessioner i Target SKill Builder, chats för utvecklare, webbinarier och sessioner med Target Coffee Break. Mer information finns i [Målmeddelanden](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.5.1 (17 juni 2020)

| Funktion/förbättring | Beskrivning |
| --- | --- |
| Analyser för målstöd (A4T) för automatisk allokering av aktiviteter | I juniversionen har autofördelningstester stöd för [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md). Tack vare den här integreringen kan ni använda Auto-Allocates multiväpnade bandit-funktion för att dirigera trafik till vinnande upplevelser, samtidigt som ni använder Adobe Analytics-målstatistik och/eller Adobe Analytics-rapporter och analysfunktioner. Om du redan har [implementerat A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) för användning med A/B Test- och Experience Targeting-aktiviteter är allt klart! |
| Utgivarroll | Den nya rollen liknar den nuvarande observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet för aktiva aktiviteter. |
| Administrationssida<br>Tidigare &quot;Inställningar&quot;. | Sidan Inställningar har bytt namn till Administration och gränssnittet för alla menyalternativ har uppdaterats för att förbättra arbetsflödet och göra det enklare att använda.<br>Tillgängliga menyalternativ är:<ul><li>Visual Experience Composer</li><li>Rapportering</li><li>Inställningar för Scene7</li><li>Implementering</li><li>Egenskaper</li><li>Värdar</li><li>Miljö</li><li>Svarstoken</li><li>Användare</li></ul> |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
