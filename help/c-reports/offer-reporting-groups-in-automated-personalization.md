---
keywords: automatiserad personalisering;erbjudande;rapportering;grupp;rapporteringsgrupp
description: Information om hur du använder rapportgrupper i Automated Personalization-aktiviteter (AP) i Adobe Target.
title: Erbjud rapportgrupper i Automated Personalization-aktiviteter (AP)
feature: Reports
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMOffer-rapporteringsgrupper i Automated Personalization{#offer-reporting-groups-in-automated-personalization}

Information om hur du använder rapporteringsgrupper i [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)-aktiviteter (AP).

Rapportgrupper utför två nyckelfunktioner:

* De gör att du kan se dina erbjudanden grupperade i en AP-aktivitetsrapportering.
* De spelar en nyckelroll med hur personaliseringsmodellerna [!DNL Target] fungerar.

När du använder rapporteringsgrupper skapar [!DNL Target] bara en personaliseringsmodell för varje rapporteringsgrupp i stället för varje erbjudande i din AP-aktivitet med hjälp av data från alla erbjudanden i den gruppen.

Om din aktivitetsinställning inte har tillräckligt med data för att en personaliseringsmodell ska kunna skapas per erbjudande kan rapporteringsgrupper bidra till att minska datakraven för att använda Automated Personalization. Rapporteringsgrupper kan också bidra till att lösa problemet med att&quot;komma igång&quot; med nya erbjudanden genom att gruppera liknande erbjudanden så att varje modell får mer data att utbilda. Modelleringsgrupper kan också användas för aktiviteter där nya erbjudanden regelbundet introduceras i din AP-aktivitet.

Detta fungerar bra om besökarna svarar på samma sätt som alla erbjudanden i en grupp. Det bästa sättet är att gruppera erbjudanden som liknande grupper av besökare svarar på på liknande sätt. Med andra ord, grupperbjudanden med liknande konverteringsgrader. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp. Att gruppera alla erbjudanden eller grupperingserbjudanden med mycket olika konverteringsgrader minskar troligen effekten av personaliseringsmodellerna [!DNL Target].

>[!NOTE]
>
>Om ett erbjudande tas bort eller ersätts från en viss modellgrupp tas även den historiska trafik som såg det erbjudandet bort från modellgruppen. Borttagna erbjudanden bidrar med andra ord inte till vilka data som används för [!DNL Target]-personaliseringsmodellerna för att lära sig.

**Så här ställer du in rapporteringsgrupper:**

1. Klicka på ikonen **[!UICONTROL Manage Content]** på sidan [!UICONTROL Experiences] för en AP-aktivitet.

   ![](assets/ap_manage_content.png)

1. Klicka på fliken **[!UICONTROL Offers]** högst upp i dialogrutan [!UICONTROL Manage Content].
1. (Villkorligt) Lägg till specifika upplevelser i en rapporteringsgrupp genom att hålla markören över önskat erbjudande och sedan klicka på mappikonen **[!UICONTROL Reporting Group]**.

   ![](assets/ap_manage_content_2.png)

1. (Villkorligt) Gruppera inkluderar upplevelser i en rapportgrupp genom att markera kryssrutan för relevanta upplevelser och sedan klicka på mappikonen **[!UICONTROL Reporting Group]** i dialogrutans övre högra hörn.

   ![](assets/ap_manage_content_3.png)

1. (Villkorligt) Om du vill tilldela det valda erbjudandet till en befintlig rapporteringsgrupp väljer du **[!UICONTROL Existing]**, väljer önskad rapporteringsgrupp i listrutan och klickar sedan på **[!UICONTROL Apply]**.

   eller

   Om du vill skapa en ny rapporteringsgrupp att tilldela det valda erbjudandet till väljer du **[!UICONTROL New]**, ger den nya rapporteringsgruppen ett namn och klickar sedan på **[!UICONTROL Apply]**.

   ![](assets/ap_reporting_groups.png)

