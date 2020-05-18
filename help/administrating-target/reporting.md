---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Konfigurera Adobe Target Visual Experience Composer (VEC) genom att ange dess allmänna inställningar, konfiguration av mobilvisningsruta och CSS-väljare.
title: Konfigurera rapportering i Adobe Target
topic: Standard
translation-type: tm+mt
source-git-commit: 34c4c48602df8550287e86c535ebc350fe2185f7
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---


# Konfigurera rapportering i mål

Konfigurera allmänna inställningar som ska användas i Target-rapportering för hela ditt [!DNL Target] konto.

Du öppnar konfigurationssidan genom att klicka [!UICONTROL Reporting] > **[!UICONTROL Administration]** **[!UICONTROL Reporting].**

Du kan ange följande inställningar på den här sidan:

* Adobe Experience Cloud-lösningen som ska användas för rapportering
* Tidszonen som ska användas för rapportering
* Valutan som ska användas för rapportering
* IP-adresser som ska uteslutas från rapportering
* Anger om en uppskattad ökning av intäkterna ska visas vid rapportering
* Om finjusterade prioriteringar ska aktiveras

![Rapporteringssida](/help/administrating-target/assets/reporting.png)

## Reporting Cloud Solution

Ange alternativ som avgör vilka data som används för dina resultat och rapporter.

Välj rapportkälla för dina aktiviteter, antingen [!DNL Target] eller Adobe Analytics. Du kan också välja att välja rapportkälla per aktivitet.

Tänk på följande när du väljer rapportkälla:

* [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] (AP) kan användas för att skapa, aktivera och inaktivera aktiviteter oavsett vilken rapportkälla som valts. Dessa aktivitetstyper stöds inte när du väljer [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Även om du anger Analytics som rapportkälla används det som rapportkälla för [!DNL Target] de här aktivitetstyperna.
* Om rapportkällan är inställd på Analytics (Analys) här, får du inte aktivera en aktivitet som använder [!DNL Target] som rapportkälla (rapportkällan anges som Target per aktivitet). Du måste ändra rapportkällan till Analytics i din aktivitet eller ändra rapporteringsmotorn till Select Per Activity (Välj per aktivitet) i Inställningar > Inställningar.
* Om rapportkällan anges [!DNL Target] här får du inte aktivera en aktivitet som använder Analytics som rapportkälla. Du måste ändra rapportkällan till [!DNL Target] i din aktivitet eller ändra rapportkällan till Välj per aktivitet i Inställningar > Inställningar.
* Om rapportkällan är inställd på Välj per aktivitet här kan du skapa, aktivera och inaktivera aktiviteter som stöds av den valda rapportkällan. En matris med aktiviteter som stöds finns i [Adobe Analytics som rapportkälla för Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* När du växlar från A/B-handbok till [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target]försvinner alla mätvärden och rapportmålgrupper om rapportkällan för A/B-handboken inte stöds i [!UICONTROL Auto-Allocate] - eller [!UICONTROL Auto-Target] -aktiviteter.

## Tidszon för rapportering

Ange den tidszon som ska användas för rapportering.

## Valuta för rapportering

Ange valutan som ska användas för rapportering.

## IP-adresser som ska uteslutas från målrapporteringsdata

Ange de IP-adresser som du vill utesluta från rapportdata. Att utesluta interna företagsadresser är till exempel ett bra sätt att se till att dina rapporteringsdata återspeglar kundinteraktioner på din webbplats.

Ange varje IP-adress på en ny rad.

## Visa uppskattad ökning av intäkter

Du kan välja att visa den beräknade ökningen av intäkterna om du anger ett penningvärde för ditt mål. [!DNL Target] kan beräkna den vinst du skulle uppnå om alla användare såg den vinnande upplevelsen. Den uppskattade lyftfunktionen är inaktiverad som standard.

Endast Experience Cloud Admin-användare kan aktivera eller inaktivera den här funktionen. Om den uppskattade höjden är inaktiverad visas inte motsvarande fält i gränssnittet. Om du inaktiverar funktionen går det inte att förlora data, inklusive data som används för dina uppskattningar. Beräkningarna baseras på data som samlas in oavsett om funktionen är aktiverad eller inte.

Mer information finns i [Beräkna Lyft i intäkter](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Aktivera finkorniga prioriteringar

Tillåt numeriska värden för prioritet från 0-999.

Beroende på dina inställningar varierar gränssnittet och alternativen för prioritet. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.
