---
keywords: Översikt och referens
description: Läs mer om när en besökarprofil upphör att gälla om  [!DNL Adobe Target].
title: Hur lång är besökarprofilen och kan jag utöka den?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Livslängd för besökarprofil

Som standard upphör en besökarprofil i [!DNL Adobe Target] att gälla efter 14 dagars inaktivitet för den besökaren. Profilens livslängd kan förlängas.

[Kontakta kundtjänst eller din Adobe-konsult](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du vill förlänga profilens livstid utan extra kostnad. Livslängden kan anges till så många som 90 dagar.

Du behöver inte hämta en ny [!DNL Platform Web SDK]-fil eller at.js-fil om din profil är utökad efter standardvärdet.

Förfallodatumet återställs inte för befintliga profiler. Om en tidigare besökare inte återvänder på 15 dagar upphör den profilen att gälla. Om en tidigare besökare återgår innan den ursprungliga tvåveckorsprofilen går ut återställs profilen till den utökade livstiden. Alla nya besökarprofiler ställs in på den utökade profilens livstid.
