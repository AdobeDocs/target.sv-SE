---
keywords: skapa upplevelse;upplevelseskapa;prioritet;målgrupp;upplevelse;kompositör för visuell upplevelse
description: Lär dig använda [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) för att skapa och redigera upplevelser på din sida i en [!UICONTROL Experience Targeting] (XT) aktivitet.
title: Hur skapar jag upplevelser i en [!UICONTROL Experience Targeting] Aktivitet?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# Skapa upplevelser i [!UICONTROL Experience Targeting] (XT) aktiviteter

The [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] har ett visuellt gränssnitt för redigering av upplevelser på din sida i en [!UICONTROL Experience Targeting] (XT) aktivitet.

1. Markera elementen som du vill ändra och gör önskade ändringar.

   while [skapa [!UICONTROL Experience Targeting] aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), steg ett av de guidade arbetsflödena i tre delar ([!UICONTROL Experiences]) visas standard [!UICONTROL Experience A] med [!UICONTROL All Visitors] målgrupp.

   ![Alla besökare](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Alla ändringar du gör nu gäller för [!UICONTROL Experience A]. I ett steg nedan klickar du **[!UICONTROL Add Experience Targeting]** för att skapa fler upplevelser.

   När du håller muspekaren över elementen på sidan markeras elementen. Alla markerade element kan ändras med VEC. En lista över åtgärder som kan utföras på ett element för att ändra upplevelsen finns i [Alternativ för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >VEC tillåter som standard inte ändringar av element som innehåller JavaScript, t.ex. roterande banners. Du kan inaktivera JavaScript för att ändra dessa element med hjälp av VEC.

1. Om du vill skapa fler upplevelser klickar du på **[!UICONTROL Add Experience Targeting]**.

   ![Länken Lägg till Experience Targeting](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL Add Audience] visas. Om du vill rikta en upplevelse till en viss målgrupp väljer du målgruppen innan du lägger till upplevelsen.

   Målgruppsbiblioteket innehåller målgrupper som tidigare har definierats, inklusive några vanliga målgrupper som är färdigbyggda som en del av [!DNL Target]. Du kan välja en målgrupp i biblioteket eller [skapa en ny målgrupp](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   När du skapar en målgrupp kan du välja en plats och ange parametrar för den platsen. Under [!UICONTROL Custom] ([!UICONTROL Create Audience] > [!UICONTROL Custom]) väljer du platsen och anger önskade parametrar.

   >[!NOTE]
   >
   >Publiken importeras automatiskt i bakgrunden när du öppnar målgruppslistan och de importerade målgrupperna är mer än tio minuter gamla.

1. Välj en eller flera målgrupper att inrikta sig på med upplevelsen och klicka sedan på **[!UICONTROL Done]**.

   ![Upplevelse B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   Experience B visas nu i föregående bild och den här upplevelsen är inriktad på besökarna i USA.

1. Markera de element som du vill ändra för den här upplevelsen och gör de önskade ändringarna enligt beskrivningen i steg 1 ovan.

1. Upprepa de föregående stegen för att skapa ytterligare målinriktade upplevelser efter behov.

1. Klicka **[!UICONTROL Next]** när ni är färdiga med att designa era upplevelser.

   Aktivitetsdiagrammet visar:

   ![XT Targeting-diagram](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Du kan leverera en bild från en annan källa än huvudsidan (till exempel en bild som finns på `akamai.net` och levereras den `adobe.com`). Bilder som finns på en annan plats visas inte i miniatyrbilden av sidan som visas i flödesdiagrammet.

1. (Villkorligt) Dra och släpp målgrupps- och upplevelsepar när du skapar eller redigerar [!UICONTROL Experience Targeting] aktiviteter för att ordna paren i önskad ordning.

   Besökarna utvärderas utifrån upplevelser i ordning, uppifrån och ned.

   ![Flytta upplevelser](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL Experience Targeting] förutsätter att ordern är viktig. Om en besökare faller på det första målgrupps- och upplevelseparet levereras den första upplevelsen.

   Anta till exempel att du inte var medveten om att ordern är viktig när du skapar en [!UICONTROL Experience Targeting] aktivitet. När ni testar upptäcker ni senare att besökare som ni anser borde vara kvalificerade för upplevelserna B eller C i stället kvalificerar sig för upplevelsen A. Detta kan bero på att målgrupperna inte utesluter varandra och inte är i rätt ordning (till exempel upplevelsen A = USA, upplevelsen B = San Francisco och upplevelsen C = Kalifornien). I det här scenariot kvalificerar alla användare från USA sig för upplevelsen A, även om de befinner sig i San Francisco eller någon annanstans i Kalifornien. Du kan ändra ordning på målgruppspar och upplevda par från de mest restriktiva till de minst restriktiva (San Francisco > California > United States) utan att återskapa hela aktiviteten.

   Om du har en [!UICONTROL All Visitors] måste du se till att det inte är den första målgruppen i diagrammet. En upplevelse som är inriktad på[!UICONTROL All Visitors]&quot; kan användas som den sista upplevelsen i [!UICONTROL Experience Targeting] aktiviteter för att&quot;fånga&quot; besökare som inte har hamnat i någon annan upplevelse.

## Byta namn på eller redigera en upplevelse

Du kan klicka på [!UICONTROL Edit] ikonen (den lodräta ellipsen) för en upplevelse i en [!UICONTROL Experience Targeting] och välj bland följande alternativ efter behov:

* [!UICONTROL Rename]
* [!UICONTROL Edit]

![Alternativ för att byta namn och redigera](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Ta bort en upplevelse

På **[!UICONTROL Experiences]** (det första steget i det guidade arbetsflödet i tre steg), klicka på den lodräta ellipsen > **[!UICONTROL Delete]**.

![Ta bort upplevelse](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicera en upplevelse

Du kan kopiera en upplevelse i en [!UICONTROL Experience Targeting] så att du kan göra mindre ändringar i den utan att behöva återskapa hela upplevelsen.

På **[!UICONTROL Experiences]** (det första steget i det guidade arbetsflödet i tre steg), klicka på den lodräta ellipsen > **[!UICONTROL Duplicate]**.

![Dubblettupplevelse](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Utbildningsvideor:

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Från A/B-testning till [!UICONTROL Experience Targeting]

I den här videon beskrivs hur A/B-testning går till nästa nivå med [!UICONTROL Experience Targeting] (XT).

* Beskriv det guidade arbetsflödet i tre steg för att konfigurera ett [!UICONTROL Experience Targeting] aktivitet
* Beskriv hur ni levererar platsspecifikt innehåll till målgrupper inom olika geografiska områden
* Beskriv hur ni ordnar om upplevelserna för att säkerställa att rätt innehåll levereras till rätt målgrupp

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Aktivitetstyper (9:03)

I den här videon förklaras aktivitetstyperna som finns i [!DNL Target]. [!UICONTROL Experience Targeting] behandlas från 17:15.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Använda [!UICONTROL Visual Experience Composer]

I den här videon finns information om hur du använder [!UICONTROL Experience Targeting] (VEC).

* Ändra innehållet på en sida
* Ändra layouten för en sida

>[!VIDEO](https://video.tv.adobe.com/v/17399)
