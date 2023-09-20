---
keywords: automatiserad personalisering;erbjudanden;mål;målgrupp;målinriktningsregler;målinriktning
description: Lär dig målinrikta enskilda erbjudanden till specifika målgrupper med en [!UICONTROL Automated Personalization] (AP) aktivitet i [!DNL Adobe Target].
title: Hur kan jag rikta mig mot [!UICONTROL Automated Personalization] Erbjudanden?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---

# Mål [!UICONTROL Automated Personalization] erbjudanden

I en [!DNL Adobe Target] [!DNL Automated Personalization] (AP) kan ni rikta erbjudanden till specifika målgrupper.

Om du använder den här funktionen minskas antalet erbjudanden som en viss besökare är kvalificerad att se. Ta till exempel en [!UICONTROL Automated Personalization] som har tre erbjudanden. Erbjudandet 1 har en målinriktningsregel som begränsar dess exponering till Audience A. Två besökare såg den här aktiviteten.

| | Besökare 1 | Besökare 2 |
|--- |--- |--- |
| Målgruppskvalifikation | Målgrupp A | Målgrupp B |
| Erbjudande 1 Resultat av målpersonaliseringsmodell | 90 | 90 |
| Resultat för målinriktad personalisering | 50 | 70 |
| Erbjudande 3 Resultat av målpersonaliseringsmodell | 80 | 60 |

I det här scenariot ser besökare 1 erbjudandet (eftersom besökaren kvalificerar sig som en del av målgrupp A), vilket är besökarens högsta poäng. Men besökare 2 ser Erbjudande 2 trots att det högsta poängen är för Erbjudande 1, eftersom besökare 2 inte ingår i Audience A. I det här exemplet visas varför målinriktningsreglerna bör användas sparsamt för att tillgodose verksamhetens behov. Genom att lägga till dessa regler kan man minska effektiviteten hos [!DNL Target] personaliseringsmodeller.

## Ställ in målinriktningsregler

1. Skapa en [Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) som innehåller de erbjudanden du vill rikta in dig på.
1. När du har ställt in erbjudandena för aktiviteten i [!UICONTROL Visual Experience Composer], klicka **[!UICONTROL Manage Content]**.

   ![Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   The [!UICONTROL Manage Content] visas.

1. Klicka på **[!UICONTROL Offers]** -fliken.

   ![Sidan Erbjudanden](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Välj önskade erbjudanden och välj sedan de målgrupper du vill ha för att se erbjudandet.

   Om du vill ange målinriktning för ett enskilt erbjudande för du muspekaren över önskat erbjudande och klickar sedan på **[!UICONTROL Targeting]** -ikon.

   Om du vill ange mål för flera erbjudanden markerar du kryssrutorna för önskade erbjudanden och klickar sedan på **[!UICONTROL Targeting]** som visas längst upp till höger i listan.

1. I [!UICONTROL Choose Audience] väljer du målgrupper för erbjudandena och klickar sedan på **[!UICONTROL Done]** för att gå tillbaka till [!UICONTROL Manage Content] -dialogrutan.

   >[!NOTE]
   >
   >Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Klicka på **[!UICONTROL Done]**.

>[!NOTE]
>
>Du kan konfigurera 50 platser och upp till 250 erbjudanden per plats.
