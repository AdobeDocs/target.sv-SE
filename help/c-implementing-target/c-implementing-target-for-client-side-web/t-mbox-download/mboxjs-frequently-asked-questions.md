---
keywords: mbox.js faq;mbox.js frequently asked questions;document.write;tt.omtrdc.net;parser blocking
description: Svar på vanliga frågor om mbox.js.
title: mbox.js Vanliga frågor
feature: null
subtopic: Getting Started
uuid: af3105ab-87d9-4dbf-a380-b72788928958
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---


# mbox.js Vanliga frågor{#mbox-js-frequently-asked-questions}

Svar på vanliga frågor om mbox.js.

## Hur påverkar mbox.js sidinläsningstiderna? {#section_90B3B94FE0BF4B369577FCB97B67F089}

Mer information finns i [Fördelar med at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits).

## Varför får jag varningsmeddelanden om&quot;parser-blockering&quot; i Google Chrome när jag använder mbox.js och document.write? {#section_355A3A5BF02F42EEB8271C96EF41590A}

Det här konsolmeddelandet visas när Chrome används i många scenarier där `document.write` funktionen används i filen mbox.js. Det här är ett varningsmeddelande och bör inte påverka aktivitetsinställningsprocessen.

Det bästa sättet att förhindra detta är att [migrera Target-implementeringen till JavaScript-biblioteket](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)at.js, som inte använder `document.write` funktionen. Att använda at.js ger många fördelar jämfört med att använda mbox.js. Mer information finns i [at.js Vanliga frågor](../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## Varför skjuter inte mina lådor på mina webbsidor? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

I moderna webbläsare sparas inte cookies om du använder dessa domäner om du inte anpassar inställningen med targetGlobalSettings(). `cookieDomain` Mer information finns i [Använda molnbaserade instanser med Target](../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## Vad är domänen tt.omtrdc.net som anrop från målservern går till? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] är domännamnet för Adobe EDGE-nätverket, som används för att ta emot alla serveranrop för Target.

## Varför använder inte at.js och mbox.js flaggorna HttpOnly och Secure cookie? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly kan bara anges via kod på serversidan. Målcookies, som mbox, skapas och sparas via JavaScript-kod, så Target kan inte använda HTML-cookie-flaggan.

Säker kan bara ställas in via JavaScript när sidan har lästs in via HTTPS. Om sidan först läses in via HTTP kan JavaScript inte ange den här flaggan. Om du dessutom använder flaggan Secure är cookie bara tillgänglig på HTTPS-sidor.

För att garantera att Target kan spåra användare på rätt sätt och eftersom cookies genereras på klientsidan, använder inte Target någon av dessa flaggor.
