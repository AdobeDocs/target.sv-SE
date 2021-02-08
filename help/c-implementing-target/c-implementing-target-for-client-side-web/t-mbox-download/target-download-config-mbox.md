---
keywords: Implementering;Mbox;mbox.js;download mbox.js;configure mbox.js
description: Läs om den gamla implementeringen av mbox.js i Adobe Target. Migrera till Adobe Experience Platform Web SDK (AEP Web SDK) eller till den senaste versionen av at.js.
title: Hur hämtar jag Target mbox.js-biblioteket?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Hämta mbox.js{#download-mbox-js}

I Target Standard och Premium används en modifierad version av filen Adobe Target mbox.js.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Om du vill använda [!DNL Adobe Target] [!UICONTROL Visual Experience Editor] måste du ta med ytterligare en rad med JavaScript som en del av din [!DNL mbox.js]-fil.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** i [!DNL Target Standard].
1. Klicka på **[!UICONTROL Download mbox.js]** och följ anvisningarna för att spara filen.
1. (Villkorligt) Om du använder [!DNL mbox.js] version 60 eller senare kan du konfigurera biblioteket så att sidinnehållet döljs automatiskt som standard tills rutor läses in för att minska flimret på responsiva webbplatser.

   Mer information finns i&quot;Utelämna sidinläsningsflimmer&quot; i [mbox.js Avancerade inställningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Skapa [!DNL mbox.js]-referensen på webbplatsen.

   Från och med [!DNL mbox.js] version 57 kan [!DNL mbox.js]-referensen placeras var som helst i `<head>`-avsnittet på sidan.

   >[!IMPORTANT]
   >
   >Om du använder en version av [!DNL mbox.js] som är tidigare än version 57 måste referensen vara det sista objektet i `<head>`-avsnittet på sidorna. Om referensen inte är den sista posten kan allvarliga problem med visning eller prestanda uppstå. Mer information finns i [What mbox.js does](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md).

1. Överför den sparade [!DNL mbox.js]-filen till den plats i värdmiljön som du angav i koden.
