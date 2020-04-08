---
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report builder;confidence
description: Det här avsnittet innehåller svar på frågor som ofta ställs om lift och självförtroende när Analytics används som rapportkälla för Target (A4T).
title: Lyft och tillförsikt - A4T FAQ
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: a06747412ba93cacb012e0d68334590fc3d52ab7

---


# Lyft och tillförsikt - A4T FAQ{#lift-and-confidence-a-t-faq}

Det här avsnittet innehåller svar på frågor som ofta ställs om lift och självförtroende när Analytics används som rapportkälla för Target (A4T).

## Kan jag utföra offlineberäkningar för A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Du kan utföra offlineberäkningar för A4T, men det krävs ett steg med dataexport i [!DNL Analytics]. Mer information finns i&quot;Utföra offlineberäkningar för målanalys (A4T)&quot; i [konfidensnivå och konfidensintervall](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Hur beräknas lift? {#section_8CAE788EED5646C4B1D64A0D22070734}

Lyft är den procentuella skillnaden mellan kontrollsidans resultat och en lyckad testvariant.

## Hur beräknas förtroendet? {#section_97DB24D833E742988318CA65DA65DAD9}

Konfidensnivån är sannolikheten för att den uppmätta konverteringsgraden skiljer sig från den främsta konverteringsgraden av andra orsaker än enbart chans.

## Varför kan jag inte se lyft och självförtroende för beräknade mätvärden? {#lift-confidence}

Lyft och förtroende stöds för närvarande inte med beräknade värden. I de flesta fall bör detta emellertid inte vara något problem eftersom den konverteringsgrad som beräknas i A4T-rapporten redan är ett beräknat mått där nämnaren är det normaliserande måttet (instanser, besök eller besökare). Om du till exempel väljer ordermåttet och normaliseringsmåttet är besökare, beräknas konverteringsgraden (order/besökare) automatiskt genom A4T-rapportering. Det resulterande lyftmåttet visar skillnaden i konverteringsgraden mellan textupplevelserna jämfört med standardvärdet.

De flesta beräknade mätvärdena för optimering kan delas in i en av två kategorier: aggregerade mått eller andra konverteringsberäkningar, t.ex. genomsnittligt ordervärde (AOV).

Sammanställningsvärden används när en organisation använder unika händelser för att fånga upp olika&quot;smak&quot; i den sparade konverteringen. Om du till exempel vill befordra inskickade formulär och har tio olika formulär kan du skapa unika händelser för att räkna varje typ av formulärkonvertering. Om du vill se den totala kvantiteten av alla formulär som skickats in för lead måste du skapa ett enkelt beräknat mått för att lägga ihop dem. Ett bättre och modernare sätt att spåra detta är att implementera en enda lead-submit-händelse i Analytics och sedan använda en eVar för att samla in typen av lead-formulär. Metoden kräver färre variabler och eliminerar behovet av att samla in enskilda värden, och du kan fortfarande se en helhetsbild av konverteringen av lead-form och dela upp den efter typ av lead-formulär med eVar. Detta eliminerar också behovet av aggregerade mätvärden vid utvärdering av prestandan för en Target-aktivitet.

Ett annat vanligt beräknat mätvärde, Average Order Value, stöds för närvarande inte med lyft och självförtroende eftersom det normaliserade måttet inte är ett standardmått (instanser, besök eller besökare). Rekommendationen är i stället att hålla ett öga på de två påverkande mätvärdena för AOV, Intäkter per besökare och konverteringsgrad.

## Hur hanterar A4T tillförlitlighetsberäkningar? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T använder icke-binära måttberäkningar med summan av kvadratiska data. Avvikelsen beräknas med summan av kvadratdata. Extrema order tas inte med i beräkningen.

Alla Analytics-segment kan tillämpas på rapporten. Det är så du kan få den&quot;extrema ordningen&quot; bland andra segmentalternativ. Ett mätvärde kan också skapas för att begränsa exempelvis hur många gånger en besökare konverteras.

## Fungerar lyft och förtroende i Ad Hoc och Report Builder? Kan jag göra det själv om det inte är inbyggt? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Lyft och förtroende fungerar inte i Ad Hoc eller Report Builder och kan inte beräknas själv för kontinuerliga variabler. Det går att beräkna den manuellt för binära mått.
