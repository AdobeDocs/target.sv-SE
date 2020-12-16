---
keywords: Click tracking;track clicks;clicks;AppMeasurement
description: Med Target kan du spåra klick på ett element som ett framgångsmått.
title: Klickspårning
feature: success metrics
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 0%

---


# Klicka på spårning{#click-tracking}

Med Target kan du spåra klick på ett element som ett framgångsmått.

>[!NOTE]
>
>Spårningsklickningar stöds inte i den globala Target-begäran när den används som en plats i en formulärbaserad aktivitet.

## Konfigurera klickspårning {#section_5540C5A533114E57BAE022A600B02E72}

1. När du anger dina mål på [!UICONTROL Goals & Settings]-sidan för din aktivitet väljer du måttet **[!UICONTROL Conversion]** för framgång.
1. För åtgärden väljer du **[!UICONTROL Clicked an element]** och klickar sedan på **[!UICONTROL Select elements]**.

   Sidan öppnas i [!UICONTROL Visual Experience Composer] (VEC).

1. Markera de element som du vill spåra.

   Se avsnittet Saker att tänka på nedan för tips om hur du väljer element.

1. Klicka på bockmarkeringen längst upp på skärmen för att spara dina val.

När en aktivitetsdeltagare klickar på ett markerat element räknas det klicket som en konvertering.

## Panelen Valda element {#selected-elements}

För A/B-tester, Experience Targeting (XT), Automated Personalization (AP) och Multivariate Test (MVT) visas en [!UICONTROL Selected Elements]-panel med alla markerade element för klickspårning till höger.

![Panelen Markerade element](/help/c-activities/r-success-metrics/assets/selected-elements.png)

Det finns flera åtgärder som kan användas när du hovrar över ett element på panelen [!UICONTROL Selected Elements]. I följande tabell beskrivs varje åtgärd som kan utföras på ett element:

| Åtgärd | Beskrivning |
| --- | --- |
| Information | Visar elementtypen och den fullständiga DOM-sökvägen till väljaren. |
| Redigera | Gör att du kan redigera CSS-väljaren. |
| Ta bort | Tar bort elementet. |

### Lägg till element

Om du redan känner till DOM-sökvägen till väljaren kan du lägga till den manuellt genom att klicka på plusikonen som finns högst upp på panelen.

![Ikonen Lägg till element](/help/c-activities/r-success-metrics/assets/add-element.png)

### Popup för hovring av markerade element

När du har markerat flera element för klickspårning kan du klicka på länken [!UICONTROL Elements Selected] i aktivitetens [!UICONTROL Goals & Settings]-steg för att se den fullständiga listan över element som har markerats för klickspårning. Listan innehåller den fullständiga DOM-sökvägen för elementet som hjälper dig att validera att det markerade elementet ska användas för klickspårning.

![Länk för markerade element](/help/c-activities/r-success-metrics/assets/elements-selected-link.png)

## Överväganden {#considerations}

Det finns flera saker att tänka på när du markerar element:

* DOM-sökvägsfunktionen är tillgänglig när du ställer in klickspårning. När du klickar på ett element på sidan visas VEC-alternativmenyn. Dessutom visas motsvarande DOM-sökväg längst ned på sidan. Du kan använda DOM-sökvägen för att snabbt visa information om det markerade elementet (typ, ID och klass) och flytta upp eller ned DOM-sökvägen för att markera det önskade elementet.

   ![DOM-banillustration](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   Precis som när du skapar upplevelser i steg 1 i arbetsflödet för att skapa aktiviteter kan du välja ett element med DOM-sökvägsväljaren längst ned på sidan. När du väljer ett element från DOM-sökvägen visas motsvarande element i VEC som&quot;Markerat&quot;. Om du vill avmarkera ett markerat element kan du klicka på elementet i DOM-sökvägsväljaren eller klicka på rutan Markerat i VEC.

   Mer information finns i [Navigera mellan element med DOM-sökvägen](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) i *Alternativ för Visual Experience Composer*.

* Du kan bläddra till en annan sida för att spåra klick på en sida där du kanske inte ändrar innehåll. Den här andra sidan måste inkluderas i aktiviteten med flersidesfunktionen [](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) och [!DNL at.js] eller [!DNL mbox.js] måste implementeras på den.
* Om du markerar mer än ett element, och en deltagare klickar på något av de valda elementen, räknas klickningen. Om du vill räkna varje objekt för sig anger du individuella framgångsmått för varje element. Om du vill räkna ett objekt genom att klicka på flera element på en sida redigerar du CSS-elementväljaren så att den matchar flera element.
* Se till att du väljer den elementnivå som du vill spåra. Om du till exempel anger en knapp måste du markera länken och inte knapptexten.
* Klickhändelser skickas till [!DNL Target] på samma sida som klickningen.
* Om klickspårningsmåttet är målmåttet för en A4T-aktivitet måste besökaren klicka på det här elementet inom 60 sekunder från inläsningen för att mätvärdet ska kunna spåras.
* Klickspårning fungerar inte för element som innehåller escape-tecken i sina väljare, inklusive följande:

   | Tecken | Beskrivning |
   |---|---|
   | # | Nummertecken eller hash |
   | : | Colon |
   | . | Period |
   | $ | Dollar-tecken |
   | `[ ]` | Fyrkantiga parenteser |

* Om du använder [!DNL at.js] klickspårning och även använder Analytics AppMeasurement, avbryter klickspårning alla andra klickhändelsehanterare. [!DNL at.js] Därför körs aldrig klickhanteraren för AppMeasurement.

   [!DNL at.js] har specialhantering för klickspårning när det underliggande elementet är en  `A` (link)-tagg eller - `FORM` tagg.

   Följande steg utförs av [!DNL at.js] när klickspårningshändelsen är kopplad till en `A` (link)-tagg eller en `FORM`-tagg:

   1. Anropa `event.preventDefault()`.

   1. Fire Target-begäran.

   1. Kör standardbeteendet om Target-begäran lyckas eller om ett fel uppstår:

      * `A` (link)-tagg: Standardbeteendet är att navigera till den URL som definieras av HREF-attributet.
      * `FORM` tagg: Standardbeteendet är att skicka formuläret.

   Detta standardbeteende kan störa klickspårningen i Analytics. Om ni använder Analytics bör ni förlita er på Analytics för klickspårning i stället för Target.

* Klickspårning registreras inte på sidor där sid- och aktivitets-URL:en tillhör olika egenskaper. Enterprise-användarbehörigheter är en Target Premium-funktion. Mer information finns i [Företagsanvändarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md).

## Utbildningsvideo {#section_36607204DAE146E3B8E2C609D244EDB1}

Den här videon innehåller information om hur du skapar framgångsmått för klickspårning.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)