---
keywords: Klicka på spårning;spåra klick;klicka;AppMeasurement
description: Lär dig mer [!DNL Adobe Target] gör att du kan spåra klick på ett element som ett framgångsmått.
title: Vad är Click Tracking?
feature: Success Metrics
exl-id: 9181424b-179e-49fc-b760-b764a0c3458a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Klickspårning

[!DNL Adobe Target] gör att du kan spåra klick på ett element som ett framgångsmått.

>[!NOTE]
>
>Spårningsklickningar stöds inte på den globala [!DNL Target] begära när den används som en plats i en formulärbaserad aktivitet.

## Ställ in klickspårning {#section_5540C5A533114E57BAE022A600B02E72}

1. När du ställer in dina mål på [!UICONTROL Goals & Settings] väljer du **[!UICONTROL Conversion]** framgångsmått.
1. Välj **[!UICONTROL Clicked an element]** och sedan klicka **[!UICONTROL Select elements]**.

   Sidan öppnas i [!UICONTROL Visual Experience Composer] (VEC).

1. Markera de element som du vill spåra.

   Se *Överväganden* nedan för tips om hur du väljer element.

1. Klicka **[!UICONTROL Save]** längst upp på skärmen för att spara dina val.

När en aktivitetsdeltagare klickar på ett markerat element räknas det klicket som en konvertering.

## Panelen Markerade element {#selected-elements}

För [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP), och [!UICONTROL Multivariate Test] MVT-verksamhet, [!UICONTROL Selected Elements] På panelen visas de markerade elementen för klickspårning till höger.

![Panelen Markerade element](/help/main/c-activities/r-success-metrics/assets/selected-elements.png)

Det finns flera åtgärder som kan användas när du håller muspekaren över ett element i [!UICONTROL Selected Elements] -panelen. I följande tabell beskrivs varje åtgärd som kan utföras på ett element:

| Åtgärd | Beskrivning |
| --- | --- |
| Information | Visar elementtypen och den fullständiga DOM-sökvägen till väljaren. |
| Redigera | Gör att du kan redigera CSS-väljaren. |
| Ta bort | Tar bort elementet. |

### Lägg till element

Om du redan känner till DOM-sökvägen till väljaren kan du lägga till den manuellt genom att klicka på plusikonen högst upp på panelen.

![Ikonen Lägg till element](/help/main/c-activities/r-success-metrics/assets/add-element.png)

### Popup för markerade element

När du har markerat flera element för klickspårning kan du klicka på [!UICONTROL Elements Selected] länk till aktivitetens [!UICONTROL Goals & Settings] om du vill visa en fullständig lista över de element som har valts för klickspårning. Listan innehåller den fullständiga DOM-sökvägen för elementet som hjälper dig att validera att det markerade elementet ska användas för klickspårning.

![Länk för markerade element](/help/main/c-activities/r-success-metrics/assets/elements-selected-link.png)

## Överväganden {#considerations}

Det finns flera saker att tänka på när du markerar element:

* DOM-sökvägsfunktionen är tillgänglig när du ställer in klickspårning. När du klickar på ett element på sidan visas VEC-alternativmenyn. Dessutom visas motsvarande DOM-sökväg längst ned på sidan. Du kan använda DOM-sökvägen för att snabbt visa information om det markerade elementet (typ, ID och klass) och flytta upp eller ned DOM-sökvägen för att markera det önskade elementet.

   ![DOM-banillustration](/help/main/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   Precis som när du skapar upplevelser i steg 1 i arbetsflödet för att skapa aktiviteter kan du välja ett element med DOM-sökvägsväljaren längst ned på sidan. När du väljer ett element från DOM-sökvägen visas motsvarande element i VEC som&quot;Markerat&quot;. Om du vill avmarkera ett markerat element kan du klicka på elementet igen i DOM-banväljaren eller klicka på rutan Markerat i VEC.

   Mer information finns i [Navigera mellan element med DOM-sökvägen](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) in *Alternativ för Visual Experience Composer*.

* Du kan bläddra till en annan sida för att spåra klick på en sida där du kanske inte ändrar innehåll. Den här andra sidan måste inkluderas i aktiviteten med [flersidig funktion](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) och [!DNL at.js] måste implementeras på den.
* Om du markerar mer än ett element, och en deltagare klickar på något av de valda elementen, räknas klickningen. Om du vill räkna varje objekt för sig anger du individuella framgångsmått för varje element. Om du vill räkna ett objekt genom att klicka på flera element på en sida redigerar du CSS-elementväljaren så att den matchar flera element.
* Se till att du väljer den elementnivå som du vill spåra. Om du till exempel anger en knapp måste du markera länken och inte knapptexten.
* Klickhändelser skickas till [!DNL Target] på samma sida som klickningen.
* Om klickspårningsmåttet är målmåttet för ett [!UICONTROL Analytics for Target] (A4T) måste besökaren klicka på det här elementet inom 60 sekunder från sidan som läses in för att mätvärdet ska kunna spåras.
* Klickspårning fungerar inte för element som innehåller escape-tecken i sina väljare, inklusive följande:

   | Tecken | Beskrivning |
   |---|---|
   | # | Nummertecken eller hash |
   | : | Colon |
   | . | Period |
   | $ | Dollar-tecken |
   | `[ ]` | Fyrkantiga parenteser |

* Om du använder [!DNL at.js] klickspårning och du använder [!DNL Analytics] AppMeasurement, [!DNL at.js] click tracking avbryter alla andra klickhändelsehanterare. Därför körs aldrig klickhanteraren för AppMeasurement.

   [!DNL at.js] har specialhantering för klickspårning när det underliggande elementet är ett `A` (link)-tagg eller `FORM` -tagg.

   Följande steg utförs av [!DNL at.js] när klickspårningshändelsen är kopplad till en `A` (link) eller en `FORM` tagg:

   1. Anropa `event.preventDefault()`.

   1. Eld [!DNL Target] begäran.

   1. På [!DNL Target] fråga om lyckad eller felåteranrop, kör standardbeteende:

      * `A` (link)-tagg: Standardbeteendet är att navigera till den URL som definieras av HREF-attributet.
      * `FORM` tagg: Standardbeteendet är att skicka formuläret.

   Detta standardbeteende kan störa [!DNL Analytics] klickspårning. Om du använder [!DNL Analytics]bör du lita på [!DNL Analytics] för klickspårning i stället för [!DNL Target].

* Klickspårning registreras inte på sidor där sid- och aktivitets-URL:en tillhör olika egenskaper. Enterprise-användarbehörigheter är [!DNL Target Premium] -funktion. Mer information finns i [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

* Klickspårningsstatistik är inte länkade till någon specifik upplevelse i en aktivitet.

* Använd målgrupper om det är nödvändigt att begränsa omfattningen av klickspårningsmätningarna.

* Flera aktiviteter kan definiera ett klickspårsmått för samma väljare. Om så är fallet, när en besökare kvalificerar sig för någon av dessa aktiviteter och klickar på väljaren, ökar klickspårningsmåttet för alla associerade aktiviteter som besökaren är kvalificerad för.

## Utbildningsvideo {#section_36607204DAE146E3B8E2C609D244EDB1}

Den här videon innehåller information om hur du skapar framgångsmått för klickspårning.

* Förstå målvärden
* Förstå och bygga [!UICONTROL Conversion], [!UICONTROL Revenue]och [!UICONTROL Engagement] mått
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
