---
keywords: rapport;rapporter;rapportering;Experience cloud solution;tidszon;tidszon;valuta;exkludera IPs;beräknad ökning av intäkter;ökning av intäkter;finkorniga prioriteringar;finkornig
description: Använd [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] som rapportkälla, ange standardtidszon och standardvalutaformat, lägg till IP-adresser som ska uteslutas från rapportering och mycket annat.
title: Hur konfigurerar jag rapporter i [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: ea9513c4310d13e1e7899aa7e228b4d7ecdf0748
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 0%

---

# Konfigurera rapportering i [!DNL Target]

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
>Observera att tidszonen, valutan och IP-adresserna som ska exkluderas gäller för aktiviteter som använder [!DNL Target] rapportering. De här inställningarna gäller inte för aktiviteter som använder [Analyser för mål (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) eller [!DNL Customer Journey Analytics] som rapportkälla.

![Rapporteringssida](/help/main/administrating-target/assets/reporting.png)

## Reporting Cloud Solution {#solution}

Ange alternativ som avgör vilka data som används för dina resultat och rapporter.

Välj rapportkälla för dina aktiviteter, antingen [!DNL Target], [!DNL Adobe Analytics], eller [!DNL Adobe Customer Journey Analytics]. Du kan också välja rapportkälla per aktivitet som en del av ett guidat arbetsflöde i tre delar när du skapar aktiviteten.

Tänk på följande när du väljer rapportkälla:

* **[!DNL Adobe Target]**: Om rapportkällan är inställd på **[!DNL Target]** här får du inte skapa eller aktivera en aktivitet som använder [!DNL Analytics] eller [!DNL Customer Journey Analytics] som rapportkälla. Du måste ändra rapportkällan till **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Analytics]**: Om rapportkällan är inställd på **[!DNL Analytics]** här får du inte skapa eller aktivera en aktivitet som använder [!DNL Target] eller [!DNL Customer Journey Analytics] som rapportkälla. Du måste ändra rapportkällan till **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Customer Journey Analytics]**: Om rapportkällan är inställd på **[!DNL Customer Journey Analytics]** här får du inte skapa eller aktivera en aktivitet som använder [!DNL Target] eller [!DNL Analytics] som rapportkälla. Du måste ändra rapportkällan till **[!UICONTROL Select per activity]**.
* **Välj per aktivitet**: Om rapportkällan är inställd på **[!UICONTROL Select per activity]** Här kan du skapa och aktivera aktiviteter som stöds av den valda rapportkällan.

Tänk på följande när du bestämmer rapportkällan:

* **[!DNL Analytics]**: För en matris med aktiviteter som stöds med [!DNL Analytics] som rapportkälla (A4T), se [Aktivitetstyper som stöds](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics som rapportkälla för Adobe Target (A4t)*.

  [!UICONTROL Automated Personalization] (AP) skapande och aktivering av aktivitet tillåts oavsett vilken rapportkälla som valts. [!UICONTROL Automated Personalization] aktiviteter stöds inte när du väljer [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  Även om du anger [!DNL Analytics] som rapportkälla, [!DNL Target] används som rapportkälla för [!DNL Automated Personalization] verksamhet.

* **[!DNL Customer Journey Analytics]**: För en matris med aktiviteter som stöds med [!DNL Target] rapportering i [!DNL Customer Journey Analytics], se [Aktivitetstyper som stöds](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) in *[!DNL Target]rapportering i[!DNL Adobe Customer Journey Analytics]*.

  [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate]och [!UICONTROL Auto-Target] skapande och aktivering av aktivitet tillåts oavsett vilken rapportkälla som valts. Dessa aktiviteter stöds inte när du väljer [Adobe Customer Journey Analytics som rapportkälla](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  Även om du anger [!DNL Customer Journey Analytics] som rapportkälla, [!DNL Target] används som rapportkälla för [!DNL Automated Personalization] verksamhet.

  Om du anger [!DNL Customer Journey Analytics] som rapportkälla för [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target] verksamhet, [!DNL Target] eller [!DNL Analytics] kan användas som rapportkälla.

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
