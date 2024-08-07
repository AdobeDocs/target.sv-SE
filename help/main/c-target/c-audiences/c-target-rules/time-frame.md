---
keywords: tidsram;startdatum;slutdatum;start-/slutdatum;tidsram;målschema;veckoavskiljning;dagavskiljning
description: Lär dig hur du använder start- och slutdatum och sluttider för att rikta in dig på användare som besöker webbplatsen under en viss tidsperiod.
title: Kan jag rikta in mig på besökare som besöker min webbplats vid särskilda tillfällen?
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# [!UICONTROL Time Frame]

Du kan lägga till start- och slutdatum och sluttider i [!DNL Adobe Target] för målanvändare som besöker webbplatsen under en viss tidsperiod. Du kan också ange alternativen Vecka och Dag-delning för att skapa återkommande mönster för målgruppsanpassning.

Om du till exempel använder funktionen [för kombinerade ad hoc-målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) kan du rikta in dig på lågfrekventa kunder med specifikt innehåll under de tre dagarna fram till Black Friday och annat innehåll efter Black Friday.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Time Frame]** i rutan för målgruppsbyggaren.

   ![target_timeframe_dialog image](assets/target_timeframe_dialog.png)

1. Ange [!UICONTROL Start] och [!UICONTROL End] datum och tider för målgruppen.

   Lämna startdatumet tomt för att börja målinriktningen enligt aktivitetens schema. Lämna slutdatumet tomt om du vill fortsätta målinriktningen tills aktivitetens slutdatum och sluttid.

   Du kan också lämna både start- och slutdatum tomma. Med den här funktionen kan du använda samma målgrupp i flera aktiviteter (utan att behöva kopiera målgruppen) samtidigt som du styr start- och slutdatum på aktivitetsnivå.

   >[!NOTE]
   >
   >Tänk på följande:
   >
   >* Tidszonen för Start-/slutdatum visas som GMT +/- NN:NN, där NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon skulle till exempel visas som GMT -08:00.
   >
   >* [!DNL Target]-målgrupper tar inte hänsyn till DST-ändringar (Daylight Saving Time). Du måste spara om målgrupperna manuellt för att kunna ta hänsyn till DST-ändringar.

1. (Villkorligt) Klicka på **[!UICONTROL Set frequency]** för att ange återkommande mönster, inklusive veckodagar och tider.

   ![Vecka och dagdelning](assets/week_and_day_parting.png)

   Du kan till exempel använda alternativen för [!UICONTROL Frequency] för att visa alternativet Chatta nu för besökare endast under de dagar och timmar som telefonsamtalscentret är bemannat.

   Välj en eller flera dagar i veckan och ange start- och sluttider. Klicka på **[!UICONTROL Add frequency]** om du vill ange ytterligare mönster.

   >[!NOTE]
   >
   >Tidszonen för [!UICONTROL Week and Day Parting] visas som GMT +/- NN:NN, där NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon för Pacific Daylight Time skulle till exempel visas som GMT -07:00.

1. (Valfritt) Ange ytterligare regler för målgruppen.

   Du kan upprepa steg 5 för varje regel om du vill.

1. Klicka på **[!UICONTROL Done]**.

## Utbildningsvideo: Skapar märket ![Översikt](/help/main/assets/overview.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
