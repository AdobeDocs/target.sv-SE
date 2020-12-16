---
keywords: create experience;experience create;priority;audience;experience;visual experience composer
description: Adobe Target Visual Experience Composer (VEC) ger ett visuellt gränssnitt för att redigera upplevelser på din sida i en XT-aktivitet (Experience Targeting).
title: Skapa upplevelse
feature: xt
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 0%

---


# Skapa upplevelse{#create-experience}

[!UICONTROL Visual Experience Composer] (VEC) ger ett visuellt gränssnitt för redigering av upplevelser på sidan i en [!UICONTROL Experience Targeting] (XT)-aktivitet.

1. Markera elementen som du vill ändra och gör önskade ändringar.

   När [du skapar en XT-aktivitet](/help/c-activities/t-experience-target/t-xt-create/xt-create.md) visar steg ett av de guidade arbetsflödena i tre delar ([!UICONTROL Experiences]) standard [!UICONTROL Experience A] med en [!UICONTROL All Visitors]-målgrupp.

   ![Alla besökare](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Alla ändringar du gör gäller nu för Experience A. I ett steg nedan klickar du på **[!UICONTROL Add Experience Targeting]** för att skapa fler upplevelser.

   När du håller muspekaren över elementen på sidan markeras elementen. Alla markerade element kan ändras med VEC. En lista över åtgärder som kan utföras på ett element för att ändra upplevelsen finns i [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Om du skapade en [!DNL Target]-begäran på sidan med [!DNL Target Classic], visas [!DNL Target]-begäran som ett element som visar begäransnamnet och kan ändras som vilket element som helst.

   >[!NOTE]
   >
   >VEC tillåter som standard inte ändringar av element som innehåller JavaScript, t.ex. roterande banners. Du kan välja att inaktivera JavaScript för att ändra dessa element med hjälp av VEC.

1. Om du vill skapa fler upplevelser klickar du på **[!UICONTROL Add Experience Targeting]**.

   ![Länken Lägg till Experience Targeting](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   Dialogrutan [!UICONTROL Choose Audience] visas. Om du vill rikta en upplevelse till en viss målgrupp måste du välja målgrupp innan du kan lägga till en upplevelse.

   Målgruppsbiblioteket innehåller målgrupper som tidigare har definierats, inklusive några vanliga målgrupper som är förbyggda som en del av [!DNL Target]. Du kan välja en målgrupp i biblioteket eller [skapa en ny målgrupp](/help/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   När du skapar en målgrupp kan du välja en plats och ange parametrar för den platsen. Under [!UICONTROL Custom] (Skapa publik > Lägg till regel > Anpassad) markerar du platsen och anger önskade parametrar.

   >[!NOTE]
   >
   >Publiken importeras automatiskt i bakgrunden när du öppnar målgruppslistan och de importerade målgrupperna är mer än tio minuter gamla.

1. Välj en eller flera målgrupper att rikta in sig på med upplevelsen och klicka sedan på **[!UICONTROL Done]**.

   ![Upplevelse B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   Du kommer att märka att Experience B nu visas i föregående bild och att den här upplevelsen är inriktad på besökarna i USA.

1. Markera de element som du vill ändra för den här upplevelsen och gör önskade ändringar, vilket förklaras i steg 1 ovan.

1. Upprepa de föregående stegen för att skapa ytterligare målinriktade upplevelser efter behov.

1. Klicka på **[!UICONTROL Next]** när du är färdig med att designa dina upplevelser.

   Aktivitetsdiagrammet visar:

   ![XT Targeting-diagram](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Om du levererar en bild från en annan källa än huvudsidan (till exempel en bild som finns på `akamai.net` och som levereras `adobe.com`) visas inte den bilden i miniatyrbilden för sidan som visas i flödesdiagrammet.

1. (Villkorligt) Dra och släpp målgruppspar/upplevelsepar när du skapar eller redigerar XT-aktiviteter för att ordna paren i önskad ordning.

   Besökarna utvärderas utifrån upplevelser i ordning, uppifrån och ned.

   ![Flytta upplevelser](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL Experience Targeting] förutsätter att ordern är viktig. Om en besökare tillhör det första målgrupps-/upplevelseparet levereras den första upplevelsen.

   Anta till exempel att du inte var medveten om att ordern är viktig när du skapar en XT-aktivitet. När ni testar upptäcker ni senare att besökare som ni anser borde vara kvalificerade för upplevelserna B eller C i stället kvalificerar sig för upplevelsen A. Detta kan bero på att målgrupperna inte utesluter varandra och inte är i rätt ordning (till exempel upplevelsen A = USA, upplevelsen B = San Francisco och upplevelsen C = Kalifornien). I det här scenariot kvalificerar alla användare från USA sig för upplevelsen A, även om de befinner sig i San Francisco eller någon annanstans i Kalifornien. Du kan ändra ordning på målgruppspar/upplevelsepar från de mest restriktiva till de minst restriktiva (San Francisco > California > United States) utan att skapa om hela aktiviteten.

   Om du har en [!UICONTROL All Visitors]-målgrupp kontrollerar du att det inte är den första målgruppen i diagrammet. En upplevelse som är inriktad på&quot;Alla besökare&quot; kan användas som den sista upplevelsen i aktiviteten för målinriktning av upplevelser för att&quot;fånga&quot; besökare som inte har hamnat i någon annan upplevelse.

## Byta namn på eller redigera en upplevelse

Du kan klicka på ikonen [!UICONTROL Edit] (tre lodräta ellipser) för en upplevelse i en XT-aktivitet och välja bland följande alternativ, om det behövs:

* Byt namn
* Redigera

![Alternativ för att byta namn och redigera](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Ta bort en upplevelse

På sidan **[!UICONTROL Experiences]** (det första steget i det guidade arbetsflödet i tre steg) klickar du på de tre lodräta ellipserna > **[!UICONTROL Delete]**.

![Ta bort upplevelse](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicera en upplevelse

Du kan kopiera en upplevelse i en XT-aktivitet så att du kan göra mindre ändringar i den utan att behöva skapa en helt ny upplevelse.

På sidan **[!UICONTROL Experiences]** (det första steget i det guidade arbetsflödet i tre steg) klickar du på de tre lodräta ellipserna > **[!UICONTROL Duplicate]**.

![Dubblettupplevelse](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Utbildningsvideor:

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Från A/B-testning till Experience Targeting

I den här videon beskrivs hur A/B-testning går ett steg längre med Experience Targeting (XT).

* Beskriv det guidade arbetsflödet i tre steg för att konfigurera en XT-aktivitet
* Beskriv hur ni levererar platsspecifikt innehåll till målgrupper inom olika geografiska områden
* Beskriv hur ni ordnar om upplevelserna för att säkerställa att rätt innehåll levereras till rätt målgrupp

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Aktivitetstyper (9:03)

I den här videon förklaras vilka aktivitetstyper som finns i Target Standard/Premium. Experience Targeting diskuteras från 17:15.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Använda Visual Experience Composer

Den här videon innehåller information om hur du använder alternativen för Visual Experience Composer.

* Ändra innehållet på en sida
* Ändra layouten för en sida

>[!VIDEO](https://video.tv.adobe.com/v/17399)