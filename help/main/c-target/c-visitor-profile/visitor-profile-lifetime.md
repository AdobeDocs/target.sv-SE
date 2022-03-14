---
keywords: Översikt och referens
description: Läs mer om när en besökarprofil upphör att gälla i [!DNL Adobe Target].
title: Vad är besökarprofilens livstid och kan jag utöka den?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Livslängd för besökarprofil

Som standard är en besökarprofil i [!DNL Adobe Target] upphör efter 14 dagars inaktivitet för besökaren. Profilens livslängd kan förlängas.

[Kontakta kundtjänst eller din Adobe-konsult](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att förlänga profilens livstid utan extra kostnad. Livslängden kan anges till så många som 90 dagar.

Du behöver inte ladda ned en ny [!DNL Platform Web SDK] eller filen at.js om din profil är utökad utanför standardvärdet.

Förfallodatumet återställs inte för befintliga profiler. Om en tidigare besökare inte återvänder på 15 dagar upphör den profilen att gälla. Om en tidigare besökare återgår innan den ursprungliga tvåveckorsprofilen går ut återställs profilen till den utökade livstiden. Alla nya besökarprofiler ställs in på den utökade profilens livstid.
