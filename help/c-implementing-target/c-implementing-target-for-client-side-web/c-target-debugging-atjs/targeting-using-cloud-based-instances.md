---
keywords: molninstanser;offentlig suffixlista;offentligt suffix;cookie;förstapartscookie;förstapartscookie;förstapartscookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Utforska problem (med lösningar) som kunder ställs inför när de använder molnbaserade instanser för att testa Adobe [!DNL Target] eller för koncepttestkorrektur.
title: Kan jag använda [!DNL Target] med molnbaserade instanser?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 0%

---

# Använd molnbaserade instanser med Target

Information om problem som kunder ställs inför när de använder molnbaserade instanser för att testa [!DNL Adobe Target].

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. De här instanserna kan omfatta följande domäner:

`azurewebsites.net`,  `cloudapp.net`,  `amazonaws.com`,  `cloudfront.net`,  `herokuapp.com`eller  `firebaseapp.com`

Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

**Problem:** Moderna webbläsare sparar inte cookies om du använder dessa domäner.

JavaScript-biblioteken [!DNL at.js] och [!DNL mbox.js] använder cookies för att spåra användare och säkerställa att [!DNL Target] alltid ger en enhetlig upplevelse. Om JavaScript-biblioteken [!DNL Target] inte kan spara cookies inaktiveras [!DNL Target]-begäranden.

**Lösning:** Om du tänker använda molnbaserade instanser med domäner som finns med i Public Suffix List bör du se till att du anpassar  `cookieDomain` inställningen. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
