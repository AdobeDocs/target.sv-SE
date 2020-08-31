---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL Adobe Target-versionerna.
title: Adobe Target prerelease notes
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 405715f1ee1afd1d298dc7f1ef0cd3599620cbca
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---


# Versionsinformation för mål (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 31 augusti 2020**

Information om den aktuella versionen finns i [Versionsinformation](release-notes.md)för mål. Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!IMPORTANT]
>
>* **Adobe igen utsedd till ledare i Gartners Magic Quadrant for Personalization Engines**: Adobe utnämndes ännu en gång till ledare i den tredje årsrapporten Gartner Magic Quadrant for Personalization Engines, 2020. Gartner Magic Quadrant for Personalization Engines utvärderade leverantörer i 15 olika kategorier: fullständighet i synen och förmågan att genomföra. [Läs om det på Adobe-bloggen](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **borttagning** av mbox.js: 18 januari 2021 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 18 januari 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor som har Target-aktiviteter igång genom att skicka standardinnehåll. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKomplett Builder: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig från Adobe.
   >
   >
* **Målmeddelanden**: På sidan med målmeddelanden hittar du information om kommande evenemang, bland annat om sessioner i Target SKill Builder, chats för utvecklare, webbinarier och sessioner med Target Coffee Break. Mer information finns i [Målmeddelanden](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.8.1 (2 september 2020)

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Korrigerade ett problem som orsakade att fel visades när de nya [!UICONTROL Administration] sidorna lästes in efter bytet av organisationer. (TGT-37730)
* Korrigerade ett visningsproblem som gjorde att fel klientkod visades på [!UICONTROL Administration > Implementation] sidan. (TGT-37849)
* Korrigerade ett fel som ibland förhindrade användare från att använda redigeringsfunktionerna i [!UICONTROL Visual Experience Composer] (VEC) efter att ha läst in VEC. (TGT-37162)
* Korrigerade ett problem som förhindrade att sidor lästes in i VEC och Enhanced Experience Composer (EEC) trots att VEC Helper-tillägget installerades. Detta berodde på ändringar i Google Chrome 80+. Ladda ned det [uppdaterade VEC Helper-tillägget](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md). (TGT-37893)
* Korrigerade ett problem som ibland förhindrade användare från att hämta at.js från [!UICONTROL Administration > Implementation] sidan efter att ha bytt organisation. (TGT-37668)
* Nedladdningsknappen at.js är nu inaktiverad vid inläsning för att förhindra att flera begäranden skickas om användare klickar på nedladdningsknappen flera gånger. [!DNL Target] (TGT-37633)
* Korrigerade ett problem i [!UICONTROL Experience Targeting] (XT)-aktiviteter som gjorde att upplevelser visade &quot;hämtningsresultat&quot; under en längre tid. (TGT-37684)
* Förbättrad navigering och funktionalitet för användare som bara använder tangentbordet. (TGT-34479 &amp; TGT-34473)
* Etiketter har lagts till i användargränssnittet för att underlätta för användare som använder hjälpmedelstekniker. (TGT-34480)
* Förbättrade felmeddelandet när en mobil visningsruta som används i en aktivitet tas bort. Felmeddelandet visas nu: &quot;Den här visningsrutan är för närvarande associerad med en eller flera aktiviteter. Du måste ta bort visningsrutan från dessa aktiviteter innan du kan ta bort den.&quot; (TGT-37030)
* Stöd har lagts till i VEC för klickspårning på en CSS-väljare som matchar mer än ett element på sidan. (TGT-37323)
* Ett problem som gjorde att vissa användare inte kunde visa [!UICONTROL Activity] listan har korrigerats. Följande felmeddelande visades: &quot;Det gick inte att hämta URL-förslag.&quot; Felet uppstod för användare som använder vagnreturer i FirstName (FirstName/r/n) i Adobe Backend-systemet. (TGT-37330)
* Korrigerade ett problem som gjorde att användare inte kunde visa [!UICONTROL Activity] sidan om arbetsytans namn (som anges i [!UICONTROL Adobe Admin Console for Enterprise]) innehåller en apostrof. (TGT-37709)
* Korrigerade ett fel i [!UICONTROL Auto-Allocate] aktiviteter när optimerings- och konverteringsmått valdes, där ett felmeddelande felaktigt informerade användarna om att de skulle välja en rapportserie, trots att en rapportserie redan hade angetts. (TGT-37689)
* Korrigerade ett problem som ibland orsakade att mätvärden på [!UICONTROL Goals and Settings] sidan blev tomma efter att du navigerade till [!UICONTROL Targeting] sidan och sedan tillbaka. (TGT-37691)
* Korrigerade ett problem som orsakade ett felaktigt värde för senaste ändring för [!DNL Recommendations] villkor. (TGT-37666)
* Korrigerade ett problem som gjorde att mbox-ID:n visades i listrutan Mboxes i stället för i mbox-namn. (TGT-37739)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
