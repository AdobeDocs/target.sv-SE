---
keywords: automatiserad personalisering;erbjudande;rapportering;grupp;rapporteringsgrupp;ap
description: Läs om hur du använder grupper för anbudsrapportering i [!DNL Adobe Target] [!UICONTROL Automated Personalization] verksamhet.
title: Kan jag använda rapporteringsgrupper i [!UICONTROL Automated Personalization] Verksamheter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# Erbjud rapportgrupper i [!UICONTROL Automated Personalization]

Information om hur du använder rapporteringsgrupper i [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) aktiviteter.

Rapportgrupper utför två nyckelfunktioner:

* Med rapportgrupper kan du se dina erbjudanden grupperade i AP-aktivitetsrapporter.
* Rapporteringsgrupper spelar en viktig roll när det gäller att [!DNL Target] funktionen för personaliseringsmodeller.

När du använder rapporteringsgrupper [!DNL Target] skapar en personaliseringsmodell för varje rapporteringsgrupp med hjälp av data från alla erbjudanden i gruppen. Utan rapporteringsgrupper [!DNL Target] skapar en personaliseringsmodell för varje erbjudande i din AP-aktivitet.

Om din aktivitetsinställning inte har tillräckligt med data för att en personaliseringsmodell ska kunna skapas per erbjudande hjälper rapportgrupper till att minska datakraven [!UICONTROL Automated Personalization]. Rapporteringsgrupper kan också bidra till att lösa problemet med att&quot;kalla igång&quot; för nya erbjudanden genom att gruppera liknande erbjudanden så att varje modell får mer data att utbilda sig på. Modelleringsgrupper kan också användas för aktiviteter där nya erbjudanden regelbundet introduceras i din AP-aktivitet.

Detta fungerar bra om besökarna svarar på samma sätt som alla erbjudanden i en grupp. Det bästa sättet är att gruppera erbjudanden som liknande grupper av besökare svarar på på liknande sätt. Med andra ord, grupperbjudanden med liknande konverteringsgrader. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp. Att gruppera alla erbjudanden eller grupperingserbjudanden med olika konverteringsgrader minskar troligen effekten av [!DNL Target] personaliseringsmodeller.

>[!NOTE]
>
>Om ett erbjudande tas bort eller ersätts från en viss modellgrupp tas även den historiska trafik som såg det erbjudandet bort från modellgruppen. Borttagna erbjudanden bidrar med andra ord inte till vilka data som används för [!DNL Target] personaliseringsmodeller att lära sig.

## Ställ in rapporteringsgrupper

1. På **[!UICONTROL Experiences]** sidan för en AP-aktivitet klickar du på **[!UICONTROL Manage Content]** -ikon.

   ![Ikonen Hantera innehåll](/help/main/c-reports/assets/ap_manage_content.png)

1. Klicka på **[!UICONTROL Offers]** överst på [!UICONTROL Manage Content] -dialogrutan.
1. (Villkorligt) Lägg till specifika upplevelser i en rapporteringsgrupp genom att hålla markören över önskat erbjudande och sedan klicka på **[!UICONTROL Reporting Group]** mappikon.

   ![Ikon för rapporteringsgrupp](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Villkorligt) Gruppera för att inkludera upplevelser i en rapporteringsgrupp genom att markera kryssrutorna för de relevanta upplevelserna och sedan klicka på **[!UICONTROL Reporting Group]** mappikon i dialogrutans övre högra hörn.

   ![Ikon för rapporteringsgrupp](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Om du vill tilldela ett valt erbjudande till en befintlig rapporteringsgrupp väljer du **[!UICONTROL Existing]** väljer du önskad rapportgrupp i listrutan och klickar sedan på **[!UICONTROL Apply]**.

   eller

   Om du vill skapa en rapporteringsgrupp att tilldela det valda erbjudandet till väljer du **[!UICONTROL New]**, namnge den nya rapporteringsgruppen och klicka sedan på **[!UICONTROL Apply]**.

   ![Ny ikon för att skapa en ny rapporteringsgrupp](/help/main/c-reports/assets/ap_reporting_groups.png)

Du kan använda [!UICONTROL Location] lista för att filtrera erbjudanden efter plats. Använd [!UICONTROL Report Group] lista som ska filtreras efter erbjudanden efter rapporteringsgrupper. Du kan också använda [!UICONTROL Report Group] lista att filtrera efter [!UICONTROL Unassigned Offers] så att ni kan tilldela en rapporteringsgrupp till ett erbjudande som för närvarande inte är tilldelat någon rapporteringsgrupp.

Mer information om att rikta ett erbjudande till specifika målgrupper finns i [Mål [!UICONTROL Automated Personalization] erbjudanden](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Caveats

* Det är viktigt att förstå att rapporteringsgrupper påverkar hur [!DNL Target] bygger sina modeller. Detta resulterar i [!DNL Adobe] rekommenderar att du endast använder rapporteringsgrupper om du tänker ersätta eller lägga till nya erbjudanden när en aktivitet är aktiv. Om ett nytt erbjudande införs i en liveaktivitet kan maskinen använda de data som redan samlats in för de andra erbjudandena i sin grupp för att lära sig mer om det nya erbjudandet genom att lägga in det nya erbjudandet i en grupp med befintliga liknande erbjudanden. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp.

* AP-aktiviteter har kombinationer av location+offer (modellables). När [!DNL Target] registrera uppgifter i rapporter, [!DNL Target] tar hänsyn till sådana kombinationer så att det är tydligt från vilken händelse (display, click o.s.v.) erbjudandet kom.

  En aktivitet kan till exempel ha flera platser och erbjudanden som överlappar varandra. Om en besökare ser mer än ett av dessa erbjudanden på olika platser, [!DNL Target] sparar endast data för dessa erbjudanden. Om samma besökare senare klickar på ett erbjudande, [!DNL Target] registrerar endast en händelse från den kombinationen (inte för alla kombinationer).

  Om klickningen kommer från en annan plats, som finns i ett mätresultat men inte visar något erbjudande, loggas händelsen under aktiviteten, men inte för någon kombination av erbjudande och plats. Därför visas inte erbjudandet i rapporteringsgruppen för erbjudanden.

  Detta beteende beror på att klickningen kan ha gjorts från en annan ruta och inte från den ruta som levererade erbjudandet. Därför är mätvärdet kopplat till aktiviteten, men inte till erbjudandet.

## Visa erbjudanden i en rapporteringsgrupp

1. Klicka **[!UICONTROL Activities]** klickar du på [!UICONTROL Automated Personalization] från listan och klicka sedan på **[!UICONTROL Reports]** för att visa [Erbjudandenivå](/help/main/c-reports/personalization-reports/reports-ap.md) rapport.

   Om du har många aktiviteter klickar du på [!UICONTROL Show Filters] (tratt) väljer du [!UICONTROL Automated Personalization] kryssrutan för att filtrera listan så att den bara visas [!UICONTROL Automated Personalization] verksamhet.

1. Klicka **[!UICONTROL Control]** eller **[!UICONTROL Targeted]** i tabellen för att visa ogrupperade erbjudanden och erbjudanden inuti rapporteringsgrupper.

   ![Erbjudandegrupper: Kontroll och målinriktning](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Mer information om hur du använder [!UICONTROL Automated Personalization] rapporter (inklusive [!UICONTROL Offer Level] rapport), se [Automated Personalization Sammanfattningsrapporter](/help/main/c-reports/personalization-reports/reports-ap.md).


