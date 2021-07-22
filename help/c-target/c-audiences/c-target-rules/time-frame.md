---
keywords: tidsram;startdatum;slutdatum;start-/slutdatum;tidsram;målschema;veckoavskiljning;dagavskiljning
description: Lär dig hur du använder start- och slutdatum och sluttider för att rikta in dig på användare som besöker webbplatsen under en viss tidsperiod.
title: Kan jag rikta in mig på besökare som besöker min webbplats vid särskilda tillfällen?
feature: Målgrupper
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# Tidsram

Du kan lägga till start- och slutdatum och sluttider i [!DNL Adobe Target] för målanvändare som besöker webbplatsen under en viss tidsperiod. Du kan också ange alternativen Vecka och Dag-delning för att skapa återkommande mönster för målgruppsanpassning.

Om du till exempel använder funktionen [för kombinerade ad hoc-målgrupper](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) kan du rikta in dig på lågfrekventa kunder med specifikt innehåll under de tre dagar som leder fram till Black Friday och annat innehåll efter Black Friday.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. 
   1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Time Frame]** i rutan för målgruppsbyggaren.

   ![](assets/target_timeframe_dialog.png)

1. Ange [!UICONTROL Start]- och [!UICONTROL End]-datum och tider för målgruppen.

   Lämna startdatumet tomt för att börja målinriktningen enligt aktivitetens schema. Lämna slutdatumet tomt om du vill fortsätta målinriktningen tills aktivitetens slutdatum och sluttid.

   Du kan också lämna både start- och slutdatum tomma. Med den här funktionen kan du använda samma målgrupp i flera aktiviteter (utan att behöva kopiera målgruppen) samtidigt som du styr start- och slutdatum på aktivitetsnivå.

   >[!NOTE]
   >
   >Tidszonen för Start-/slutdatum visas som GMT +/- NN:NN, där NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon skulle till exempel visas som GMT -08:00.

1. (Villkorligt) Klicka på **[!UICONTROL Set frequency]** för att ange återkommande mönster, inklusive veckodagar och tider.

   ![Vecka och dagdelning](assets/week_and_day_parting.png)

   Du kan till exempel använda [!UICONTROL Frequency]-alternativ för att visa alternativet Chatta nu för besökare endast under de dagar och timmar som telefonsamtalscentret är bemannat.

   Välj en eller flera dagar i veckan och ange start- och sluttider. Klicka på **[!UICONTROL Add frequency]** om du vill ange ytterligare mönster.

   >[!NOTE]
   >
   >Tidszonen för [!UICONTROL Week and Day Parting] visas som GMT +/- NN:NN, där NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon för Pacific Daylight Time skulle till exempel visas som GMT -07:00.

1. (Valfritt) Ange ytterligare regler för målgruppen.

   Du kan upprepa steg 5 för varje regel om du vill.

1. Klicka på **[!UICONTROL Done]**.

## Utbildningsvideo: Skapar publikation ![Översikt](/help/assets/overview.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
