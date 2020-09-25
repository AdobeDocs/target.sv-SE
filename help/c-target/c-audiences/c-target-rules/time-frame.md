---
keywords: time frame;start date;end date;start/end dates;timeframe;target schedule;week parting;day parting;parting
description: Du kan lägga till start-/slutdatum och sluttider för målanvändare som besöker webbplatsen under en viss tidsperiod. Du kan också ange alternativen Vecka och Dag-delning för att skapa återkommande mönster för målgruppsanpassning.
title: Alternativ för tidsramar i Adobe Target-målgrupper
feature: audiences
uuid: 6c75014b-f0fd-4f76-a84f-b841bf87f1d7
translation-type: tm+mt
source-git-commit: 6922b80c88cbd2947c3bfd0cc9d8409ff5dcdcd0
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---


# Tidsram{#time-frame}

Du kan lägga till start-/slutdatum och sluttider för målanvändare som besöker webbplatsen under en viss tidsperiod. Du kan också ange alternativen Vecka och Dag-delning för att skapa återkommande mönster för målgruppsanpassning.

Med den [kombinerade ad hoc-målgruppsfunktionen](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)kan du till exempel rikta in dig på lågfrekventa kunder med specifikt innehåll under de tre dagarna fram till Black Friday och annat innehåll efter Black Friday.

1. I [!DNL Target] gränssnittet klickar du **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Time Frame]**.

   ![](assets/target_timeframe_dialog.png)

1. Ange start- och slutdatum och sluttider för målgruppen.

   Lämna startdatumet tomt för att börja målinriktningen enligt aktivitetens schema. Lämna slutdatumet tomt om du vill fortsätta målinriktningen tills aktivitetens slutdatum och sluttid.

   Du kan också lämna både start- och slutdatum tomma. På så sätt kan du använda samma målgrupp i flera aktiviteter (utan att göra en kopia av målgruppen) samtidigt som du styr start- och slutdatum på aktivitetsnivå.

   >[!NOTE]
   >
   >Tidszonen för Start-/slutdatum visas som GMT +/- NN:NN, där NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon skulle till exempel visas som GMT -08:00.

1. (Villkorligt) Klicka **[!UICONTROL Week and Day Parting]** för att ange återkommande mönster, inklusive veckodagar och tider.

   ![Vecka och dagdelning](assets/week_and_day_parting.png)

   Du kan till exempel använda alternativen Vecka och Dag-delning för att visa alternativet Chatta nu för besökare endast under de dagar och timmar som telefonsamtalscentret är bemannat.

   Välj en eller flera dagar i veckan och ange start- och sluttider. Klicka **[!UICONTROL Add More]** för att ange ytterligare mönster efter behov.

   >[!NOTE]
   >
   >Tidszonen för [!UICONTROL Week and Day Parting] visas som GMT +/- NN:NN, där NN:NN är förskjutningen från GMT och återspeglar tidszonen på kontonivå i stället för besökarens tidszon. Kaliforniens tidszon skulle till exempel visas som GMT -08:00.

1. (Valfritt) Klicka **[!UICONTROL Add Rule]** och ange ytterligare regler för publiken.

   Observera att du kan upprepa steg 5 för varje regel om du vill.

1. Klicka på **[!UICONTROL Save]**.

## Utbildningsvideo: Märket Skapa ![publiköversikt](/help/assets/overview.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
