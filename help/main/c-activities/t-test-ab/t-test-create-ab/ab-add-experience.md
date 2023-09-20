---
keywords: Målgruppsanpassning;upplevelse;lägg till upplevelse;lägg till upplevelse
description: Lär dig använda [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target].
title: Hur lägger jag till upplevelser i en [!DNL Target] A/B-aktivitet?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: 6fa1b428e7955bae976649c42d3eb9b2ddc2c79f
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Lägg till upplevelse

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) är ett visuellt gränssnitt för att lägga till och redigera upplevelser på sidan.

Mer information om upplevelser finns på [Erfarenheter](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Från **[!UICONTROL Experiences]** i VEC, klicka **[!UICONTROL Add Experience]**.

   ![Alternativet Lägg till upplevelse](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >Om ni riktar in er på en upplevelse måste ni välja målgrupp innan ni kan lägga till en upplevelse. Det visas ett meddelande som påminner dig om att du kan välja målgrupp.

1. Markera elementen som du vill ändra och gör önskade ändringar.

   När du håller muspekaren över elementen på sidan markeras elementen. Alla markerade element kan ändras med VEC.

   Om du skapade en [!DNL Target] begäran på sidan med [!DNL Target Classic] (tidigare [!DNL Test&Target]), att [!DNL Target] begäran visas som ett element som visar begäransnamnet och kan ändras som vilket element som helst.

   En lista över åtgärder som kan utföras på ett element på den visade sidan för att ändra upplevelsen finns i [Alternativ för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Om du levererar en bild från en annan källa än huvudsidan (till exempel en bild som finns på `akamai.net` och levereras den `example.com`) visas den bilden inte i miniatyrbilden av sidan som visas i flödesdiagrammet.

1. Klicka **[!UICONTROL Save]** när du är klar med designen.

## Byt namn på upplevelsen

1. Klicka på **[!UICONTROL Rename Experience]** ikon på en upplevelse i en [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting] (XT) för att ge upplevelsen ett nytt namn.

   ![Byt namn på upplevelsen](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/rename-experience.png)

2. Ange ett nytt namn.

   När du namnger eller byter namn på en upplevelse tillåts inte följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | / | Snedstreck |
   | ? | Frågetecken |
   | # | Nummertecken |
   | : | Colon |
   | = | Lika med |
   | + | Plus |
   | - | Minus |
   | @ | Vid tecken |

## Omdirigera till URL

1. Klicka på **[!UICONTROL More]** ikonen (den lodräta ellipsen) på en upplevelse i en [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting] (XT) och sedan klicka **[!UICONTROL Redirect to URL]**.

   Mer information finns i [Omdirigera till URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

   **ANMÄRKNING**: När du namnger eller byter namn på en upplevelse tillåts inte följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | / | Snedstreck |
   | ? | Frågetecken |
   | # | Nummertecken |
   | : | Colon |
   | = | Lika med |
   | + | Plus |
   | - | Minus |
   | @ | Vid tecken |

1. Ange den URL som du vill omdirigera upplevelsen till.

1. (Villkorligt) Markera **[!UICONTROL Include Current Query Parameters]** kryssruta.

## Duplicera en upplevelse

Du kan kopiera en upplevelse i en [!UICONTROL A/B Test] så att du kan göra mindre ändringar i den utan att behöva skapa en helt ny upplevelse.

1. På **[!UICONTROL Experiences]** (det första steget i det guidade arbetsflödet i tre steg), klicka på ikonen för lodrät ellips > **[!UICONTROL Duplicate]**.

   ![Alternativet Duplicera upplevelse](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## Ta bort en upplevelse

1. På **[!UICONTROL Experiences]** (det första steget i det guidade arbetsflödet i tre steg), klicka på ikonen för lodrät ellips > **[!UICONTROL Duplicate]**.

   ![Ta bort upplevelsealternativ](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## Utbildningsvideo: Använda [!UICONTROL Visual Experience Composer]

I videon nedan finns information om hur du använder [!UICONTROL Visual Experience Composer] alternativ. (7:17)

* Ändra innehållet på en sida
* Ändra layouten för en sida

>[!VIDEO](https://video.tv.adobe.com/v/17399)
