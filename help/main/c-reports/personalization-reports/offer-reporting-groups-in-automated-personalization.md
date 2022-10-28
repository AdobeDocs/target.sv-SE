---
keywords: automatiserad personalisering;erbjudande;rapportering;grupp;rapporteringsgrupp;ap
description: Lär dig hur du använder rapporteringsgrupper i Adobe [!DNL Target] [!UICONTROL Automated Personalization] verksamhet.
title: Kan jag använda rapporteringsgrupper i Automated Personalization-aktiviteter?
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 60655a93b515095bd8c67a4af2193d36789ab96e
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Erbjud rapportgrupper i [!UICONTROL Automated Personalization]

Information om hur du använder rapporteringsgrupper i [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) aktiviteter.

Rapportgrupper utför två nyckelfunktioner:

* Med rapportgrupper kan du se dina erbjudanden grupperade i AP-aktivitetsrapporter.
* Rapporteringsgrupper spelar en viktig roll när det gäller att [!DNL Target] funktionen för personaliseringsmodeller.

När du använder rapporteringsgrupper [!DNL Target] skapar en personaliseringsmodell för varje rapporteringsgrupp med hjälp av data från alla erbjudanden i gruppen. Utan rapporteringsgrupper [!DNL Target] skapar en personaliseringsmodell för varje erbjudande i din AP-aktivitet.

Om din aktivitetsinställning inte har tillräckligt med data för att en personaliseringsmodell ska kunna skapas per erbjudande, kan rapporteringsgrupper bidra till att minska datakraven [!UICONTROL Automated Personalization]. Rapporteringsgrupper kan också bidra till att lösa problemet med att&quot;komma igång&quot; med nya erbjudanden genom att gruppera liknande erbjudanden så att varje modell får mer data att utbilda. Modelleringsgrupper kan också användas för aktiviteter där nya erbjudanden regelbundet introduceras i din AP-aktivitet.

Detta fungerar bra om besökarna svarar på samma sätt som alla erbjudanden i en grupp. Det bästa sättet är att gruppera erbjudanden som liknande grupper av besökare svarar på på liknande sätt. Med andra ord, grupperbjudanden med liknande konverteringsgrader. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp. Att gruppera alla erbjudanden eller grupperingserbjudanden med mycket olika konverteringsgrader minskar troligen effekten av [!DNL Target] personaliseringsmodeller.

>[!NOTE]
>
>Om ett erbjudande tas bort eller ersätts från en viss modellgrupp tas även den historiska trafik som såg det erbjudandet bort från modellgruppen. Borttagna erbjudanden bidrar med andra ord inte till vilka data som används för [!DNL Target] personaliseringsmodeller att lära sig.

**Så här ställer du in rapporteringsgrupper:**

1. På **[!UICONTROL Experiences]** sidan för en AP-aktivitet klickar du på **[!UICONTROL Manage Content]** ikon.

   ![Ikonen Hantera innehåll](/help/main/c-reports/assets/ap_manage_content.png)

1. Klicka på **[!UICONTROL Offers]** överst på [!UICONTROL Manage Content] -dialogrutan.
1. (Villkorligt) Lägg till specifika upplevelser i en rapporteringsgrupp genom att hålla markören över önskat erbjudande och sedan klicka på **[!UICONTROL Reporting Group]** mappikon.

   ![Ikon för rapporteringsgrupp](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Villkorligt) Gruppera för att inkludera upplevelser i en rapporteringsgrupp genom att markera kryssrutan för relevanta upplevelser och sedan klicka på **[!UICONTROL Reporting Group]** mappikon i dialogrutans övre högra hörn.

   ![Ikon för rapporteringsgrupp](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Om du vill tilldela ett valt erbjudande till en befintlig rapporteringsgrupp väljer du **[!UICONTROL Existing]** väljer du önskad rapportgrupp i listrutan och klickar sedan på **[!UICONTROL Apply]**.

   eller

   Om du vill skapa en ny rapporteringsgrupp att tilldela det valda erbjudandet till väljer du **[!UICONTROL New]**, namnge den nya rapporteringsgruppen och klicka sedan på **[!UICONTROL Apply]**.

   ![Ny ikon för att skapa en ny rapporteringsgrupp](/help/main/c-reports/assets/ap_reporting_groups.png)
