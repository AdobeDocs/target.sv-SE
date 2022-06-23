---
keywords: felsökning;vanliga frågor;Vanliga frågor;Vanliga frågor;Vanliga frågor;global;global mbox
description: Frågor och svar om Adobe [!DNL Target] globala lådor.
title: Vilka är de vanliga frågorna om den globala rutan?
feature: at.js
role: Developer
exl-id: ec8399df-5222-44bd-9e61-dfce8fd1694d
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---

# Vanliga frågor och svar om Global Mbox

Lista med vanliga frågor och svar om globala kryssrutor.

## Kan jag ha fler än en global mbox om [!DNL Target] anges kontot över flera domäner? {#section_B7252BA6C3BB4EF4AE9E53F47FD58ABD}

Endast en global mbox stöds för hela kontot.

Du kan begränsa var dina aktiviteter körs genom att lägga till URL-regler i dina aktiviteter. Mer information finns i [Inkludera samma upplevelse på liknande sidor](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Du kan också skicka en parameter på sidan med [targetPageParams](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparams/) och sedan välja parametrarna i avsnittet &quot;Konfigurera URL&quot; i [!UICONTROL Visual Experience Composer] (VEC) eller genom att lägga till parametrarna som&quot;förbättringar&quot; i den formulärbaserade Experience Composer.

## Hur skickar jag intäktsdata till en [!DNL Target] global mbox? {#section_17AEA933BADA4D169CCEDF5833C41306}

Om du vill samla in intäkter och orderinformation för target-global-mbox måste&quot;mbox parameters&quot; skickas till Target. Dessa parametrar är namn/värde-par som används för att skicka mer information till Target. Target söker automatiskt efter dessa parametrar (reserverade namn) för att fylla i intäktsdata.

För `orderConfirmPage`bör du skicka in `orderTotal`, `orderId`och `productPurchasedId`.

Dessa parametrar måste skickas till target-global-mbox via `targetPageParams()`. Mer information finns i [Skicka parametrar till en global mbox](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/).

Du kommer också att lägga till målinriktning i konverteringsdelen så att Target endast räknar konverteringar i målets globala mbox när orderbekräftelsesidan har visats, vilket visas nedan:

![](assets/revenue1.png)

Avsnittet Webbplatssidor som visas ovan innehåller följande markeringar: Aktuell sida, URL, innehåller, orderbekräftelse.

![](assets/revenue2.png)

Alternativen i ovanstående bild omfattar följande inställningar:

* **Vad vill du mäta med den här aktiviteten:** Intäkter
* **Standardvy för rapportering:** Intäkter per besökare (RPV)
* **Vilka åtgärder vidtogs av er målgrupp för att ange att ni har nått ert mål?** Visad mbox, target-global-mbox
