---
keywords: global mbox;;implementera at.js
description: Läs mer om den globala mbox i Adobe Target, ett namn som används för att hänvisa till det enda serveranropet som gjordes högst upp på varje webbsida på din [!DNL Target] implementering.
title: Vad är en global mbox?
feature: at.js
role: Developer
exl-id: 84d15feb-f5df-4879-ae35-a7f455c1b20f
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Förstå den globala mbox

Information om den globala mbox, ett namn som används för att referera till det enskilda serveranropet som görs högst upp på varje webbsida på din [!DNL Adobe Target] implementering.

Som standard har den globala mbox namnet `target-global-mbox`. Den kan vid behov få ett nytt namn för ditt konto.

Det finns flera skillnader mellan en vanlig mbox (icke-global mbox) och den globala mbox, inklusive:

| Vanlig mbox | Global mbox |
|--- |--- |
| En vanlig ruta figursätts vanligtvis runt innehåll med en `<DIV>` -tagg. | Den globala rutan är tom och figursätts inte runt något innehåll. |
| Innehåll från endast en aktivitet kan levereras i en vanlig mbox. | Innehåll från flera aktiviteter kan levereras som ett svar på en global mbox. |

Om flera aktiviteter levereras via den globala mbox eller via flera vanliga mbox-meddelanden, [!DNL Target] [bestämmer prioriteten](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) genom vilken aktiviteten (eller aktiviteterna) levereras till en webbsida.

Ytterligare data på sidnivå kan skickas till [!DNL Target] tillsammans med den globala mboxen med `targetPageParams` funktion. Detta liknar mbox-parameterfunktionen. Mer information finns i [Skicka parametrar till en global mbox](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/).
