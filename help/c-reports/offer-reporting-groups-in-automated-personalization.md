---
keywords: automated personalization;offer;reporting;group;reporting group
description: Information om hur du använder rapportgrupper i Automated Personalization-aktiviteter (AP) i Adobe Target.
title: Erbjud rapportgrupper i Automated Personalization-aktiviteter (AP) i Adobe Target
feature: null
topic: Advanced
uuid: 5b111a68-bd05-4ef1-8156-d064f2c7e257
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Erbjud rapporteringsgrupper i Automated Personalization{#offer-reporting-groups-in-automated-personalization}

Information om hur du använder rapportgrupper i [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) -aktiviteter.

Rapportgrupper utför två nyckelfunktioner:

* De gör att du kan se dina erbjudanden grupperade i en AP-aktivitetsrapportering.
* De spelar en viktig roll när det gäller hur personaliseringsmodellerna fungerar [!DNL Target] .

När du använder rapporteringsgrupper skapar [!DNL Target] bara en personaliseringsmodell för varje rapporteringsgrupp i stället för varje erbjudande i din AP-aktivitet med hjälp av data från alla erbjudanden i den gruppen.

Om din aktivitetsinställning inte har tillräckligt med data för att en personaliseringsmodell ska kunna skapas per erbjudande kan rapporteringsgrupper bidra till att minska datakraven för att använda Automated Personalization. Rapporteringsgrupper kan också bidra till att lösa problemet med att&quot;kalla igång&quot; för nya erbjudanden genom att gruppera liknande erbjudanden så att varje modell får mer data att utbilda sig på. Modelleringsgrupper kan också användas för aktiviteter där nya erbjudanden regelbundet introduceras i din AP-aktivitet.

Detta fungerar bra om besökarna svarar på samma sätt som alla erbjudanden i en grupp. Det bästa sättet är att gruppera erbjudanden som liknande grupper av besökare svarar på på liknande sätt. Med andra ord, grupperbjudanden med liknande konverteringsgrader. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp. Att gruppera alla erbjudanden eller grupperingserbjudanden med mycket olika konverteringsgrader minskar troligen personaliseringsmodellernas effektivitet [!DNL Target] .

>[!NOTE]
>
>Om ett erbjudande tas bort eller ersätts från en viss modellgrupp tas även den historiska trafik som såg det erbjudandet bort från modellgruppen. Borttagna erbjudanden bidrar med andra ord inte till vilka data som används för de personaliseringsmodeller som [!DNL Target] ska lära sig.

**Så här ställer du in rapporteringsgrupper:**

1. Klicka på [!UICONTROL Experiences] ikonen på **[!UICONTROL Manage Content]** sidan med en AP-aktivitet.

   ![](assets/ap_manage_content.png)

1. Klicka på **[!UICONTROL Offers]** fliken överst i [!UICONTROL Manage Content] dialogrutan.
1. (Villkorligt) Lägg till specifika upplevelser i en rapporteringsgrupp genom att hålla markören över önskat erbjudande och sedan klicka på **[!UICONTROL Reporting Group]** mappikonen.

   ![](assets/ap_manage_content_2.png)

1. (Villkorligt) Gruppera inkluderar upplevelser i en rapportgrupp genom att markera kryssrutan för de relevanta upplevelserna och sedan klicka på mappikonen i dialogrutans övre högra hörn genom att klicka på **[!UICONTROL Reporting Group]** .

   ![](assets/ap_manage_content_3.png)

1. (Villkorligt) Om du vill tilldela det valda erbjudandet till en befintlig rapporteringsgrupp väljer du **[!UICONTROL Existing]** den önskade rapporteringsgruppen i listrutan och klickar sedan på **[!UICONTROL Apply]**.

   eller

   Om du vill skapa en ny rapporteringsgrupp att tilldela det valda erbjudandet till väljer du **[!UICONTROL New]**, namnger den nya rapporteringsgruppen och klickar sedan på **[!UICONTROL Apply]**.

   ![](assets/ap_reporting_groups.png)

