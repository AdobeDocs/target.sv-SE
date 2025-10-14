---
keywords: automatiserad personalisering;erbjudande;rapportering;grupp;rapporteringsgrupp;ap
description: Lär dig hur du använder rapporteringsgrupper i  [!DNL Adobe Target] [!UICONTROL Automated Personalization] aktiviteter.
title: Kan jag använda rapporteringsgrupper för erbjudanden i [!UICONTROL Automated Personalization] aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# Erbjud rapportgrupper i [!UICONTROL Automated Personalization]

Information om hur du använder rapporteringsgrupper i [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)-aktiviteter.

Rapportgrupper utför två nyckelfunktioner:

* Med rapportgrupper kan du se dina erbjudanden grupperade i AP-aktivitetsrapporter.
* Rapporteringsgrupper spelar en viktig roll med hur personaliseringsmodellerna i [!DNL Target] fungerar.

När du använder rapporteringsgrupper skapar [!DNL Target] en personaliseringsmodell för varje rapporteringsgrupp med hjälp av data från alla erbjudanden i den gruppen. Utan rapportgrupper skapar [!DNL Target] en personaliseringsmodell för varje erbjudande i din AP-aktivitet.

Om din aktivitetsinställning inte har tillräckligt med data för att en personaliseringsmodell ska kunna skapas per erbjudande hjälper rapportgrupper till att minska datakraven för att använda [!UICONTROL Automated Personalization]. Rapporteringsgrupper kan också bidra till att lösa problemet med att&quot;kalla igång&quot; för nya erbjudanden genom att gruppera liknande erbjudanden så att varje modell får mer data att utbilda sig på. Modelleringsgrupper kan också användas för aktiviteter där nya erbjudanden regelbundet introduceras i din AP-aktivitet.

Detta fungerar bra om besökarna svarar på samma sätt som alla erbjudanden i en grupp. Det bästa sättet är att gruppera erbjudanden som liknande grupper av besökare svarar på på liknande sätt. Med andra ord, grupperbjudanden med liknande konverteringsgrader. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp. Att gruppera alla erbjudanden eller grupperingserbjudanden med olika konverteringsgrader minskar troligen effekten av personaliseringsmodellerna i [!DNL Target].

>[!NOTE]
>
>Om ett erbjudande tas bort eller ersätts från en viss modellgrupp tas även den historiska trafik som såg det erbjudandet bort från modellgruppen. Borttagna erbjudanden bidrar med andra ord inte till vilka data som används för personaliseringsmodellerna [!DNL Target] att lära sig.

## Ställ in rapporteringsgrupper

1. Klicka på ikonen **[!UICONTROL Experiences]** ( **[!UICONTROL Manage Content]** ikonen Hantera innehåll![&#x200B; ) på sidan &#x200B;](/help/main/assets/icons/Experience.svg) i en AP-aktivitet.
1. Klicka på fliken **[!UICONTROL Offers]** högst upp i dialogrutan [!UICONTROL Manage Content].
1. (Villkorligt) Lägg till specifika upplevelser i en rapporteringsgrupp genom att klicka på ikonen [!UICONTROL More Actions] ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) för önskat erbjudande och sedan genom att klicka på **[!UICONTROL Reporting Group]**.

1. (Villkorligt) Gruppera inkluderar upplevelser i en rapportgrupp genom att markera kryssrutorna för de relevanta upplevelserna och sedan klicka på **[!UICONTROL Reporting Group]** längst ned i dialogrutan.

1. Om du vill tilldela det valda erbjudandet till en befintlig rapporteringsgrupp väljer du **[!UICONTROL Existing]**, väljer önskad rapporteringsgrupp i listrutan och klickar sedan på **[!UICONTROL Confirm]**.

   eller

   Om du vill skapa en rapporteringsgrupp som du kan tilldela det valda erbjudandet till väljer du **[!UICONTROL New]**, namnger den nya rapporteringsgruppen och klickar sedan på **[!UICONTROL Confirm]**.

Du kan använda listan [!UICONTROL Location] för att filtrera erbjudanden efter plats. Använd listan [!UICONTROL Report Group] för att filtrera erbjudanden efter rapporteringsgrupper. Du kan också använda listan [!UICONTROL Report Group] för att filtrera efter [!UICONTROL Unassigned Offers] så att du kan tilldela en rapporteringsgrupp till ett erbjudande som för närvarande inte är tilldelat någon rapporteringsgrupp.

Mer information om att rikta ett erbjudande till specifika målgrupper finns i [Mål [!UICONTROL Automated Personalization] erbjudanden](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Caveats

* Det är viktigt att förstå att rapportgrupper påverkar hur [!DNL Target] bygger sina modeller. Därför rekommenderar [!DNL Adobe] att du bara använder rapporteringsgrupper om du tänker ersätta eller lägga till nya erbjudanden medan en aktivitet är aktiv. Om ett nytt erbjudande införs i en liveaktivitet kan maskinen använda de data som redan samlats in för de andra erbjudandena i sin grupp för att lära sig mer om det nya erbjudandet genom att lägga in det nya erbjudandet i en grupp med befintliga liknande erbjudanden. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp.

* AP-aktiviteter har kombinationer av location+offer (modellables). När [!DNL Target] registrerar data i rapporter, undersöker [!DNL Target] sådana kombinationer så att det är tydligt från vilken händelse (visa, klicka och så vidare) erbjudandet kom.

  En aktivitet kan till exempel ha flera platser och erbjudanden som överlappar varandra. Om en besökare ser mer än ett av dessa erbjudanden på olika platser, registrerar [!DNL Target] endast data för dessa erbjudanden. Om samma besökare senare klickar på ett erbjudande registrerar [!DNL Target] endast en händelse från den kombinationen (inte för alla kombinationer).

  Om klickningen kommer från en annan plats, som finns i ett mätresultat men inte visar något erbjudande, loggas händelsen under aktiviteten, men inte för någon kombination av erbjudande och plats. Därför visas inte erbjudandet i rapporteringsgruppen för erbjudanden.

  Detta beteende beror på att klickningen kan ha gjorts från en annan ruta och inte från den ruta som levererade erbjudandet. Därför är mätvärdet kopplat till aktiviteten, men inte till erbjudandet.

## Visa erbjudanden i en rapporteringsgrupp

1. Klicka på **[!UICONTROL Activities]**, klicka på önskad [!UICONTROL Automated Personalization]-aktivitet i listan och klicka sedan på fliken **[!UICONTROL Reports]** för att visa rapporten [Erbjudandenivå](/help/main/c-reports/personalization-reports/reports-ap.md).

   Om du har många aktiviteter klickar du på ikonen [!UICONTROL Show Filters] (tratt) och markerar kryssrutan [!UICONTROL Automated Personalization] för att filtrera listan så att endast [!UICONTROL Automated Personalization] aktiviteter visas.

1. Klicka på **[!UICONTROL Control]** eller **[!UICONTROL Targeted]** i tabellen för att visa de ogrupperade erbjudandena och erbjudandena inuti rapporteringsgrupperna.

   ![Erbjudandegrupper: Kontroll och målinriktning](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Mer information om hur du använder [!UICONTROL Automated Personalization]-rapporter (inklusive [!UICONTROL Offer Level]-rapporten) finns i [Sammanfattningsrapporter för Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
