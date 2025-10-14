---
keywords: målgrupp;utvalda målgrupper;välj målgrupp;Väljare
description: Definiera vilka webbplatsbesökare som går med i din Adobe [!DNL Target] aktivitet baserat på målgruppskriterier.
title: Hur väljer jag en publik i en [!DNL Target] A/B-aktivitet?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: f6845756f9d4220214b0d9131cd5f27db2ae94a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Välj målgrupp

Publiken avgör vilka kvalificerade besökare som registreras i din [!DNL Adobe Target]-aktivitet.

Steg [!UICONTROL Targeting] i det guidade arbetsflödet i tre delar när [en aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) skapas visas ett flödesdiagram som leder dig genom stegen för att tilldela en målgrupp och dess trafikprocent, välja trafikallokeringsmetod och ange trafikallokeringen för varje upplevelse i aktiviteten.

![Åtgärd för A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Mer information om alla alternativ i flödesdiagrammet finns i [Skapa en A/B-testaktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Välj en målgrupp för aktiviteten

1. Klicka på kontrollen **[!UICONTROL All Visitors]** för att välja en annan målgrupp för aktiviteten.

   [!UICONTROL All Visitors]-målgruppen är inställd som standard. Om du väljer en annan målgrupp visas dess namn längst till vänster.

   Välj standardvärdet [!UICONTROL All Visitors] för ett A/B-test utan specifik målgruppsanpassning.

   Den högra bildrutan visas, vilket gör att du kan lägga till eller ta bort en målgrupp och tilldela besökarprocenten för aktiviteten.

1. Om du vill ändra målgruppen klickar du på ikonen **[!UICONTROL Replace]** ( ![ikonen Ersätt](/help/main/assets/icons/Retweet.svg) ) i den högra ramen.

1. I dialogrutan [!UICONTROL Add Audience] [väljer du önskad målgrupp](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) och klickar sedan på **[!UICONTROL Assign Audience]**.

   Som standard är alla besökare er målgrupp. Men ni kan ändra målgruppen. Publiker väljs från [!UICONTROL Audience Library] eller så kan du skapa en målgrupp som bara innehåller aktiviteter. [!UICONTROL Audience Library] innehåller målgrupper som tidigare har definierats, inklusive några vanliga målgrupper som är fördefinierade som en del av [!DNL Target].

1. (Villkorligt) Klicka på **Kombinera publiker** för att [skapa en målgrupp som kombinerar flera målgrupper](/help/main/c-target/combining-multiple-audiences.md).

1. (Villkorligt) Om du vill skapa en ny publik som inte redan finns i [!UICONTROL Audience Library] klickar du på **Skapa publik**, definierar målgruppen och klickar sedan på **[!UICONTROL Done]**.

   Under [målgruppsarbetsflödet](/help/main/c-target/c-audiences/audiences.md) kan du välja bland följande alternativ:

   * **[!UICONTROL Audience Library]**: Skapa en målgrupp på begäran som sparas i [!UICONTROL Audience Library] som kan återanvändas i andra aktiviteter.
   * **[!UICONTROL This activity only]**: Skapa en [aktivitetsspecifik målgrupp](/help/main/c-target/creating-activity-only-audience.md) som inte har sparats i [!UICONTROL Audience Library] och som bara kan användas i den aktuella aktiviteten.

1. Klicka på **[!UICONTROL Visitor Percentage]** i den högra rutan och ange sedan hur många procent kvalificerade besökare som ska inkluderas i aktiviteten.

1. När du är nöjd med målgruppen klickar du på **[!UICONTROL Next]** för att gå till det tredje steget i det guidade arbetsflödet i tre steg.

>[!NOTE]
>
>Publiker importeras automatiskt i bakgrunden när du öppnar listan [!UICONTROL Audience] och de importerade målgrupperna är mer än tio minuter gamla.

## Visa information om en viss målgrupp

1. I dialogrutan [!UICONTROL Add Audiences] klickar du på ikonen **[!UICONTROL Information]** ( ![informationsikonen &#x200B;](/help/main/assets/icons/InfoOutline.svg) ) bredvid en målgrupp för att visa information om den målgruppen, inklusive dess källa och attribut.

1. Klicka på **[!UICONTROL View Full Details]** om du vill visa mer information om målgruppen. Detaljerna innehåller publikens attribut, målgruppens beskrivning, arbetsyta, typ och källa samt en lista över aktiviteter som refererar till den här målgruppen. Du kan visa information om varje målgrupp, inklusive aktivitetsnamn, status, arbetsyta och när målgruppen senast ändrades och av vem.

## Redigera eller kopiera en målgrupp

Du kan redigera eller kopiera en målgrupp genom att klicka på ikonen [!UICONTROL More Actions] ( ![Fler åtgärder &#x200B;](/help/main/assets/icons/More.svg) ) bredvid den önskade målgruppen i dialogrutan [!UICONTROL Add Audience] och sedan klicka på [!UICONTROL Edit] eller [!UICONTROL Copy].

Det är praktiskt att kopiera en målgrupp om du vill skapa en liknande målgrupp som en befintlig målgrupp. Ni kan göra en kopia av målgruppen, göra redigeringar och sedan spara den som en ny målgrupp.
