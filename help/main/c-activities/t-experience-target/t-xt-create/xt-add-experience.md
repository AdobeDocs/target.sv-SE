---
keywords: skapa upplevelse;upplevelseskapa;prioritet;målgrupp;upplevelse;kompositör för visuell upplevelse
description: Lär dig hur du använder  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) för att skapa och redigera upplevelser på din sida i en [!UICONTROL Experience Targeting] (XT)-aktivitet.
title: Hur skapar jag upplevelser i en [!UICONTROL Experience Targeting]-aktivitet?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 0%

---

# Skapa upplevelse i [!UICONTROL Experience Targeting] (XT)-aktiviteter

[!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] tillhandahåller ett visuellt gränssnitt för redigering av upplevelser på din sida i en [!UICONTROL Experience Targeting] (XT)-aktivitet.

1. Markera elementen som du vill ändra och gör önskade ändringar.

   När [skapar en [!UICONTROL Experience Targeting] aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) visar steg ett av de guidade arbetsflödena i tre delar ([!UICONTROL Experiences]) standardvärdet [!UICONTROL Experience A] med en [!UICONTROL All Visitors]-målgrupp.

   ![Alla besökare](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors-new.png)

   Alla ändringar du gör gäller nu för [!UICONTROL Experience A]. I ett steg nedan klickar du på **[!UICONTROL Add Experience Targeting]** för att skapa fler upplevelser.

   När du håller muspekaren över elementen på sidan markeras elementen. Alla markerade element kan ändras med VEC. En lista över åtgärder som kan utföras på ett element för att ändra upplevelsen finns i [Alternativ för visuell Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >VEC tillåter som standard inte ändringar av element som innehåller JavaScript, t.ex. roterande banderoller. Du kan inaktivera JavaScript för att ändra dessa element med hjälp av VEC.

1. Om du vill skapa fler upplevelser klickar du på **[!UICONTROL Add]** ( ![Lägg till knapp](/help/main/assets/icons/Add.svg) ).

   Dialogrutan [!UICONTROL Add Audience] visas. Om du vill rikta en upplevelse till en viss målgrupp väljer du målgruppen innan du lägger till upplevelsen.

   Målgruppsbiblioteket innehåller målgrupper som tidigare har definierats, inklusive några vanliga målgrupper som är fördefinierade som en del av [!DNL Target]. Du kan välja en målgrupp i biblioteket eller [skapa en ny målgrupp](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa kombinerade målgrupper on demand i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   När du skapar en målgrupp kan du välja en plats och ange parametrar för den platsen. Under [!UICONTROL Custom] ([!UICONTROL Create Audience] > [!UICONTROL Custom]) markerar du platsen och anger önskade parametrar.

   >[!NOTE]
   >
   >Publiken importeras automatiskt i bakgrunden när du öppnar målgruppslistan och de importerade målgrupperna är mer än tio minuter gamla.

1. Välj en eller flera målgrupper att rikta in sig på med upplevelsen och klicka sedan på **[!UICONTROL Assign Audience]**.

   Experience B visas nu i föregående bild och den här upplevelsen är riktad till rätt målgrupp.

1. Markera de element som du vill ändra för den här upplevelsen och gör de önskade ändringarna enligt beskrivningen i steg 1 ovan.

1. Upprepa de föregående stegen för att skapa ytterligare målinriktade upplevelser efter behov.

1. Klicka på **[!UICONTROL Next]** när du är klar med att utforma dina upplevelser.

   Aktivitetsdiagrammet visar:

   ![XT-måldiagram](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-refresh.png)

   >[!NOTE]
   >
   >Du kan leverera en bild från en annan källa än huvudsidan (till exempel en bild som finns på `akamai.net` och levereras `adobe.com`). Bilder som finns på en annan plats visas inte i miniatyrbilden av sidan som visas i flödesdiagrammet.

1. (Villkorligt) Dra-och-släpp målgruppspar och upplevelsepar när du skapar eller redigerar [!UICONTROL Experience Targeting]-aktiviteter för att ordna paren i önskad ordning.

   Klicka på ikonen Ändra ordning ( ![ikonen Ändra ordning &#x200B;](/help/main/assets/icons/Reorder.svg) ) för att visa kolumnen [!UICONTROL Experiences] till höger och sedan ordna om upplevelserna efter behov.

   Besökarna utvärderas utifrån upplevelser i ordning, uppifrån och ned.

   [!UICONTROL Experience Targeting] antar att beställningen är viktig. Om en besökare faller på det första målgrupps- och upplevelseparet levereras den första upplevelsen.

   Anta till exempel att du inte var medveten om att ordern är viktig när du skapar en [!UICONTROL Experience Targeting]-aktivitet. När ni testar upptäcker ni senare att besökare som ni anser borde vara kvalificerade för upplevelserna B eller C i stället kvalificerar sig för upplevelsen A. Denna situation kan bero på att målgrupperna inte utesluter varandra och inte är i rätt ordning (till exempel upplevelsen A = USA, upplevelsen B = San Francisco och upplevelsen C = Kalifornien). I det här scenariot kvalificerar alla användare från USA sig för upplevelsen A, även om de befinner sig i San Francisco eller någon annanstans i Kalifornien. Du kan ändra ordning på målgruppspar och upplevda par från de mest restriktiva till de minst restriktiva (San Francisco > California > United States) utan att återskapa hela aktiviteten.

   Om du har en [!UICONTROL All Visitors]-målgrupp kontrollerar du att det inte är den första målgruppen i diagrammet. En upplevelse som är riktad till [!UICONTROL All Visitors] kan användas som den sista upplevelsen i [!UICONTROL Experience Targeting]-aktiviteten för att&quot;fånga&quot; besökare som inte har hamnat i någon annan upplevelse.

## Byta namn på, redigera, duplicera eller ta bort en upplevelse

Klicka på en upplevelse i diagrammet i en [!UICONTROL Experience Targeting]-aktivitet för att visa kolumnen [!UICONTROL Experiences] till höger.

![Alternativ för att byta namn och redigera](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-refresh.png)

Välj bland följande alternativ efter behov:

* **[!UICONTROL Rename]**: Skriv det önskade namnet i fältet [!UICONTROL Name].
* **[!UICONTROL Edit]**: Klicka på ikonen Redigera ( ![ikonen Redigera](/help/main/assets/icons/Edit.svg) ) och gör sedan önskade ändringar.
* **[!UICONTROL Duplicate]**: Kopiera en upplevelse i en [!UICONTROL Experience Targeting]-aktivitet så att du kan göra mindre ändringar i den utan att behöva återskapa hela upplevelsen. Klicka på ikonen [!UICONTROL Duplicate] ( ![ikonen Duplicera &#x200B;](/help/main/assets/icons/Duplicate.svg) ) och redigera sedan upplevelsen efter behov.
* **[!UICONTROL Delete]**: Klicka på ikonen [!UICONTROL Delete] (![Ta bort ikon](/help/main/assets/icons/Delete.svg) ) och bekräfta sedan borttagningen.

## Utbildningsvideor:

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Från A/B-testning till [!UICONTROL Experience Targeting]

I den här videon beskrivs hur A/B-testning går till nästa nivå med [!UICONTROL Experience Targeting] (XT).

* Beskriv det guidade arbetsflödet i tre steg för att konfigurera en [!UICONTROL Experience Targeting]-aktivitet
* Beskriv hur ni levererar platsspecifikt innehåll till målgrupper inom olika geografiska områden
* Beskriv hur ni ordnar om upplevelserna för att säkerställa att rätt innehåll levereras till rätt målgrupp

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Aktivitetstyper (9:03)

I den här videon förklaras de aktivitetstyper som är tillgängliga i [!DNL Target]. [!UICONTROL Experience Targeting] diskuteras med början vid 5:15.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Använda [!UICONTROL Visual Experience Composer]

Den här videon innehåller information om hur du använder alternativen för [!UICONTROL Experience Targeting] (VEC).

* Ändra innehållet på en sida
* Ändra layouten för en sida

>[!VIDEO](https://video.tv.adobe.com/v/17399)
