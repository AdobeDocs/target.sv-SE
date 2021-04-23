---
keywords: mvt;multivariate test;multivariate test create;multivariate test creating;mvt create;mvt creating;mvt how;multivariate test how
description: Lär dig hur du använder Visual Experience Composer (VEC) i Adobe [!DNL Target] för att skapa ett Multivariate Test (MVT) direkt på en [!DNL Target]-aktiverad sida.
title: Hur skapar jag ett multivariata test?
feature: Multivariata tester
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# Skapa ett multivariata test

Med [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] är det enkelt att skapa ett test direkt på en målaktiverad sida och att ändra delar av sidan i [!DNL Target].

Med redigeraren [!DNL Target] kan du välja valfri plats och lägga till flera erbjudanden.

[!UICONTROL Multivariate Test] (MVT) tar en sida i taget. Testet körs med andra ord på en specifik URL-adress med de upplevelser du utformar för sidan.

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**.

   ![Skapa multivariata tester](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på ditt Target-konto. Vissa aktivitetstyper kanske inte visas i listan. [!UICONTROL Automated Personalization] är till exempel en [Target Premium-funktion](/help/c-intro/intro.md#premium).
   >
   >Mer information om de olika aktivitetstyperna som finns i [!DNL Target] och skillnaderna mellan dem finns i [Aktiviteter](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Se [Målaktivitetstyper](/help/c-activities/target-activities-guide.md) för att få hjälp att avgöra vilken aktivitetstyp som bäst uppfyller dina behov.

1. Välj **[!UICONTROL Visual (Default)]** om det behövs.

   ![Skapa multivariat testaktivitet, dialogruta](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-mvt-dialog.png)

   >[!NOTE]
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) om du har problem.
   >
   >Alternativet [!UICONTROL Choose Workplace] i föregående bild är en [Target Premium](/help/c-intro/intro.md)-funktion. Din organisation har en Target Standard-licens om du inte ser det här alternativet.

1. (Villkorligt) Om du är en Target Premium-kund [väljer du en arbetsyta](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Ange ](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) URL-adressen till sidan som du vill testa och klicka sedan på  **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >Använd en fullständig URL, inklusive HTTP eller HTTPS i början.

   Om ett meddelande visas där du uppmanas att aktivera webbläsaren för blandat innehåll följer du instruktionerna i meddelandet. När du har aktiverat din webbläsare för blandat innehåll börjar du om på steg 1.

   Visual Experience Composer öppnas.

1. Ange ett namn för aktiviteten.

   ![Aktivitetsnamnfält](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

1. [Skapa erbjudandena på varje plats](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   ![Dialogrutan Redigera text/HTML](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Du kan lägga till följande typer av erbjudanden:

   * HTML
   * Bild
   * Text

1. Klicka på **[!UICONTROL Preview]** för att [förhandsgranska dina upplevelser](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![Förhandsgranska upplevelser](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   Du kan visa varje upplevelse och utesluta alla som du inte vill ta med i testet. Om du vill utesluta en eller flera upplevelser markerar du de önskade kryssrutorna och klickar sedan på **[!UICONTROL Exclude]** .

   ![Exkludera upplevelser](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [Använd Traffic ](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) Estimatorför att testa om din testplan är genomförbar.

   ![Trafikindikator](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   Bilden nedan visar att aktiviteten inte har tillräckligt med trafik.

   ![](assets/estimator.png)

   Bilden nedan visar att aktiviteten inte har tillräckligt med trafik.

   ![](assets/estimator2.png)

1. Klicka på **[!UICONTROL Next]** för att gå vidare till sidan [!UICONTROL Targeting].

1. Välj målgrupp och procentandel kvalificerade besökare som du vill ange aktiviteten för.

   ![Målsida i MVT-aktivitet](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

   >[!NOTE]
   >
   >Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. [Granska testsammanfattningen ](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) och gör eventuella ändringar. Klicka sedan på  **[!UICONTROL Next]**.

1. [Ange mål och ](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) inställningar för testet.

1. Klicka på **[!UICONTROL Save and Close]** för att skapa aktiviteten.

## Utbildningsvideo: Skapa multivariata tester (9:25) ![Tutorial badge](/help/assets/tutorial.png)

I den här videon visas hur du planerar och skapar ett multivariata test med hjälp av det guidade arbetsflödet i tre steg för Target.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
