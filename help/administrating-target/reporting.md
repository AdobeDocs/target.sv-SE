---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Konfigurera allmänna inställningar som ska användas i Adobe Target-rapporter för hela Target-kontot. Du kan konfigurera Adobe Experience Cloud-lösningen så att den används för rapportering (mål eller analys), tidszon och valutaformat för rapportering, IP-adresser som ska uteslutas från rapportering och om den beräknade ökningen av intäkter och finjusterade prioriteringar ska visas vid rapportering.
title: Konfigurera rapportering i Adobe Target
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---


# Konfigurera rapportering i mål

Konfigurera allmänna inställningar som ska användas i [!DNL Adobe Target]-rapporter som gäller för hela ditt [!DNL Target]-konto.

Om du vill komma åt konfigurationssidan [!UICONTROL Reporting] klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Du kan ange följande inställningar på den här sidan:

* Den Adobe Experience Cloud-lösning som ska användas för rapportering
* Tidszonen som ska användas för rapportering
* Valutan som ska användas för rapportering
* IP-adresser som ska uteslutas från rapportering
* Anger om en uppskattad ökning av intäkterna ska visas vid rapportering
* Om finjusterade prioriteringar ska aktiveras

>[!NOTE]
>
>Observera att tidszonen, valutan och IP-adresserna som ska exkluderas gäller för aktiviteter som använder [!DNL Target]-rapportering. Dessa inställningar gäller inte för aktiviteter som använder [Analytics för Target (A4T)] som rapportkälla (/help/c-integrating-target-with-mac/a4t/a4t.md).

![Rapporteringssida](/help/administrating-target/assets/reporting.png)

## Reporting Cloud Solution

Ange alternativ som avgör vilka data som används för dina resultat och rapporter.

Välj rapportkälla för dina aktiviteter, antingen [!DNL Target] eller [!DNL Adobe Analytics]. Du kan också välja att välja rapportkälla per aktivitet.

Tänk på följande när du väljer rapportkälla:

* Om rapportkällan är **[!DNL Target]** här, får du inte aktivera en aktivitet som använder [!DNL Analytics] som rapportkälla. Du måste ändra rapportkällan till [!DNL Target] i aktiviteten eller ändra rapportkällan till **[!UICONTROL Select per activity]** i **[!UICONTROL Administration]>[!UICONTROL Reporting]**.
* Om rapporteringskällan är **[!DNL Analytics]** här tillåts du inte aktivera en aktivitet som använder [!DNL Target] som rapportkälla (rapportkällan är **[!UICONTROL Target per activity])**. Du måste ändra rapportkällan till [!DNL Analytics] i aktiviteten eller ändra rapporteringsmotorn till **[!UICONTROL Select per activity]** i **[!UICONTROL Administration]>[!UICONTROL Reporting]**.
* Om rapportkällan är **[!UICONTROL Select per activity]** här kan du skapa, aktivera och inaktivera aktiviteter som stöds av den valda rapportkällan. En matris med aktiviteter som stöds finns i [Aktivitetstyper som stöds](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) i *Adobe Analytics som rapportkälla för Adobe Target (A4t)*.
* [!UICONTROL Automated Personalization] (AP) skapande, aktivering och inaktivering av aktivitet tillåts oavsett vald rapportkälla. Automated Personalization-aktiviteter stöds inte när du väljer [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Även om du anger [!DNL Analytics] som rapportkälla används [!DNL Target] som rapportkälla för Automated Personalization-aktiviteter. Mer information finns i [Aktivitetstyper som stöds](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) i *Adobe Analytics som rapportkälla för Adobe Target (A4t)*.

## Tidszon för rapportering

Ange den tidszon som ska användas för rapportering.

## Valuta för rapportering

Ange valutan som ska användas för rapportering.

## IP-adresser som ska uteslutas från målrapporteringsdata

Ange de IP-adresser som du vill utesluta från rapportdata. Att utesluta interna företagsadresser är till exempel ett bra sätt att se till att dina rapporteringsdata återspeglar kundinteraktioner på din webbplats.

Ange varje IP-adress på en ny rad.

## Visa uppskattad ökning av intäkter

Du kan välja att visa den beräknade ökningen av intäkterna om du anger ett penningvärde för ditt mål. [!DNL Target] kan beräkna den vinst du skulle uppnå om alla användare såg den vinnande upplevelsen. Den uppskattade lyftfunktionen är inaktiverad som standard.

Endast [!DNL Experience Cloud]-administratörsanvändare kan aktivera eller inaktivera den här funktionen. Om den uppskattade höjden är inaktiverad visas inte motsvarande fält i gränssnittet. Om du inaktiverar funktionen går det inte att förlora data, inklusive data som används för dina uppskattningar. Beräkningarna baseras på data som samlas in oavsett om funktionen är aktiverad eller inte.

Mer information finns i [Beräkna Lyft i intäkt](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Aktivera finkorniga prioriteringar

Tillåt numeriska värden för prioritet från 0-999.

Beroende på dina inställningar varierar gränssnittet och alternativen för prioritet. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.
