---
keywords: mvt;multivariata test;platsavgiftsrapport
description: Lär dig hur du använder platsbidragsrapporten för Adobe [!DNL Target] [!UICONTROL Experience Targeting]-aktiviteter som visar prestanda för varje element och varje erbjudande.
title: Hur använder jag [!UICONTROL Location Contribution]-rapporten för [!UICONTROL Multivariate Test]-aktiviteter?
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: 6f70ff18cfbee5c02e6bb2bd345acbd2e1b2006f
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# [!UICONTROL Location Contribution]-rapport (MVT)

Rapporten [!UICONTROL Location Contribution] visar prestanda för varje element och varje erbjudande.

I rapportens övre del visas mätvärden, start- och slutdatum samt målgrupp som används i rapporten. Du kan ändra någon av dessa faktorer.

>[!NOTE]
>
>Tänk på följande information när du arbetar med rapporten [!UICONTROL Location Contribution]:
>
>* Publiken och mätväljarna är bara tillgängliga om [!DNL Analytics] används som rapportkälla (A4T).
>
>* Data för [!UICONTROL Location Contribution]-rapporten hämtas från [!DNL Target]-serverdelen även om aktiviteten har konfigurerats att använda [!UICONTROL Analytics as the reporting source] (A4T).
>
>* Data för rapporten [!UICONTROL Location Contribution] hämtas för produktionsmiljön även om en annan standardmiljö har definierats på kontonivån [!DNL Target].

Rapporten [!UICONTROL Location Contribution] innehåller två tabeller.

Den första tabellen visar den relativa effekten av varje element. I den här tabellen visas vilka av de element du har lagt till erbjudanden som ger flest konverteringar.

![Platsbidragsrapport i Adobe Target](/help/main/c-reports/assets/locationcontributiontop.png)

Den andra tabellen innehåller en rapport på erbjudandenivå. Den visar konverteringsgraden, lyften och förtroendet för varje erbjudande i varje enskilt element. Tabellen hjälper dig att avgöra vilka erbjudanden som är mest framgångsrika. I den andra kolumnen visas värden för det valda måttet (konverteringsgrad, RPV, AOV, order eller interaktionsmått) för erbjudandet och en standardisering.

![Platsbidragsrapport i Adobe Target](/help/main/c-reports/assets/locationcontributionbottom.png)

## Utbildningsvideo: Skapa ett MVT-test ![självstudiekursetikett](/help/main/assets/tutorial.png)

I den här videon visas hur du skapar ett multivariata test med det guidade arbetsflödet i tre steg för Target. Platsbidragsrapporten beskrivs från och med 08:45.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
