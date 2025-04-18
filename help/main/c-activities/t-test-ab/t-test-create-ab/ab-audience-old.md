---
keywords: målgrupp;utvalda målgrupper;välj målgrupp;Väljare
description: Publiken avgör vilka besökare som läggs in i din Adobe [!DNL Target] -aktivitet.
title: Hur väljer jag en publik i en [!DNL Target] A/B-aktivitet?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Välj målgrupp

Publiken avgör vilka webbplatsbesökare som är registrerade i din [!DNL Adobe Target]-aktivitet.

>[!NOTE]
>
>Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Klicka på ikonen **[!UICONTROL Edit]** (den lodräta ellipsen) i rutan [!UICONTROL Audience] och klicka sedan på **[!UICONTROL Replace Audience]**.

   ![Ersätt publik, alternativ](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   Som standard är alla besökare er målgrupp. Men ni kan ändra målgruppen. Målgrupper väljs ut från målgruppsbiblioteket eller så kan du skapa en målgrupp som bara är aktiv. Målgruppsbiblioteket innehåller målgrupper som tidigare har definierats, inklusive några vanliga målgrupper som är fördefinierade som en del av [!DNL Target].

1. Välj eller skapa önskad målgrupp:

   * Välj en målgrupp i biblioteket
   * [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [Skapa en ny målgrupp](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [Skapa en målgrupp som bara är aktiv](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

   Välj standardvärdet [!UICONTROL All Visitors] för ett A/B-test utan specifik målgruppsanpassning.

   Du kan också redigera eller kopiera en målgrupp genom att hålla markören över den önskade målgruppen i dialogrutan [!UICONTROL Add Audience], vilket visas nedan.

   Det är praktiskt att kopiera en målgrupp om du vill skapa en liknande målgrupp som en befintlig målgrupp. Ni kan göra en kopia av målgruppen, göra redigeringar och sedan spara den som en ny målgrupp. Den här hovringsfunktionen finns även i andra aktivitetstyper.

   ![Målgruppshovring](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   När du skapar en målgrupp kan du välja en plats (mbox) och ange parametrar för den platsen. Under [!UICONTROL Custom Parameters] markerar du mbox och anger önskade parametrar.

   >[!NOTE]
   >
   >Publiken importeras automatiskt i bakgrunden när du öppnar målgruppslistan och de importerade målgrupperna är mer än tio minuter gamla.

1. (Villkorligt) Ange den procentandel kvalificerade besökare som ska inkluderas i aktiviteten.

   Du kan till exempel välja att ta med 50 % av alla besökare.

   ![Målgruppsprocent](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Du kan också välja att låta mål [tilldela trafik automatiskt](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Använda målgrupper i Adobe Target (6:21) ![märket Översikt](/help/main/assets/overview.png)

I den här videon förklaras hur du använder målgrupper i [!DNL Target Standard/Premium].

* Förklara termen&quot;Målgrupp&quot;
* Förklara de två sätt på vilka målgrupper används för optimering
* Hitta målgrupper i publiklistan
* Rikta en aktivitet mot en målgrupp
* Använd målgrupper för passiv rapportering i en aktivitet

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### Aktivitetsarbetsflöde - Målinriktning (2:14) ![Självstudiekurs](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du konfigurerar målgrupper.

* Tilldela en målgrupp till din aktivitet
* Begränsa trafiken uppåt eller nedåt
* Välj trafikallokeringsmetod
* Fördela trafik mellan olika upplevelser

>[!VIDEO](https://video.tv.adobe.com/v/17385)

Mer information finns i [Publiker](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).
