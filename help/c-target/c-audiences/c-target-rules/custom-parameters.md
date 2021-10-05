---
keywords: anpassade parametrar;anpassade målparametrar;målparametrar;målparametrar;målparametrar för mbox
description: Lär dig hur du skickar anpassade parametrar till [!DNL Adobe Target] för användning i målgrupper.
title: Kan jag rikta in besökare baserat på anpassade parametrar?
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: b74cccdc43c34367819ed8a908a304b567d7ecbb
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Egna parametrar

Egna parametrar är mbox-parametrar i [!DNL Adobe Target]. Om du skickar några mbox-parametrar till mbox, eller använder funktionen `targetPageParams`, visas dessa parametrar här för användning i målgrupper.

Mer information finns i [Skicka parametrar till en global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

När du skapar en anpassad målgrupp baserat på en mbox-parameter uppmanar `mboxParameter` dig inte längre att ange `mboxName`. Nu är mbox-namnet valfritt. Med den här ändringen kan du använda parametrar från flera rutor eller referera till en parameter som ännu inte har registrerats på kanten.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Custom]** i Audience Builder.

   Så här väljer du önskad parameter:

   * När du skapar en målgrupp väljer du ett parameternamn i listan, börjar skriva de första tecknen i det önskade parameternamnet eller skriver det fullständiga namnet på det önskade parameternamnet.
   * Om du kommer ihåg mbox-namnet, men inte parameternamnet, använder du listrutan [!UICONTROL Filter by] för att filtrera på en känd mbox som skickar den önskade parametern.

   Om du använder någon av metoderna finns det ingen länk mellan mbox och parametern. Publiken arbetar baserat på parametern i alla mbox som skickar den parametern.

   Om du redigerar en befintlig målgrupp visas filtervillkoren med namnet på mbox som angavs när målgruppen skapades.

1. Välj en utvärderare:

   * Innehåller (skiftlägesokänslig)
   * Innehåller inte (skiftlägesokänslig)
   * Lika med
   * Är inte lika med
   * Är större än
   * Är större än eller lika med
   * Är mindre än
   * Är mindre än eller lika med
   * Parametern finns
   * Parametern finns inte
   * Parametervärdet finns
   * Parametervärdet finns inte
   * Parametern eller värdet finns inte
   * Börja med
   * Slutar med

   ![Anpassad parametermålgrupp](assets/custom.png)

1. Ange varje värde på en ny rad.
1. (Valfritt) Ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Done]**.

Publiken [på popup-kortet för definitionsinformation](/help/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) visas parameternamnet i avsnittet **[!UICONTROL Rules]**. Det finns ingen referens till mbox som används för filtrering.

>[!NOTE]
>
>För anpassade målgrupper som skapats före [!DNL Target] 18.5.1-utgåvan (22 maj 2018) visas inte mbox-namnen i publikens definitionskort. Spara den anpassade målgruppen igen för att få mbox-namnet som ska visas på kortet.

## Överväganden {#considerations}

* Målgrupper och aktiviteter utvärderas för en viss ruta. Om till exempel den globala mbox skickar en viss parameter, men den regionala mbox inte gör det, är aktiviteten/målgruppen som anger den parametern inte kvalificerad för i den regionala mbox.
* Målinriktning utvärderas inte för interna mbox-parametrar, som mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId och mboxVersion.

## Utbildningsvideo: Skapar publik ![Självstudiekursikon](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
