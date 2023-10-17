---
keywords: rapport;rapporter;rapportering;Experience cloud solution;tidszon;tidszon;valuta;exkludera IPs;beräknad ökning av intäkter;ökning av intäkter;finkorniga prioriteringar;finkornig
description: Använd [!DNL Target] eller Adobe Analytics som rapportkälla, ange standardtidszon och standardvalutaformat, lägg till IP-adresser som ska uteslutas från rapportering med mera.
title: Hur konfigurerar jag rapportering i Target?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: d414f1554e1875e873f1ce557a7edf86b88ee79e
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 0%

---

# Konfigurera rapportering i mål

Konfigurera allmänna inställningar att använda i [!DNL Adobe Target] som gäller för hela [!DNL Target] konto.

Så här öppnar du [!UICONTROL Reporting] konfigurationssida, klicka på **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Du kan ange följande inställningar på den här sidan:

* Den Adobe Experience Cloud-lösning som ska användas för rapportering
* Tidszonen som ska användas för rapportering
* Valutan som ska användas för rapportering
* IP-adresser som ska uteslutas från rapportering
* Anger om en uppskattad ökning av intäkterna ska visas vid rapportering
* Om finjusterade prioriteringar ska aktiveras

>[!NOTE]
>
>Observera att tidszonen, valutan och IP-adresserna som ska exkluderas gäller för aktiviteter som använder [!DNL Target] rapportering. De här inställningarna gäller inte för aktiviteter som använder [Analyser för mål (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) som rapportkälla.

![Rapporteringssida](/help/main/administrating-target/assets/reporting.png)

## Reporting Cloud Solution {#solution}

Ange alternativ som avgör vilka data som används för dina resultat och rapporter.

Välj rapportkälla för dina aktiviteter, antingen [!DNL Target] eller [!DNL Adobe Analytics]. Du kan också välja att välja rapportkälla per aktivitet.

Tänk på följande när du väljer rapportkälla:

* Om rapportkällan är inställd på **[!DNL Target]** här får du inte aktivera en aktivitet som använder [!DNL Analytics] som rapportkälla. Du måste ändra rapportkällan till [!DNL Target] i din aktivitet eller ändra rapportkällan till **[!UICONTROL Select per activity]** in **[!UICONTROL Administration]>[!UICONTROL Reporting]**.
* Om rapportkällan är inställd på **[!DNL Analytics]** här får du inte aktivera en aktivitet som använder [!DNL Target] som rapportkälla (rapportkällan anges som **[!UICONTROL Target per activity])**. Du måste ändra rapportkällan till [!DNL Analytics] i din aktivitet eller ändra rapporteringsmotorn till **[!UICONTROL Select per activity]** in **[!UICONTROL Administration]>[!UICONTROL Reporting]**.
* Om rapportkällan är inställd på **[!UICONTROL Select per activity]** Här kan du skapa, aktivera och inaktivera aktiviteter som stöds av den valda rapportkällan. En matris med aktiviteter som stöds finns på [Aktivitetstyper som stöds](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics som rapportkälla för Adobe Target (A4t)*.
* [!UICONTROL Automated Personalization] (AP) skapande, aktivering och inaktivering av aktivitet tillåts oavsett vilken rapportkälla som valts. Automated Personalization-aktiviteter stöds inte när du väljer [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md). Även om du anger [!DNL Analytics] som rapportkälla, [!DNL Target] används som rapporteringskälla för Automated Personalization-aktiviteter. Mer information finns i [Aktivitetstyper som stöds](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics som rapportkälla för Adobe Target (A4t)*.

## Tidszon för rapportering

Ange den tidszon som ska användas för rapportering.

## Valuta för rapportering

Ange valutan som ska användas för rapportering.

## IP-adresser att undanta från [!DNL Target] rapporteringsdata

Ange de IP-adresser som du vill utesluta från rapportdata. Att utesluta interna företagsadresser är till exempel ett bra sätt att se till att dina rapporteringsdata återspeglar kundinteraktioner på din webbplats.

Ange varje IP-adress på en ny rad.

## Visa uppskattad ökning av intäkter

Du kan välja att visa den beräknade ökningen av intäkterna om du anger ett penningvärde för ditt mål. [!DNL Target] kan beräkna den vinst du skulle uppnå om alla användare såg den vinnande upplevelsen. Den uppskattade lyftfunktionen är inaktiverad som standard.

Endast [!DNL Experience Cloud] Administratörsanvändare kan aktivera eller inaktivera den här funktionen. Om den uppskattade höjden är inaktiverad visas inte motsvarande fält i gränssnittet. Om du inaktiverar funktionen går det inte att förlora data, inklusive data som används för dina uppskattningar. Beräkningarna baseras på data som samlas in oavsett om funktionen är aktiverad eller inte.

Mer information finns i [Uppskattar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Aktivera finkorniga prioriteringar

Tillåt numeriska värden för prioritet från 0-999.

Beroende på dina inställningar varierar gränssnittet och alternativen för prioritet. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.
