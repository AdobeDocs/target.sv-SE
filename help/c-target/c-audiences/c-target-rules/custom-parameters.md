---
keywords: custom parameters;target custom parameters;targetpageparams;targeting mbox parameters
description: Egna parametrar är mbox-parametrar. Om du skickar några mbox-parametrar till mboxes, eller använder funktionen targetPageParams, visas de parametrarna här för användning i målgrupper.
title: Egna parametrar i Adobe Target
feature: audiences
topic: Standard
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---


# Egna parametrar{#custom-parameters}

Egna parametrar är mbox-parametrar. Om du skickar några mbox-parametrar till mboxes, eller använder funktionen targetPageParams, visas de parametrarna här för användning i målgrupper.

Mer information finns i [Skicka parametrar till en global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

När du skapar en anpassad målgrupp baserat på en mbox-parameter får du inte längre någon fråga om det `mboxParameter` `mboxName`. Nu är mbox-namnet valfritt. Med den här ändringen kan du använda parametrar från flera rutor eller referera till en parameter som ännu inte har registrerats på kanten.

1. I [!DNL Target] gränssnittet klickar du **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Custom]**.

   Så här väljer du önskad parameter:

   * När du skapar en ny målgrupp väljer du ett parameternamn i listan, börjar skriva de första tecknen i det önskade parameternamnet eller skriver det fullständiga namnet på det önskade parameternamnet.
   * Om du kommer ihåg mbox-namnet, men inte parameternamnet, använder du kryssrutan för att filtrera på en känd mbox som skickar den önskade parametern.

   Om du använder någon av metoderna finns det ingen länk mellan mbox och parametern. Publiken kommer att arbeta baserat på parametern i alla mbox som skickar den parametern.

   Om du redigerar en befintlig målgrupp visas filtervillkoren med namnet på mbox som angavs när målgruppen skapades.

1. Välj en utvärderare:

   * Innehåller (skiftlägesokänslig)
   * Innehåller inte (skiftlägesokänslig)
   * Lika med

   ![Anpassad parametermålgrupp](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. Ange varje värde på en ny rad.
1. (Valfritt) Klicka **[!UICONTROL Add Rule]** och ange ytterligare regler för publiken.
1. Klicka på **[!UICONTROL Save]**.

Publiken har ett popup-kort [med](/help/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) definitionsinformation som visar parameternamnet i avsnittet Regler. Det finns ingen referens till mbox som används för filtrering.

>[!NOTE]
>
>För anpassade målgrupper som skapats före målversionen 18.5.1 (22 maj 2018) visas inte mbox-namnen i publikens definitionskort. Du måste spara om den anpassade målgruppen för att få mbox-namnet som ska visas på kortet.

## Överväganden {#considerations}

* Målgrupper och aktiviteter utvärderas för en viss ruta. Om till exempel den globala mbox skickar en viss parameter, men den regionala mbox inte gör det, kommer aktiviteten/målgruppen som anger den parametern inte att kvalificeras för i den regionala mbox.
* Målinriktning utvärderas inte för interna mbox-parametrar, till exempel mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId och mboxVersion.

## Utbildningsvideo: Skapa märket för ![självstudiekurser för publiker](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
