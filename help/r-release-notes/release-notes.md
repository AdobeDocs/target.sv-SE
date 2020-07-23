---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Versionsinformationen innehåller information om funktioner, förbättringar, korrigeringar och kända fel för varje version av Adobe Target Standard och Target Premium.
title: 'Versionsinformation för Adobe Target (aktuell) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: fe68bfb124a5c8c58fbc6822d31b49257a0cfc0b
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 0%

---


# Versionsinformation om Target (aktuell){#target-release-notes-current}

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje Target Standard och Target Premium-version. Versionsinformation om Target API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, om tillämpligt.

>[!IMPORTANT]
>
>* **Adobe har återigen utnämnts till ledare i Gartners Magic Quadrant for Personalization Engines**: Adobe utsågs ännu en gång till ledare i den tredje årsrapporten Gartner Magic Quadrant for Personalization Engines, 2020. Gartner Magic Quadrant for Personalization Engines utvärderade leverantörer i 15 olika kategorier: fullständighet i synen och förmågan att genomföra. [Läs om det på Adobes blogg](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **borttagning** av mbox.js: Den 30 augusti 2020 stöder inte Adobe Target längre mbox.js-biblioteket. Efter den 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.
   >
   >
* **Target-meddelanden**: På Target webbplats för information om kommande evenemang, som sessioner med Target SKill Builder, chats för utvecklare, webbinarier och Target Coffee Break. Mer information finns i [Target-meddelanden](/help/r-release-notes/target-announcements.md).


Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

## Target Standard/Premium 20.7.1 (27 juli 2020)

Den här versionen innehåller följande ändringar:

### [!UICONTROL Administration] gränssnittsuppdatering för avsnitt

Vi skriver gradvis om hela [!DNL Target] användargränssnittet med en ny teknologi för att kunna erbjuda bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Det första avsnittet som uppdateras är [!UICONTROL Setup] avsnittet som har fått ett nytt namn [!UICONTROL Administration].

Som en del av den här uppdateringen kan du enkelt utföra många åtgärder med hjälp av sidorna i [!UICONTROL Administration] avsnittet, som:

* Hämta den senaste at.js-filen från [!UICONTROL Implementation] fliken (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**).
* Anpassa dina at.js-inställningar och granska enkelt dina ändringar (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**).
* Ändra utökade rapportinställningar, t.ex. standardvaluta och tidszon, IP-adresser som ska uteslutas från rapportering osv. (**[!UICONTROL Administration]** > **[!UICONTROL Reporting]**)
* Förhindra besökarens IP-adresser av sekretesskäl (**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**)
* Visa den befintliga listan över användare per arbetsyta och deras roller innan du hanterar dem i Adobe Admin Console (**[!UICONTROL Administration]** > **[!UICONTROL Users]**).
* Sök och filtrera alla tabeller i [!UICONTROL Administration] avsnittet.

Mer information finns i [Administrera Target-översikt](/help/administrating-target/administrating-target.md).

### Förbättringar, korrigeringar och ändringar

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Ett problem som gjorde att platsinställningarna inte kunde behållas efter uppdateringen har åtgärdats. (TGT-37239)
* Korrigerade ett fel som förhindrade [!UICONTROL Insert After] > [!UICONTROL Image] från att fungera korrekt med SVG-bilder (Scalable Vector Graphics). (TGT-37242)
* Ett problem har korrigerats för användare med den [!UICONTROL Publisher] rollen som förhindrade att utkast till aktiviteter togs bort. (TGT-37358)
* Korrigerade ett problem som hindrade användare från att redigera en aktivitet när [!UICONTROL All My Workspaces] den har valts. (TGT-37276)

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation - Target serversides-API:er](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Versionsinformation om Adobe Target server-side API:er. |
| [Versionsinformation - Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Versionsinformation om Adobe Target Node.js SDK. |
| [Versionsinformation - Target Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Versionsinformation om Adobe Target Java SDK. |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringarna i varje version av JavaScript-biblioteket Adobe Target at.js. |
| [versionsinformation för mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | På den här sidan visas ändringar för varje version av mbox.js.<br>Observera att mbox.js-biblioteket inte längre utvecklas. Alla kunder bör migrera från mbox.js till at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som kanske inte finns med i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](../r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation om Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud-lösningarna.<br>Mer information finns i [versionsinformationen](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)för Experience Cloud. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Följande resurser visar vad som kommer i nästa version av Target.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdateringslista för Adobe-prioritet | Om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar registrerar du dig för produktuppdateringen Adobe Priority:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation, finns på sidan [Target Release Notes - Förhandsversion](/help/r-release-notes/target-release-notes.md) . |
