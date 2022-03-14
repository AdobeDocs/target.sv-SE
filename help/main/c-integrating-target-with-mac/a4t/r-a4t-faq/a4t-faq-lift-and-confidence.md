---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;lift;ad hoc;report builder;trust
description: Hitta svar på frågor om lyft och självförtroende när ni använder Analytics för [!DNL Target] (A4T). Med A4T kan ni använda analysrapporter för [!DNL Target] verksamhet.
title: Var hittar jag information om lyft och självförtroende med A4T?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Lyft och tillförsikt - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om lyft och självförtroende när man använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

## Kan jag utföra offlineberäkningar för A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Du kan utföra offlineberäkningar för A4T, men det kräver ett steg med dataexport i [!DNL Analytics]. Mer information finns i&quot;Utföra offlineberäkningar för analys av mål (A4T)&quot; i [Konfidensnivå och konfidensintervall](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Hur beräknas lift? {#section_8CAE788EED5646C4B1D64A0D22070734}

Lyft är den procentuella skillnaden mellan kontrollsidans resultat och en lyckad testvariant.

## Hur beräknas förtroendet? {#section_97DB24D833E742988318CA65DA65DAD9}

Konfidensnivån är en sannolikhet, uttryckt i procent, som är lika med `1 - p-value`, där `p-value` beräknas från ett t-test. Se [Konverteringsgrad](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Varför kan jag inte se lyft och självförtroende för beräknade mätvärden? {#lift-confidence}

Beräknade mätvärden stöds för närvarande inte för lyftnings- och förtroendefunktioner. Analyser beräknar mätvärden på aggregeringsnivå i stället för på besökarnivå. Särskilt förtroendet är en beräkning på besökarnivå.

Icke-beräknade (standard) händelser stöds i lift och Confidence. De blir täljare i lyftfunktionen. täljaren kan inte vara en beräkning i sig. Nämnaren är normaliseringsmåtten (visningar, besök eller besökare). Exempel på standardhändelser är order, intäkter, aktivitetskonverteringar, anpassade händelser 1-1000 och så vidare. Vanliga optimeringsmått, som konversationshastighet (beställningar/besökare) och RPV (intäkt/besökare) stöds för lyft och förtroende.

Exempel på mätvärden eller användningsfall som inte stöds är:

* Genomsnittligt ordervärde (intäkt/order, per besökare). AOV stöds inte eftersom täljaren är ett beräknat mått. Rekommendationen är i stället att beakta de två påverkande värdena för AOV - Intäkter per besökare och konverteringsgrad.
* Beräknade mått som är summan av standardhändelser. Du kan t.ex. spåra tio olika leadformulär i tio olika händelser och sedan lägga ihop dem för att få ett totalt antal leadinskick. En rekommenderad metod för att spåra dessa händelser är att implementera en enda lead-överföringshändelse i Analytics och sedan använda en eVar för att samla in typen av lead-formulär. Om du använder den här metoden krävs färre variabler och du ser till att du kan använda ett enda lead-överföringsmått för lift- och Confidence-funktioner.

## Hur hanterar A4T tillförlitlighetsberäkningar? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

[!DNL Adobe Analytics] behandlar alla mätvärden som icke-binära och beräknar därför konfidensvärden/p-värden på ett sätt som skiljer sig från användningen av binära mätvärden i ett regelbundet t-test. De beräkningar som används av A4T gör det möjligt för varje användare att få ett kontinuerligt mätresultat (inte bara 1 eller 0 för varje användare), så att variansen (eller relativt standardavvikelsen) för varje upplevelse måste beräknas på rätt sätt. Extrema order räknas inte. Konfidensberäkningen tillämpar inte heller någon Bonferroni-korrigering för flera erbjudanden.

## Jobbar hiss och självförtroende i Ad Hoc och Report Builder? Kan jag göra det själv om det inte är inbyggt? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Lyft och förtroende fungerar inte i Ad Hoc eller Report Builder och kan inte beräknas själv för kontinuerliga variabler. Det går att beräkna den manuellt för binära mått.
