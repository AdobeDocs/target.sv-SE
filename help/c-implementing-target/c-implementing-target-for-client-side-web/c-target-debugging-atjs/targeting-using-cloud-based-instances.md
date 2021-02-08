---
keywords: molninstanser;offentlig suffixlista;offentligt suffix;cookie;förstapartscookie;förstapartscookie;förstapartscookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Utforska problem (med lösningar) som kunder ställs inför när de använder molnbaserade instanser för att testa Adobe Target eller för koncepttestkorrektur.
title: Kan jag använda Target med molnbaserade instanser?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---


# Använd molnbaserade instanser med Target{#use-cloud-based-instances-with-target}

Information om problem som kunder ställs inför när de använder molnbaserade instanser för att testa [!DNL Adobe Target].

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. De här instanserna kan omfatta följande domäner:

`azurewebsites.net`,  `cloudapp.net`,  `amazonaws.com`,  `cloudfront.net`,  `herokuapp.com`eller  `firebaseapp.com`

Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

**Problem:** Moderna webbläsare sparar inte cookies om du använder dessa domäner.

JavaScript-biblioteken [!DNL at.js] och [!DNL mbox.js] använder cookies för att spåra användare och säkerställa att [!DNL Target] alltid ger en enhetlig upplevelse. Om JavaScript-biblioteken [!DNL Target] inte kan spara cookies inaktiveras [!DNL Target]-begäranden.

**Lösning:** Om du tänker använda molnbaserade instanser med domäner som finns med i Public Suffix List bör du se till att du anpassar  `cookieDomain` inställningen. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
