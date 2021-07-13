---
keywords: molninstanser;offentlig suffixlista;offentligt suffix;cookie;förstapartscookie;förstapartscookie;förstapartscookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Utforska problem (med lösningar) som kunder ställs inför när de använder molnbaserade instanser för att testa Adobe [!DNL Target] eller för koncepttestkorrektur.
title: Kan jag använda [!DNL Target] med molnbaserade instanser?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Använd molnbaserade instanser med Target

Information om problem som kunder ställs inför när de använder molnbaserade instanser för att testa [!DNL Adobe Target].

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. De här instanserna kan omfatta följande domäner:

`azurewebsites.net`,  `cloudapp.net`,  `amazonaws.com`,  `cloudfront.net`,  `herokuapp.com`eller  `firebaseapp.com`

Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

**Problem:** Moderna webbläsare sparar inte cookies om du använder dessa domäner.

JavaScript-biblioteket [!DNL at.js] använder cookies för att spåra användare så att [!DNL Target] alltid ger en enhetlig upplevelse. Om JavaScript-biblioteket [!DNL Target] inte kan spara cookies inaktiveras [!DNL Target]-begäranden.

**Lösning:** Om du tänker använda molnbaserade instanser med domäner som finns med i Public Suffix List bör du se till att du anpassar  `cookieDomain` inställningen. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
