---
keywords: global mbox;implementera mbox.js;implementera at.js
description: Lär dig mer om den globala mbox i Adobe Target, ett namn som används för att referera till det enskilda serveranropet som görs högst upp på varje webbsida i din  [!DNL Target] implementering.
title: Vad är en global mbox?
feature: at.js
role: Developer
exl-id: 84d15feb-f5df-4879-ae35-a7f455c1b20f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Förstå den globala mbox

Information om den globala mbox, ett namn som används för att referera till det enskilda serveranropet som görs högst upp på varje webbsida i din [!DNL Adobe Target]-implementering.

Som standard heter den globala mbox `target-global-mbox`. Den kan vid behov få ett nytt namn för ditt konto.

Det finns flera skillnader mellan en vanlig mbox (icke-global mbox) och den globala mbox, inklusive:

| Vanlig mbox | Global mbox |
|--- |--- |
| En vanlig mbox radbryts vanligtvis runt innehåll med en `<DIV>`-tagg. | Den globala rutan är tom och figursätts inte runt något innehåll. |
| Innehåll från endast en aktivitet kan levereras i en vanlig mbox. | Innehåll från flera aktiviteter kan levereras som ett svar på en global mbox. |

Om flera aktiviteter levereras via den globala mbox eller via flera vanliga mrutor, bestämmer [!DNL Target] [prioriteten](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) som aktiviteten (eller aktiviteterna) levereras med till en webbsida.

Ytterligare data på sidnivå kan skickas till [!DNL Target] tillsammans med den globala mbox med funktionen `targetPageParams`. Detta liknar mbox-parameterfunktionen. Mer information finns i [Skicka parametrar till en global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).
