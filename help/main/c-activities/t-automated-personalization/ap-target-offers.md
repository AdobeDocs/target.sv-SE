---
keywords: automatiserad personalisering;erbjudanden;mål;målgrupp;målinriktningsregler;målinriktning
description: Upptäck hur du kan rikta enskilda erbjudanden till specifika målgrupper med hjälp av [!UICONTROL Automated Personalization] (AP)-aktiviteter.
title: Hur kan jag rikta in mig på [!UICONTROL Automated Personalization] erbjudanden?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# Mål [!UICONTROL Automated Personalization] erbjuder

I en [!DNL Adobe Target] [!DNL Automated Personalization]-aktivitet (AP) kan du rikta erbjudanden till specifika målgrupper.

Om du använder den här funktionen minskas antalet erbjudanden som en viss besökare är kvalificerad att se. Ta till exempel en [!UICONTROL Automated Personalization]-aktivitet som har tre erbjudanden. Erbjudandet 1 har en målinriktningsregel som begränsar dess exponering till Audience A. Två besökare såg den här aktiviteten.

| | Besökare 1 | Besökare 2 |
|--- |--- |--- |
| Målgruppskvalifikation | Målgrupp A | Målgrupp B |
| Erbjudande 1 Resultat av målpersonaliseringsmodell | 90 | 90 |
| Resultat för målinriktad personalisering | 50 | 70 |
| Erbjudande 3 Resultat av målpersonaliseringsmodell | 80 | 60 |

I det här scenariot ser besökare 1 erbjudandet (eftersom besökaren kvalificerar sig som en del av målgrupp A), vilket är besökarens högsta poäng. Men besökare 2 ser Erbjudande 2 trots att det högsta poängen är för Erbjudande 1, eftersom besökare 2 inte ingår i Audience A. I det här exemplet visas varför målinriktningsreglerna bör användas sparsamt för att tillgodose verksamhetens behov. Om du lägger till dessa regler kan det minska effekten av [!DNL Target]-personaliseringsmodeller.

## Ställ in målinriktningsregler

1. Skapa eller redigera en [Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) som innehåller erbjudanden som du vill rikta.
1. När du har konfigurerat erbjudandena för aktiviteten i [!UICONTROL Visual Experience Composer] klickar du på ikonen **[!UICONTROL Manage Content]** ( ![ikonen Hantera innehåll](/help/main/assets/icons/Experience.svg) ).

   Dialogrutan [!UICONTROL Manage Content] visas.

1. Klicka på fliken **[!UICONTROL Offers]**.

1. Välj önskade erbjudanden och välj sedan de målgrupper du vill ha för att se erbjudandet.

   Om du vill ange mål för ett enskilt erbjudande klickar du på ikonen Mer information ( ![Mer info &#x200B;](/help/main/assets/icons/MoreSmallList.svg) ) bredvid önskat erbjudande och sedan på **[!UICONTROL Target Audience]** för att visa dialogrutan [!UICONTROL Add Audiences] .

   Om du vill ange mål för flera erbjudanden markerar du kryssrutorna för de önskade erbjudandena och klickar sedan på länken **[!UICONTROL Target Audience]** som visas längst ned i listan.

1. Välj önskade målgrupper för erbjudandena i dialogrutan [!UICONTROL Add Audiences] och klicka sedan på **[!UICONTROL Assign Audience]** för att återgå till dialogrutan [!UICONTROL Manage Content].

   >[!NOTE]
   >
   >Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa kombinerade målgrupper on-demand i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Klicka på **[!UICONTROL Done]**.

>[!NOTE]
>
>Du kan konfigurera 50 platser och upp till 250 erbjudanden per plats.
