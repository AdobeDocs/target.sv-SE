---
keywords: tidsram;startdatum;slutdatum;start-/slutdatum;tidsram;målschema;veckoavskiljning;dagavskiljning
description: Lär dig hur du använder start- och slutdatum för att rikta in dig på användare som besöker webbplatsen under en viss tidsperiod. Du kan också ange alternativ för Vecka och Dag-delning.
title: Kan jag [!DNL Target] besöka mina webbplatser vid olika tillfällen?
feature: Målgrupper
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---

# Tidsram

Du kan lägga till start-/slutdatum och sluttider för målanvändare som besöker webbplatsen under en viss tidsperiod. Du kan också ange alternativen Vecka och Dag-delning för att skapa återkommande mönster för målgruppsanpassning.

Om du till exempel använder funktionen [för kombinerade ad hoc-målgrupper](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) kan du rikta in dig på lågfrekventa kunder med specifikt innehåll under de tre dagar som leder fram till Black Friday och annat innehåll efter Black Friday.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Time Frame]**.

   ![](assets/target_timeframe_dialog.png)

1. Ange start- och slutdatum och sluttider för målgruppen.

   Lämna startdatumet tomt för att börja målinriktningen enligt aktivitetens schema. Lämna slutdatumet tomt om du vill fortsätta målinriktningen tills aktivitetens slutdatum och sluttid.

   Du kan också lämna både start- och slutdatum tomma. På så sätt kan du använda samma målgrupp i flera aktiviteter (utan att göra en kopia av målgruppen) samtidigt som du styr start- och slutdatum på aktivitetsnivå.

   >[!NOTE]
   >
   >Tidszonen för Start-/slutdatum visas som GMT +/- NN:NN, där NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon skulle till exempel visas som GMT -08:00.

1. (Villkorligt) Klicka på **[!UICONTROL Week and Day Parting]** för att ange återkommande mönster, inklusive veckodagar och tider.

   ![Vecka och dagdelning](assets/week_and_day_parting.png)

   Du kan till exempel använda alternativen Vecka och Dag-delning för att visa alternativet Chatta nu för besökare endast under de dagar och timmar som telefonsamtalscentret är bemannat.

   Välj en eller flera dagar i veckan och ange start- och sluttider. Klicka på **[!UICONTROL Add More]** om du vill ange ytterligare mönster.

   >[!NOTE]
   >
   >Tidszonen för [!UICONTROL Week and Day Parting] visas som GMT +/- NN:NN, där NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon skulle till exempel visas som GMT -08:00.

1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** och ange ytterligare regler för målgruppen.

   Observera att du kan upprepa steg 5 för varje regel om du vill.

1. Klicka på **[!UICONTROL Save]**.

## Utbildningsvideo: Skapar publikation ![Översikt](/help/assets/overview.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
