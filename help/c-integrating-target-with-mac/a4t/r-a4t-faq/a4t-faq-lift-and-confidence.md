---
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report builder;confidence
description: Det här avsnittet innehåller svar på frågor som ofta ställs om lift och självförtroende när Analytics används som rapportkälla för Target (A4T).
title: Lyft och tillförsikt - A4T FAQ
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Lyft och tillförsikt - A4T FAQ{#lift-and-confidence-a-t-faq}

Det här avsnittet innehåller svar på frågor som ofta ställs om lift och självförtroende när Analytics används som rapportkälla för Target (A4T).

## Kan jag utföra offlineberäkningar för A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Du kan utföra offlineberäkningar för A4T, men det krävs ett steg med dataexport i [!DNL Analytics]. Mer information finns i&quot;Utföra offlineberäkningar för målanalys (A4T)&quot; i [konfidensnivå och konfidensintervall](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Hur beräknas lift? {#section_8CAE788EED5646C4B1D64A0D22070734}

Lyft är den procentuella skillnaden mellan kontrollsidans resultat och en lyckad testvariant.

## Hur beräknas förtroendet? {#section_97DB24D833E742988318CA65DA65DAD9}

Konfidensnivån är sannolikheten för att den uppmätta konverteringsgraden skiljer sig från den främsta konverteringsgraden av andra orsaker än enbart chans.

## Varför kan jag inte se lyft och självförtroende för beräknade mätvärden? {#section_D3E44E24782A409DBD88AE4D1595CB58}

Lyft och förtroende kan för närvarande inte genereras för beräknade värden. I de flesta fall bör detta dock inte vara något problem eftersom lyften normaliseras genom normaliseringsmåttet. Om du t.ex. väljer ökning för order och normaliseringsmåttet är besök, beräknas ökningen utifrån förhållandet mellan de två, vilket är konverteringsgraden.

## Hur hanterar A4T tillförlitlighetsberäkningar? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T använder icke-binära måttberäkningar med summan av kvadratiska data. Avvikelsen beräknas med summan av kvadratdata. Extrema order tas inte med i beräkningen.

Alla Analytics-segment kan tillämpas på rapporten. Det är så du kan få den&quot;extrema ordningen&quot; bland andra segmentalternativ. Ett mätvärde kan också skapas för att begränsa exempelvis hur många gånger en besökare konverteras.

## Fungerar lyft och förtroende i Ad Hoc och Report Builder? Kan jag göra det själv om det inte är inbyggt? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Lyft och förtroende fungerar inte i Ad Hoc eller Report Builder och kan inte beräknas själv för kontinuerliga variabler. Det går att beräkna den manuellt för binära mått.
