---
keywords: Implementation;Mbox;mbox.js;download mbox.js;configure mbox.js
description: I Target Standard och Premium används en modifierad version av filen Adobe Target mbox.js.
title: Ladda ned mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---


# Ladda ned mbox.js{#download-mbox-js}

I Target Standard och Premium används en modifierad version av filen Adobe Target mbox.js.

Om du vill använda [!DNL Adobe Target][!UICONTROL Visual Experience Editor]måste du inkludera ytterligare en rad JavaScript som en del av [!DNL mbox.js] filen.

1. Klicka **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** i [!DNL Target Standard].
1. Klicka **[!UICONTROL Download mbox.js]** och följ anvisningarna för att spara filen.
1. (Villkorligt) Om du använder [!DNL mbox.js] version 60 eller senare kan du konfigurera biblioteket så att sidinnehållet automatiskt döljs som standard tills rutor läses in för att minska flimret på responsiva webbplatser.

   Mer information finns i&quot;Utelämna sidinläsningsflimmer&quot; i [mbox.js Avancerade inställningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Skapa [!DNL mbox.js] referensen på webbplatsen.

   Från och med [!DNL mbox.js] version 57 kan [!DNL mbox.js] referensen placeras var som helst i sidans `<head>` avsnitt.

   >[!IMPORTANT]
   >
   >Om du använder en version av som [!DNL mbox.js] är tidigare än version 57 måste referensen vara det sista objektet i sidavsnittet `<head>` . Om referensen inte är den sista posten kan allvarliga problem med visning eller prestanda uppstå. Mer information finns i [Vad mbox.js gör](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) .

1. Överför den sparade [!DNL mbox.js] filen till den plats i värdmiljön som du angav i koden.
