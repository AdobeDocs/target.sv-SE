---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;lift;ad hoc;report builder;trust
description: Hitta svar på frågor om lyft och förtroende när du använder Analytics för  [!DNL Target] (A4T). Med A4T kan du använda Analytics-rapportering för  [!DNL Target] aktiviteter.
title: Var hittar jag information om lyft och självförtroende med A4T?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Lyft och tillförsikt - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om lift och trust när [!DNL Adobe Analytics] används som rapportkälla för [!DNL Adobe Target] (A4T).

## Kan jag utföra offlineberäkningar för A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

+++Svar
Du kan utföra offlineberäkningar för A4T, men det krävs ett steg med dataexporter i [!DNL Analytics]. Mer information finns i [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Hur beräknas lift? {#section_8CAE788EED5646C4B1D64A0D22070734}

+++Svar
Lyft är procentskillnaden mellan kontrollsidans resultat och en lyckad testvariant.

+++

## Hur beräknas förtroendet? {#section_97DB24D833E742988318CA65DA65DAD9}

+++Svar
Konfidensnivån är en sannolikhet, uttryckt i procent, som är lika med `1 - p-value`, där `p-value` beräknas från ett t-test. Se [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Varför kan jag inte se lyft och självförtroende för beräknade mätvärden? {#lift-confidence}

+++Svar
Beräknade mätvärden stöds för närvarande inte för lyftnings- och förtroendefunktioner. Analyser beräknar mätvärden på aggregeringsnivå i stället för på besökarnivå. Särskilt förtroendet är en beräkning på besökarnivå.

Icke-beräknade (standard) händelser stöds i lift och Confidence. De blir täljare i lyftfunktionen. Täljaren kan inte vara en beräkning i sig. Nämnaren är normaliserande mått (visningar, besök eller besökare). Exempel på standardhändelser är order, intäkter, aktivitetskonverteringar, anpassade händelser 1-1000 och så vidare. Vanliga optimeringsmått, som konversationshastighet (beställningar/besökare) och RPV (intäkt/besökare) stöds för lyft och förtroende.

Exempel på mätvärden eller användningsfall som inte stöds är:

* Genomsnittligt ordervärde (intäkt/order, per besökare). AOV stöds inte eftersom täljaren är ett beräknat mått. Rekommendationen är i stället att beakta de två påverkande värdena för AOV - Intäkter per besökare och konverteringsgrad.
* Beräknade mått som är summan av standardhändelser. Du kan t.ex. spåra tio olika leadformulär i tio olika händelser och sedan lägga ihop dem för att få ett totalt antal leadinskick. En rekommenderad metod för att spåra dessa händelser är att implementera en enda lead-överföringshändelse i Analytics och sedan använda en eVar för att samla in typen av lead-formulär. Om du använder den här metoden krävs färre variabler och du ser till att du kan använda ett enda lead-överföringsmått för lift- och Confidence-funktioner.

+++

## Hur hanterar A4T tillförlitlighetsberäkningar? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++Svar
[!DNL Adobe Analytics] behandlar alla mätvärden som icke-binära och beräknar därför konfidensvärden/p-värden på ett sätt som skiljer sig från användningen av binära mätvärden i ett regelbundet t-test. De beräkningar som används av A4T gör det möjligt för varje användare att få ett kontinuerligt mätresultat (inte bara 1 eller 0 för varje användare), så att variansen (eller relativt standardavvikelsen) för varje upplevelse måste beräknas på rätt sätt. Extrema order räknas inte. Konfidensberäkningen tillämpar inte heller någon Bonferroni-korrigering för flera erbjudanden.

+++

## Jobbar hiss och självförtroende i Ad Hoc och Report Builder? Kan jag göra det själv om det inte är inbyggt? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++Svar
Lyft och förtroende fungerar inte i Ad Hoc eller Report Builder och kan inte beräknas själv för kontinuerliga variabler. Det går att beräkna den manuellt för binära mått.
+++
