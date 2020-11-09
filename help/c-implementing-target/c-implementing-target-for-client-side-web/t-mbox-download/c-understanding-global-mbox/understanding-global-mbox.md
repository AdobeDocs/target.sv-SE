---
keywords: global mbox;implement mbox.js;implement at.js
description: Information om den globala mbox, ett namn som används för att hänvisa till det enda serveranropet som gjordes högst upp på varje webbsida i din Adobe Target-implementering.
title: Förstå den globala mbox
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---


# Förstå den globala mbox{#understand-the-global-mbox}

Information om den globala mbox, ett namn som används för att referera till det enskilda serveranropet som görs högst upp på varje webbsida i din [!DNL Adobe Target] implementering.

Som standard heter den globala mbox `target-global-mbox`. Den kan vid behov få ett nytt namn för ditt konto.

Det finns flera skillnader mellan en vanlig mbox (icke-global mbox) och den globala mbox, inklusive:

| Vanlig mbox | Global mbox |
|--- |--- |
| En vanlig ruta figursätts vanligtvis runt innehåll med en `<DIV>` tagg. | Den globala rutan är tom och figursätts inte runt något innehåll. |
| Innehåll från endast en aktivitet kan levereras i en vanlig mbox. | Innehåll från flera aktiviteter kan levereras som ett svar på en global mbox. |

Om flera aktiviteter levereras via den globala mbox eller via flera vanliga mrutor, [!DNL Target] bestämmer du vilken prioritet [](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) aktiviteten (eller aktiviteterna) ska levereras med till en webbsida.

Ytterligare data på sidnivå kan skickas till [!DNL Target] tillsammans med den globala mbox-filen med hjälp av `targetPageParams` funktionen. Detta liknar mbox-parameterfunktionen. Mer information finns i [Skicka parametrar till en global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).
