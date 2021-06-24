---
keywords: mbox.js faq;mbox.js Vanliga frågor;document.write;tt.omtrdc.net;parser block
description: Läs om den gamla implementeringen av mbox.js i Adobe Target. Migrera till Adobe Experience Platform Web SDK (AEP Web SDK) eller till den senaste versionen av at.js.
title: Vad ställs det ofta frågor om [!DNL Target] mbox.js?
feature: at.js
role: Developer
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# mbox.js Vanliga frågor

Svar på vanliga frågor om mbox.js.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Varför skjuter inte mina lådor på mina webbsidor? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

Moderna webbläsare sparar inte cookies om du använder dessa domäner om du inte anpassar inställningen `cookieDomain` med targetGlobalSettings(). Mer information finns i [Använda molnbaserade instanser med Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## Vad är domänen tt.omtrdc.net som [!DNL Target] serveranrop går till? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] är domännamnet för Adobe EDGE-nätverket, som används för att ta emot alla serveranrop för Target.

## Varför använder inte at.js och mbox.js flaggorna HttpOnly och Secure cookie? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly kan bara anges via kod på serversidan. Målcookies, som mbox, skapas och sparas via JavaScript-kod, så Target kan inte använda HTML-cookie-flaggan.

Säker kan bara ställas in via JavaScript när sidan har lästs in via HTTPS. Om sidan först läses in via HTTP kan JavaScript inte ange den här flaggan. Om du dessutom använder flaggan Secure är cookie bara tillgänglig på HTTPS-sidor.

För att garantera att Target kan spåra användare på rätt sätt och eftersom cookies genereras på klientsidan, använder inte Target någon av dessa flaggor.
