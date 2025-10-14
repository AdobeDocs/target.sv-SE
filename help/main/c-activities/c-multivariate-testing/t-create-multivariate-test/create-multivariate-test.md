---
keywords: mvt;multivariate test;multivariate test create;multivariate test creating;mvt create;mvt creating;mvt how;multivariate test how
description: Lär dig hur du använder [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target]  för att skapa en [!UICONTROL Multivariate Test] (MVT).
title: Hur skapar jag en [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: 9cc1eb4c5c95ea51bc0a1fc9e89b245a18c9914b
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Skapa ett multivariata test

Med [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] är det enkelt att skapa en [!UICONTROL Multivariate Test] och att ändra delar av sidan i [!DNL Target].

Med redigeraren för peka och klicka på [!DNL Target] kan du välja valfri plats och lägga till flera erbjudanden.

[!UICONTROL Multivariate Test] (MVT) tar en sida i taget. Testet körs med andra ord på en specifik URL-adress med de upplevelser du utformar för sidan.

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**.

   >[!NOTE]
   >
   >Mer information om de olika aktivitetstyperna i [!DNL Target] och skillnaderna mellan dem finns i [Aktiviteter](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Se [Målaktivitetstyper](/help/main/c-activities/target-activities-guide.md) som hjälper dig att avgöra vilken aktivitetstyp som bäst uppfyller dina behov.

1. (Villkorligt) Välj leveranstyp: [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL Email] eller [!UICONTROL Other/API].

1. (Villkorligt) Om du är [Target Premium](/help/main/c-intro/intro.md#premium)-kund [väljer du en arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Ange URL:en](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) för sidan som du vill testa och klicka sedan på **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >Använd en fullständig URL, inklusive HTTP eller HTTPS i början.

   Om ett meddelande visas där du uppmanas att aktivera webbläsaren för blandat innehåll följer du instruktionerna i meddelandet. När du har aktiverat din webbläsare för blandat innehåll börjar du om på steg 1.

   [!UICONTROL Visual Experience Composer] öppnas.

1. Om du vill namnge aktiviteten klickar du på ikonen **[!UICONTROL Edit]** ( ![Redigera-ikon](/help/main/assets/icons/Edit.svg) ) bredvid [!UICONTROL Untitled Activity], anger ett beskrivande namn för aktiviteten och klickar sedan på **[!UICONTROL Save]**.

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

   Aktivitetsnamnet får inte innehålla någon av följande teckensekvenser:

   | Teckensekvens | Beskrivning |
   |--- |--- |
   | ;= | Semikolon, lika med |
   | ;+ | Semikolon, Plus |
   | ;- | Semikolon, minus |
   | ;@ | Semikolon, tecken |
   | ,= | Komma, motsvarar |
   | ,+ | komma, plus |
   | ,- | Komma, Minus |
   | ,@ | Komma, Vid tecken |
   | `[`&quot; | Öppen hakparentes, dubbla citattecken |
   | &quot;`]` | Dubbla citattecken, avslutande hakparentes |

1. [Skapa erbjudandena på varje plats](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Du kan lägga till följande typer av erbjudanden:

   * HTML
   * Bild
   * Text

1. Klicka på **[!UICONTROL Preview]** för att [förhandsgranska dina upplevelser](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Klicka på ikonen **[!UICONTROL Show Experiences]** ( ![&#x200B; ikonen Visa upplevelser &#x200B;](/help/main/assets/icons/WebPages.svg) ) för att visa listan med alla upplevelser i den vänstra bildrutan.

1. Klicka på en specifik upplevelse i listan för att visa den upplevelsen.

1. (Villkorligt) Om du vill utesluta en eller flera upplevelser från aktiviteten klickar du på ikonen **[!UICONTROL Manage Content]** ( ![ikonen Hantera upplevelser &#x200B;](/help/main/assets/icons/Experience.svg) ) för att visa dialogrutan [!UICONTROL Manage Experiences].

1. (Villkorligt) I dialogrutan [!UICONTROL Manage Experiences] klickar du på ikonen **[!UICONTROL More Actions]** ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmallList.svg) ) bredvid den upplevelse som du vill utesluta och klickar sedan på **[!UICONTROL Exclude]**.

   Du kan välja att exkludera en upplevelse som visar variationer i konflikt eller en upplevelse som inte är estetiskt balanserad.

1. (Villkorligt) Om du vill utesluta flera upplevelser markerar du kryssrutorna för de önskade upplevelserna och klickar sedan på **[!UICONTROL Exclude]**.

1. [Använd Traffic Estimator](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) för att testa om din testplan är genomförbar.

1. Klicka på **[!UICONTROL Next]** om du vill gå vidare till sidan [!UICONTROL Targeting].

   Steget **Mål** ser bekant ut om du har använt andra [!DNL Target]-aktivitetstyper. Här kan du välja en målgrupp och ange hur många besökare som ska se varje upplevelse.

   Flödesdiagrammet leder dig genom stegen för att tilldela en målgrupp och dess trafikprocent, välja trafikallokeringsmetod och specificera trafikallokeringen för varje upplevelse i aktiviteten.

1. (Villkorligt) Klicka på kontrollen **[!UICONTROL All Visitors]** för att välja en annan målgrupp för aktiviteten.

   [!UICONTROL All Visitors]-målgruppen är inställd som standard. Om du väljer en annan målgrupp visas dess namn längst till vänster.

   Den högra bildrutan visas, vilket gör att du kan lägga till eller ta bort en målgrupp och tilldela besökarprocenten för aktiviteten.

   1. Om du vill ändra målgruppen klickar du på ikonen **[!UICONTROL Replace]** ( ![ikonen Ersätt](/help/main/assets/icons/Retweet.svg) ) i den högra ramen.
   1. I dialogrutan [!UICONTROL Add Audience] [väljer du önskad målgrupp](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) och klickar sedan på **[!UICONTROL Assign Audience]**.

      Du kan klicka på **Kombinera målgrupper** för att [skapa en målgrupp som kombinerar flera målgrupper](/help/main/c-target/combining-multiple-audiences.md).

      Om du behöver skapa en ny målgrupp som inte redan finns i [!UICONTROL Audience Library] klickar du på **Skapa målgrupp**. Under arbetsflödet [skapa målgrupper](/help/main/c-target/c-audiences/audiences.md) kan du välja bland följande alternativ:

      * **[!UICONTROL Audience Library]**: Skapa en målgrupp på begäran som sparas i [!UICONTROL Audience Library] som kan återanvändas i andra aktiviteter.
      * **[!UICONTROL This activity only]**: Skapa en [aktivitetsspecifik målgrupp](/help/main/c-target/creating-activity-only-audience.md) som inte har sparats i [!UICONTROL Audience Library] och som bara kan användas i den aktuella aktiviteten.

   1. Klicka på **[!UICONTROL Visitor Percentage]** i den högra bildrutan och välj sedan den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. [Granska testsammanfattningen](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) och gör eventuella ändringar. Klicka sedan på **[!UICONTROL Next]**.

1. [Ange mål och inställningar](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) för testet.

1. Klicka på **[!UICONTROL Save and Close]** för att skapa aktiviteten.

## Utbildningsvideo: Skapa multivariata tester (9:25) ![Självstudiekurs &#x200B;](/help/main/assets/tutorial.png)

I den här videon visas hur du planerar och skapar ett multivariata test med hjälp av det guidade arbetsflödet i [!DNL Target] i tre steg.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
