---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL Adobe Target-versionerna.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 7f23f80a0528ea2e6de78a5491c87ca72862813d
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---


# Versionsinformation för Target (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 13 juli 2020**

Information om den aktuella versionen finns i [Target Versionsinformation](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!NOTE]
>
>* **borttagning** av mbox.js: Den 30 augusti 2020 stöder inte Adobe Target längre mbox.js-biblioteket. Efter den 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
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

### [!UICONTROL Administration] gränssnittsuppdatering för avsnitt

Vi skriver gradvis om hela [!DNL Target] användargränssnittet med en ny teknologi för att kunna erbjuda bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Det första avsnittet som uppdateras är [!UICONTROL Setup] avsnittet som har fått ett nytt namn [!UICONTROL Administration].

Som en del av den här uppdateringen kan du enkelt utföra många åtgärder med hjälp av sidorna i [!UICONTROL Administration] avsnittet, som:

* Hämta den senaste at.js-filen från [!UICONTROL Implementation] fliken (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**).
* Anpassa dina at.js-inställningar och granska enkelt dina ändringar (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**).
* Ändra utökade rapportinställningar, t.ex. standardvaluta och tidszon, IP-adresser som ska uteslutas från rapportering osv. (**[!UICONTROL Administration]** > **[!UICONTROL Reporting]**)
* Förhindra besökarens IP-adresser av sekretesskäl (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**)
* Visa den befintliga listan över användare per arbetsyta och deras roller innan du hanterar dem i Adobe Admin Console (**[!UICONTROL Administration]** > **[!UICONTROL Users]**).
* Sök och filtrera alla tabeller i [!UICONTROL Administration] avsnittet.

### Förbättringar, korrigeringar och ändringar

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Ett problem som gjorde att platsinställningarna inte kunde behållas efter uppdateringen har åtgärdats. (TGT-37239)
* Korrigerade ett fel som förhindrade [!UICONTROL Insert After] > [!UICONTROL Image] från att fungera korrekt med SVG-bilder (Scalable Vector Graphics). (TGT-37242)
* Ett problem har korrigerats för användare med den [!UICONTROL Publisher] rollen som förhindrade att utkast till aktiviteter togs bort. (TGT-37358)
* Korrigerade ett problem som hindrade användare från att redigera en aktivitet när [!UICONTROL All My Workspaces] den har valts. (TGT-37276)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
