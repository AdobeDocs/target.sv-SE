---
keywords: audience;select audience;choose audience;Selectors
description: Publiken avgör vilka besökare som läggs in i din aktivitet.
title: Välj målgrupp
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Välj målgrupp{#select-audience}

Publiken avgör vilka besökare som läggs in i din aktivitet.

>[!NOTE]
>
>Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera publiker](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

Klicka på ikonen Redigera (tre lodräta ellipser) i [!UICONTROL Audience] rutan och klicka sedan på **[!UICONTROL Replace Audience]**.

![Alternativet Ersätt publik](/help/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

Som standard är alla besökare er målgrupp. Men ni kan ändra målgruppen. Målgrupper väljs ut från målgruppsbiblioteket eller så kan du skapa en målgrupp som bara är aktiv. Målgruppsbiblioteket innehåller målgrupper som tidigare har definierats, inklusive några vanliga målgrupper som är färdigbyggda som en del av Target. Du kan välja en målgrupp i biblioteket, [skapa en ny målgrupp](/help/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)eller [skapa en målgrupp](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)som bara innehåller aktiviteter. För ett A/B-test utan specifik målgruppsanpassning väljer du standardinställningen Alla besökare.

Observera att du även kan redigera eller kopiera en målgrupp genom att hålla markören över den önskade målgruppen i [!UICONTROL Choose Audience] dialogrutan, vilket visas nedan. Det är praktiskt att kopiera en målgrupp om du vill skapa en liknande målgrupp som en befintlig målgrupp. Ni kan göra en kopia av målgruppen, göra redigeringar och sedan spara den som en ny målgrupp. Den här hovringsfunktionen finns även i andra aktivitetstyper.

![Målgruppshovring](/help/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

När du skapar en målgrupp kan du välja en plats (mbox) och ange parametrar för den platsen. Markera rutan under Egna parametrar och ange sedan önskade parametrar.

>[!NOTE]
>
>Publiken importeras automatiskt i bakgrunden när du öppnar målgruppslistan och de importerade målgrupperna är mer än tio minuter gamla.

Klicka på nedpilen för att ta bort den befintliga publiken eller ändra målgruppen.

Du kan ange hur många procent kvalificerade besökare som ska inkluderas i aktiviteten. Du kan till exempel välja att ta med 50 % av alla besökare.

![Målgrupp i procent](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

Du kan också välja att låta Target [tilldela trafik automatiskt](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Using Audiences in Adobe Target (6:21) ![Overview badge](/help/assets/overview.png)

I den här videon förklaras hur du använder målgrupper i [!DNL Target Standard/Premium].

* Förklara termen&quot;Målgrupp&quot;
* Förklara de två sätt på vilka målgrupper används för optimering
* Hitta målgrupper i publiklistan
* Rikta en aktivitet mot en målgrupp
* Använd målgrupper för passiv rapportering i en aktivitet

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### Aktivitetsarbetsflöde - Målinriktning (2:14) ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller information om hur du konfigurerar målgrupper.

* Tilldela en målgrupp till din aktivitet
* Begränsa trafiken uppåt eller nedåt
* Välj trafikallokeringsmetod
* Fördela trafik mellan olika upplevelser

>[!VIDEO](https://video.tv.adobe.com/v/17385)

Mer information finns i [Publiker](/help/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).
