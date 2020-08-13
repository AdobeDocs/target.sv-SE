---
keywords: cloud instances;public suffix list;public suffix;cookie;first-party cookie;1st-party cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Information om problem som kunderna ställs inför när de använder molnbaserade instanser för att testa Adobe Target.
title: Använd molnbaserade instanser med Target
feature: client-side
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Använd molnbaserade instanser med Target{#use-cloud-based-instances-with-target}

Information om problem som kunderna ställs inför när de använder molnbaserade instanser för att testa [!DNL Adobe Target].

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. De här instanserna kan omfatta följande domäner:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com`eller `firebaseapp.com`

Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

**Problem:** Moderna webbläsare sparar inte cookies om du använder dessa domäner.

I biblioteken [!DNL at.js] och [!DNL mbox.js] JavaScript-biblioteken används cookies för att spåra användare för att säkerställa att [!DNL Target] alltid ger en enhetlig upplevelse. Om [!DNL Target] JavaScript-biblioteken inte kan spara cookies inaktiveras [!DNL Target] begäranden.

**Lösning:** Om du tänker använda molnbaserade instanser med domäner som finns med i listan över offentliga suffix bör du se till att du anpassar `cookieDomain` inställningen. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
