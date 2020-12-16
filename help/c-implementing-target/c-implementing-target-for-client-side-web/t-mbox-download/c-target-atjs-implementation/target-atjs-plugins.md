---
keywords: at.js plugins;supported plugins;unsupported plugins;ttMeta;ttmeta;mboxTrack
description: Information om vilka plugin-program som stöds och inte stöds för at.js för Adobe Target.
title: at.js plugin-program för Adobe Target
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# at.js plug-ins{#at-js-plug-ins}

Information om plugin-program för at.js som stöds och inte stöds i Adobe Target.

Många har skapat anpassade plugin-program och plugin-program för [!DNL mbox.js]. Dessa anpassade plugin-program kanske inte stöds av [!DNL at.js] utan att uppdateras.

Om du använder ett plugin-program som inte finns med i listan och du vill veta status kontaktar du din kontorepresentant.

Här är den aktuella statusen för några av de plugin-program som används av många kunder när de används med [!DNL at.js]:

| Plugin | Detaljer |
|--- |--- |
| mboxTrack | Stöds inte.<br>Detta ersätts av  [funktionen adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) . Uppdatera plugin-programmen för att använda den nya funktionen.<br>Se  [](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md) integreringssidan. |
| Plugin för säkerhetskopiering av beständig profil | Stöds inte.<br>Denna plugin togs bort när Target-profilens livstid förlängdes från två veckor till 90 dagar. Kontrollera utgångsdatumet för din mbox-cookie för att se inställningen för profillivstid på ditt konto.<br>Kontakta ClientCare om du vill förlänga profilens livstid till 90 dagar. |
| ttMeta | Gamla SiteCatalyst-plugin-program ska inaktiveras och ersättas med [Adobe Analytics som rapportkälla för Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). ttMeta-plugin-programmet ska inaktiveras och ersättas med [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). |