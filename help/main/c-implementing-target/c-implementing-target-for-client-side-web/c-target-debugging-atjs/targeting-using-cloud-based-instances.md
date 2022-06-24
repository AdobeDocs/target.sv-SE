---
keywords: molninstanser;offentlig suffixlista;offentligt suffix;cookie;förstapartscookie;förstapartscookie;förstapartscookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Utforska problem (med lösningar) som kunder ställs inför när de använder molnbaserade instanser för att testa Adobe [!DNL Target] eller för konceptbevisändamål.
title: Kan jag använda [!DNL Target] med molnbaserade instanser?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Använd molnbaserade instanser med Target

Information om problem som kunderna ställs inför när de använder molnbaserade instanser för att testa [!DNL Adobe Target].

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. De här instanserna kan omfatta följande domäner:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com`, eller `firebaseapp.com`

Dessa domäner, och många andra, ingår i [Lista över offentliga suffix](https://publicsuffix.org/list/public_suffix_list.dat).

**Problem:** Moderna webbläsare sparar inte cookies om du använder dessa domäner.

The [!DNL at.js] JavaScript-biblioteket använder cookies för att spåra användare och säkerställa att [!DNL Target] alltid ger en enhetlig upplevelse. Om [!DNL Target] JavaScript-biblioteket kan inte spara cookies, [!DNL Target] begäranden är inaktiverade.

**Lösning:** Om du tänker använda molnbaserade instanser med domäner som finns med i listan över offentliga suffix bör du se till att du anpassar `cookieDomain` inställning. Mer information finns i [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}.
