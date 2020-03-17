---
description: I en automatiserad personaliseringsaktivitet kan ni rikta erbjudanden till specifika målgrupper.
title: Automatiserade personaliseringserbjudanden
solution: Target,Analytics
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) Target Automatiserad personalisering erbjuder{#target-automated-personalization-offers}

I en Automated Personalization-aktivitet (AP) kan ni rikta erbjudanden till specifika målgrupper.

Om du använder den här funktionen minskas antalet erbjudanden som en viss besökare är kvalificerad att se. Ta till exempel en AP-aktivitet som har tre erbjudanden. Erbjudandet 1 har en målinriktningsregel som begränsar dess exponering till Audience A. Två besökare såg den här AP-aktiviteten.

|  | Besökare 1 | Besökare 2 |
|--- |--- |--- |
| Målgruppskvalifikation | Målgrupp A | Målgrupp B |
| Erbjudande 1 Resultat av målpersonaliseringsmodell | 90 | 90 |
| Resultat för målinriktad personalisering | 50 | 70 |
| Erbjudande 3 Resultat av målpersonaliseringsmodell | 80 | 60 |

I det här scenariot skulle besökare 1 se Erbjudande 1 (eftersom han eller hon kvalificerar sig som en del av Audience A), som är besökarens högsta poäng. Men besökare 2 skulle se Erbjudande 2 trots att hans eller hennes högsta poäng är för Erbjudande 1, eftersom besökare 2 inte är en del av Audience A. I det här exemplet visas varför målinriktningsreglerna bör användas sparsamt för att tillgodose verksamhetens behov. Genom att lägga till dessa regler kan målets personaliseringsmodeller bli mindre effektiva.

## Ställ in målinriktningsregler

1. Skapa en [automatiserad personaliseringsaktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md) som innehåller de erbjudanden du vill rikta in dig på.
1. När du har ställt in erbjudandena för aktiviteten i Visual Experience Composer klickar du på **[!UICONTROL Manage Content]**.

   ![Hantera innehåll](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   Dialogrutan Hantera innehåll öppnas.

1. Klicka på fliken Erbjudanden.

   ![Sidan Erbjudanden](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Välj önskat erbjudande(n) och välj de målgrupper du vill ska vara berättigade att se erbjudandet.

   Om du vill ange målinriktning för ett enskilt erbjudande för du muspekaren över det önskade erbjudandet och klickar sedan på **[!UICONTORL målikonen]** .

   Om du vill ange mål för flera erbjudanden markerar du kryssrutorna för de önskade erbjudandena och klickar sedan på **[!UICONTROL Targeting] -ikonen som visas längst upp till höger i listan.

1. I [!UICONTROL Choose Audience] dialogrutan väljer du önskad(a) publik(er) för erbjudandet och klickar sedan på **[!UICONTROL Done]** för att återgå till [!UICONTROL Manage Content] dialogrutan.

   >[!NOTE]
   >
   >Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera publiker](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Klicka på **[!UICONTROL Done]**.

>[!NOTE]
>
>Du kan konfigurera 50 platser och upp till 250 erbjudanden per plats.
