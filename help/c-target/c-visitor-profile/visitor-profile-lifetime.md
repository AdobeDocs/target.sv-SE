---
keywords: Overview and Reference
description: Som standard lagras besöksprofiler i 14 dagar. Profilens livslängd kan förlängas.
title: Livslängd för besökarprofil
feature: null
subtopic: Getting Started
topic: Standard
uuid: 01ccda60-7e28-4d26-8d5d-1c0a022bbef0
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Livslängd för besökarprofil{#visitor-profile-lifetime}

Som standard upphör en besökarprofil att gälla efter 14 dagars inaktivitet för den besökaren. Profilens livslängd kan förlängas.

[Kontakta kundtjänst eller din Adobe-konsult](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att förlänga profilens livstid utan extra kostnad. Livslängden kan anges till så många som 90 dagar.

Det [!DNL Target] JavaScript-bibliotek som du använder ( [!DNL at.js] eller [!DNL mbox.js]) avgör om du behöver hämta en ny fil eller inte:

| Målbibliotek | Detaljer |
|--- |--- |
| at.js | Du behöver inte ladda ned en ny at.js-fil om din profil är utökad efter standardinställningen. |
| mbox.js | Om din profil har utökats efter 14-dagars standardinställning måste du hämta en ny mbox.js-fil när konsulten eller Client Care har ändrat dina inställningar. Cookie-tillägget som stöder den ändrade profilens livstid ingår i den uppdaterade filen mbox.js. När du har börjat använda det nya biblioteket uppdateras besökarnas profillivstider. |

Förfallodatumet återställs inte för befintliga profiler. Om en tidigare besökare inte återvänder på 15 dagar upphör den profilen att gälla. Om en tidigare besökare återgår innan den ursprungliga tvåveckorsprofilen går ut återställs profilen till den utökade livstiden. Alla nya besökarprofiler ställs in på den utökade profilens livstid.

Om du har två webbplatser under en klientkod och en besökare besöker båda platserna, ställs profilen in på den senaste platsens livstid. Om till exempel Plats 1 har en 84-dagars profillivstid och Plats 2 har en 14-dagars livstid, och besökaren besöker Plats 1 och sedan Plats 2, kommer besökarens profil att upphöra om 14 dagars inaktivitet. Om besökaren besöker Plats 1 efter besök på Plats 2 kommer profilen att upphöra om 84 dagars inaktivitet.
