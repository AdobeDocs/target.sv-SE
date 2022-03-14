---
keywords: felsökning;vanliga frågor;Vanliga frågor;Vanliga frågor;Vanliga frågor;global;global mbox
description: Frågor och svar om Adobe [!DNL Target] globala lådor.
title: Vilka är de vanliga frågorna om den globala rutan?
feature: at.js
role: Developer
exl-id: ec8399df-5222-44bd-9e61-dfce8fd1694d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Vanliga frågor och svar om Global Mbox

Lista med vanliga frågor och svar om globala kryssrutor.

## Kan jag ha fler än en global mbox om [!DNL Target] anges kontot över flera domäner? {#section_B7252BA6C3BB4EF4AE9E53F47FD58ABD}

Endast en global mbox stöds för hela kontot.

Du kan begränsa var dina aktiviteter körs genom att lägga till URL-regler i dina aktiviteter. Mer information finns i [Inkludera samma upplevelse på liknande sidor](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Du kan också skicka en parameter på sidan med [targetPageParams](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) och sedan välja parametrarna i avsnittet &quot;Konfigurera URL&quot; i [!UICONTROL Visual Experience Composer] (VEC) eller genom att lägga till parametrarna som&quot;förbättringar&quot; i den formulärbaserade Experience Composer.

## Hur skickar jag intäktsdata till en [!DNL Target] global mbox? {#section_17AEA933BADA4D169CCEDF5833C41306}

Om du vill samla in intäkter och orderinformation för target-global-mbox måste&quot;mbox parameters&quot; skickas till Target. Dessa parametrar är namn/värde-par som används för att skicka mer information till Target. Target söker automatiskt efter dessa parametrar (reserverade namn) för att fylla i intäktsdata.

För `orderConfirmPage`bör du skicka in `orderTotal`, `orderId`och `productPurchasedId`.

Dessa parametrar måste skickas till target-global-mbox via `targetPageParams()`. Mer information finns i [Skicka parametrar till en global mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).

Du kommer också att lägga till målinriktning i konverteringsdelen så att Target endast räknar konverteringar i målets globala mbox när orderbekräftelsesidan har visats, vilket visas nedan:

![](assets/revenue1.png)

Avsnittet Webbplatssidor som visas ovan innehåller följande markeringar: Aktuell sida, URL, innehåller, orderbekräftelse.

![](assets/revenue2.png)

Alternativen i ovanstående bild omfattar följande inställningar:

* **Vad vill du mäta med den här aktiviteten:** Intäkter
* **Standardvy för rapportering:** Intäkter per besökare (RPV)
* **Vilka åtgärder vidtogs av er målgrupp för att ange att ni har nått ert mål?** Visad mbox, target-global-mbox
