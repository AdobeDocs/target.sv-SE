---
keywords: målgrupp;utvalda målgrupper;välj målgrupp;Väljare
description: Publiken avgör vilka besökare som läggs in i Adobe [!DNL Target] aktivitet.
title: Hur väljer jag en publik i en [!DNL Target] A/B-aktivitet?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Välj målgrupp

Publiken avgör vilka besökare som läggs in på webbplatsen [!DNL Adobe Target] aktivitet.

>[!NOTE]
>
>Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

I [!UICONTROL Audience] klickar du på ikonen Redigera (tre lodräta ellipser) och sedan på **[!UICONTROL Replace Audience]**.

![Alternativet Ersätt publik](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

Som standard är alla besökare er målgrupp. Men ni kan ändra målgruppen. Målgrupper väljs ut från målgruppsbiblioteket eller så kan du skapa en målgrupp som bara är aktiv. Målgruppsbiblioteket innehåller målgrupper som tidigare har definierats, inklusive några vanliga målgrupper som är färdigbyggda som en del av Target. Du kan välja en målgrupp i biblioteket, [skapa en ny målgrupp](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1), eller [skapa en målgrupp som bara innehåller aktivitet](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483). För ett A/B-test utan specifik målgruppsanpassning väljer du standardinställningen Alla besökare.

Observera att du även kan redigera eller kopiera en publik genom att hovra över den önskade publiken i [!UICONTROL Choose Audience] som visas nedan. Det är praktiskt att kopiera en målgrupp om du vill skapa en liknande målgrupp som en befintlig målgrupp. Ni kan göra en kopia av målgruppen, göra redigeringarna och sedan spara den som en ny målgrupp. Den här hovringsfunktionen finns även i andra aktivitetstyper.

![Målgruppshovring](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

När du skapar en målgrupp kan du välja en plats (mbox) och ange parametrar för den platsen. Markera rutan under Egna parametrar och ange sedan önskade parametrar.

>[!NOTE]
>
>Publiken importeras automatiskt i bakgrunden när du öppnar målgruppslistan och de importerade målgrupperna är mer än tio minuter gamla.

Klicka på nedpilen för att ta bort den befintliga publiken eller ändra målgruppen.

Du kan ange hur många procent kvalificerade besökare som ska inkluderas i aktiviteten. Du kan till exempel välja att ta med 50 % av alla besökare.

![Målgrupp i procent](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

Du kan också välja att låta Mål [tilldela trafik automatiskt](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Använda målgrupper i Adobe Target (6:21) ![Märket Översikt](/help/main/assets/overview.png)

I den här videon förklaras hur du använder målgrupper i [!DNL Target Standard/Premium].

* Förklara termen&quot;Målgrupp&quot;
* Förklara de två sätt på vilka målgrupper används för optimering
* Hitta målgrupper i publiklistan
* Rikta en aktivitet mot en målgrupp
* Använd målgrupper för passiv rapportering i en aktivitet

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### Aktivitetsarbetsflöde - målinriktning (2:14) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du konfigurerar målgrupper.

* Tilldela en målgrupp till din aktivitet
* Begränsa trafiken uppåt eller nedåt
* Välj trafikallokeringsmetod
* Fördela trafik mellan olika upplevelser

>[!VIDEO](https://video.tv.adobe.com/v/17385)

Mer information finns i [Målgrupper](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).