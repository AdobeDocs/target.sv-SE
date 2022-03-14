---
keywords: automatiserad personalisering;erbjudanden;mål;målgrupp;målinriktningsregler;målinriktning
description: Lär dig att rikta enskilda erbjudanden till specifika målgrupper med hjälp av en Automated Personalization-aktivitet (AP) i Adobe Target.
title: Hur kan jag [!DNL Target] Automated Personalization-erbjudanden?
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 1%

---

# ![PREMIUM](/help/main/assets/premium.png) [!DNL Target] Automated Personalization erbjuder

I en [!DNL Adobe Target] [!DNL Automated Personalization] (AP) kan ni rikta erbjudanden till specifika målgrupper.

Om du använder den här funktionen minskas antalet erbjudanden som en viss besökare är kvalificerad att se. Ta till exempel en AP-aktivitet som har tre erbjudanden. Erbjudandet 1 har en målinriktningsregel som begränsar dess exponering till Audience A. Två besökare såg den här AP-aktiviteten.

|  | Besökare 1 | Besökare 2 |
|--- |--- |--- |
| Målgruppskvalifikation | Målgrupp A | Målgrupp B |
| Erbjudande 1 Resultat av målpersonaliseringsmodell | 90 | 90 |
| Resultat för målinriktad personalisering | 50 | 70 |
| Erbjudande 3 Resultat av målpersonaliseringsmodell | 80 | 60 |

I det här scenariot skulle besökare 1 se Erbjudande 1 (eftersom han eller hon kvalificerar sig som en del av Audience A), som är besökarens högsta poäng. Men besökare 2 skulle se Erbjudande 2 trots att hans eller hennes högsta poäng är för Erbjudande 1, eftersom besökare 2 inte är en del av Audience A. I det här exemplet visas varför målinriktningsreglerna bör användas sparsamt för att tillgodose verksamhetens behov. Genom att lägga till dessa regler kan målets personaliseringsmodeller bli mindre effektiva.

## Ställ in målinriktningsregler

1. Skapa en [Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) som innehåller de erbjudanden du vill rikta.
1. När du har ställt in erbjudandena för aktiviteten i Visual Experience Composer klickar du på **[!UICONTROL Manage Content]**.

   ![Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Dialogrutan Hantera innehåll öppnas.

1. Klicka på fliken Erbjudanden.

   ![Sidan Erbjudanden](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Välj önskat erbjudande(n) och välj de målgrupper du vill ska vara berättigade att se erbjudandet.

   Om du vill ange målinriktning för ett enskilt erbjudande för du muspekaren över önskat erbjudande och klickar sedan på **[!UICONTROL Targeting]** ikon.

   Om du vill ange mål för flera erbjudanden markerar du kryssrutorna för de önskade erbjudandena och klickar sedan på **[!UICONTROL Targeting] som visas längst upp till höger i listan.

1. I [!UICONTROL Choose Audience] väljer du önskad(a) publik(er) för erbjudandet och klickar sedan på **[!UICONTROL Done]** för att gå tillbaka till [!UICONTROL Manage Content] -dialogrutan.

   >[!NOTE]
   >
   >Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Klicka på **[!UICONTROL Done]**.

>[!NOTE]
>
>Du kan konfigurera 50 platser och upp till 250 erbjudanden per plats.
