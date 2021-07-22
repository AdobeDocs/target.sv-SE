---
keywords: Översikt och referens
description: Läs mer om när en besökarprofil upphör att gälla i [!DNL Adobe Target].
title: Vad är besökarprofilens livstid och kan jag utöka den?
feature: Målgrupper
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Livslängd för besökarprofil

Som standard upphör en besökarprofil i [!DNL Adobe Target] att gälla efter 14 dagars inaktivitet för den besökaren. Profilens livslängd kan förlängas.

[Kontakta kundtjänst eller din Adobe-](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) konsult för att förlänga profilens livstid utan extra kostnad. Livslängden kan anges till så många som 90 dagar.

Du behöver inte hämta en ny [!DNL Platform Web SDK]-fil eller at.js-filen om din profil är utökad utanför standardvärdet.

Förfallodatumet återställs inte för befintliga profiler. Om en tidigare besökare inte återvänder på 15 dagar upphör den profilen att gälla. Om en tidigare besökare återgår innan den ursprungliga tvåveckorsprofilen går ut återställs profilen till den utökade livstiden. Alla nya besökarprofiler ställs in på den utökade profilens livstid.

I följande scenario antar du att en eller båda platserna implementeras med [!DNL Platform Web SDK]. Om båda platserna har en klientkod och en besökare besöker båda platserna, ställs profilen in på den senaste platsens livstid. Anta till exempel att Plats 1 har en livslängd på 84 dagar. Site 2 har en 14-dagars livstid. Om besökaren besöker Plats 1 och sedan Plats 2 upphör besökarprofilen att gälla om 14 dagars inaktivitet. Om besökaren besöker Plats 1 efter besök på Plats 2 kommer profilen att upphöra om 84 dagars inaktivitet.
