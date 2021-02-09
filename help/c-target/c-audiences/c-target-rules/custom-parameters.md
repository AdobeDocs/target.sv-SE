---
keywords: anpassade parametrar;anpassade målparametrar;målparametrar;målparametrar;målparametrar för mbox
description: Lär dig hur du skickar anpassade parametrar till Adobe Target för användning i målgrupper.
title: Kan jag rikta in besökare baserat på anpassade parametrar?
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# Anpassade parametrar{#custom-parameters}

Egna parametrar är mbox-parametrar. Om du skickar några mbox-parametrar till mboxes, eller använder funktionen targetPageParams, visas de parametrarna här för användning i målgrupper.

Mer information finns i [Skicka parametrar till en global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

När du skapar en anpassad målgrupp baserat på en mbox-parameter uppmanar `mboxParameter` dig inte längre att ange `mboxName`. Nu är mbox-namnet valfritt. Med den här ändringen kan du använda parametrar från flera rutor eller referera till en parameter som ännu inte har registrerats på kanten.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
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
1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** och ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Save]**.

Publiken [på popup-kortet för definitionsinformation](/help/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) visas parameternamnet i avsnittet Regler. Det finns ingen referens till mbox som används för filtrering.

>[!NOTE]
>
>För anpassade målgrupper som skapats före målversionen 18.5.1 (22 maj 2018) visas inte mbox-namnen i publikens definitionskort. Du måste spara om den anpassade målgruppen för att få mbox-namnet som ska visas på kortet.

## Överväganden {#considerations}

* Målgrupper och aktiviteter utvärderas för en viss ruta. Om till exempel den globala mbox skickar en viss parameter, men den regionala mbox inte gör det, kommer aktiviteten/målgruppen som anger den parametern inte att kvalificeras för i den regionala mbox.
* Målinriktning utvärderas inte för interna mbox-parametrar, till exempel mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId och mboxVersion.

## Utbildningsvideo: Skapar publik ![Självstudiekursikon](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
