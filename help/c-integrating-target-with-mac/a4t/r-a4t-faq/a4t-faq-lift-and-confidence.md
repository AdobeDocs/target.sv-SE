---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;lift;ad hoc;report builder;trust
description: Hitta svar på frågor om lyft och självförtroende när du använder Analytics för [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] aktiviteter.
title: Var hittar jag information om lyft och självförtroende med A4T?
feature: Analyser för mål (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Lyft och tillförsikt - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om lift and trust när [!DNL Adobe Analytics] används som rapportkälla för [!DNL Adobe Target] (A4T).

## Kan jag utföra offlineberäkningar för A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Du kan utföra offlineberäkningar för A4T, men det krävs ett steg med dataexporter i [!DNL Analytics]. Mer information finns i&quot;Utföra offlineberäkningar för målanalys (A4T)&quot; i [Konfidensnivå och konfidensintervall](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Hur beräknas lift? {#section_8CAE788EED5646C4B1D64A0D22070734}

Lyft är den procentuella skillnaden mellan kontrollsidans resultat och en lyckad testvariant.

## Hur beräknas förtroendet? {#section_97DB24D833E742988318CA65DA65DAD9}

Konfidensnivån är sannolikheten för att den uppmätta konverteringsgraden skiljer sig från den främsta konverteringsgraden av andra orsaker än enbart chans.

## Varför kan jag inte se lyft och självförtroende för beräknade mätvärden? {#lift-confidence}

Beräknade mätvärden stöds för närvarande inte för lyftnings- och förtroendefunktioner. Analyser beräknar mätvärden på aggregeringsnivå i stället för på besökarnivå. Särskilt förtroendet är en beräkning på besökarnivå.

Icke-beräknade (standard) händelser stöds i lift och Confidence. De blir täljare i lyftfunktionen. täljaren kan inte vara en beräkning i sig. Nämnaren är normaliseringsmåtten (visningar, besök eller besökare). Exempel på standardhändelser är order, intäkter, aktivitetskonverteringar, anpassade händelser 1-1000 och så vidare. Vanliga optimeringsmått, som konversationshastighet (beställningar/besökare) och RPV (intäkt/besökare) stöds för lyft och förtroende.

Exempel på mätvärden eller användningsfall som inte stöds är:

* Genomsnittligt ordervärde (intäkt/order, per besökare). AOV stöds inte eftersom täljaren är ett beräknat mått. Rekommendationen är i stället att beakta de två påverkande värdena för AOV - Intäkter per besökare och konverteringsgrad.
* Beräknade mått som är summan av standardhändelser. Du kan t.ex. spåra tio olika leadformulär i tio olika händelser och sedan lägga ihop dem för att få ett totalt antal leadinskick. En rekommenderad metod för att spåra dessa händelser är att implementera en enda lead-överföringshändelse i Analytics och sedan använda en eVar för att samla in typen av lead-formulär. Om du använder den här metoden krävs färre variabler och du ser till att du kan använda ett enda lead-överföringsmått för lift- och Confidence-funktioner.

## Hur hanterar A4T tillförlitlighetsberäkningar? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T använder icke-binära måttberäkningar med summan av kvadratiska data. Avvikelsen beräknas med summan av kvadratdata. Extrema order räknas inte. Konfidensberäkningen tillämpar inte heller någon Bonferroni-korrigering för flera erbjudanden.

## Jobbar hiss och självförtroende i Ad Hoc och Report Builder? Kan jag göra det själv om det inte är inbyggt? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Lyft och förtroende fungerar inte i Ad Hoc eller Report Builder och kan inte beräknas själv för kontinuerliga variabler. Det går att beräkna den manuellt för binära mått.
