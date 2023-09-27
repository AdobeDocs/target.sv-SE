---
keywords: mvt;multivariate test;multivariate test create;multivariate test creating;mvt create;mvt creating;mvt how;multivariate test how
description: Lär dig använda [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] för att skapa [!UICONTROL Multivariate Test] (MVT).
title: Hur skapar jag en [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 0%

---

# Skapa ett multivariata test

The [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] gör det enkelt att skapa en [!UICONTROL Multivariate Test] och ändra delar av sidan på [!DNL Target].

The [!DNL Target] Med redigeraren kan du välja valfri plats och lägga till flera erbjudanden.

The [!UICONTROL Multivariate Test] (MVT) tar en sida i taget. Testet körs med andra ord på en specifik URL-adress med de upplevelser du utformar för sidan.

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**.

   ![Skapa multivariata tester](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >Mer information om de olika aktivitetstyperna finns i [!DNL Target] och skillnaderna [Verksamhet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Se [Typ av målaktivitet](/help/main/c-activities/target-activities-guide.md) för att hjälpa dig att avgöra vilken typ av aktivitet som bäst passar dina behov.

1. (Villkorligt) Välj leveranstyp: [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL Email], eller [!UICONTROL Other/API].

1. (Villkorligt) Om du är en [Mål Premium](/help/main/c-intro/intro.md#premium) kund, [välja en arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Ange URL-adressen](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) för sidan som du vill testa och klicka sedan på **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >Använd en fullständig URL, inklusive HTTP eller HTTPS i början.

   Om ett meddelande visas där du uppmanas att aktivera webbläsaren för blandat innehåll följer du instruktionerna i meddelandet. När du har aktiverat din webbläsare för blandat innehåll börjar du om på steg 1.

   The [!UICONTROL Visual Experience Composer] öppnas.

1. Ange ett namn för aktiviteten.

   ![Aktivitetsnamnfält](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

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

1. [Skapa erbjudanden på varje plats](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   ![Redigera text/HTML, dialogruta](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Du kan lägga till följande typer av erbjudanden:

   * HTML
   * Bild
   * Text

1. Klicka **[!UICONTROL Preview]** till [förgranska era upplevelser](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![Förhandsgranska upplevelser](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   Du kan visa varje upplevelse och utesluta alla som du inte vill ta med i testet. Om du vill utesluta en eller flera upplevelser markerar du de önskade kryssrutorna och klickar sedan på **[!UICONTROL Exclude]** .

   ![Exkludera upplevelser](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [Använda Traffic Estimator](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) för att testa om din testplan är genomförbar.

   ![Trafikindikator](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   Bilden nedan visar att aktiviteten inte har tillräckligt med trafik.

   ![uppskattningsbild](assets/estimator.png)

   Bilden nedan visar att aktiviteten inte har tillräckligt med trafik.

   ![estimator2-bild](assets/estimator2.png)

1. Klicka **[!UICONTROL Next]** för att gå vidare till [!UICONTROL Targeting] sida.

1. Välj målgrupp och procentandel kvalificerade besökare som du vill ange aktiviteten för.

   ![Målsida i MVT-aktivitet](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

   >[!NOTE]
   >
   >Förutom att välja en befintlig målgrupp kan ni kombinera flera målgrupper för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp. Mer information finns i [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. [Granska testsammanfattningen](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) och gör de ändringar du vill och klicka sedan på **[!UICONTROL Next]**.

1. [Ange mål och inställningar](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) för testet.

1. Klicka **[!UICONTROL Save and Close]** för att skapa aktiviteten.

## Utbildningsvideo: Skapa multivariata tester (9:25) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon visas hur du planerar och skapar ett multivariata test med [!DNL Target] guidat arbetsflöde i tre steg.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
