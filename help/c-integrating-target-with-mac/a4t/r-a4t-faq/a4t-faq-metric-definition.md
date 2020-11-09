---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: Det här avsnittet innehåller svar på frågor som ofta ställs om metriska definitioner och som använder Analytics som rapportkälla för Target (A4T).
title: Måttdefinitioner - A4T FAQ
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---


# Måttdefinitioner - A4T FAQ{#metric-definitions-a-t-faq}

Det här avsnittet innehåller svar på frågor som ofta ställs om metriska definitioner och som använder Analytics som rapportkälla för Target (A4T).

## Vad gäller för aktivitetsmedlemskap? Hur länge efter att besökarna har gått in i aktiviteten räknas deras aktiviteter in i aktiviteten om de inte ser den igen? {#section_41B4958F33534E4B96DEE0C981227A79}

Standardförfallotiden för aktiviteten är 90 dagar efter en besökares senaste interaktion med aktiviteten. Detta kan justeras av ClientCare vid behov. Den här inställningen är global för alla aktiviteter, så den bör inte justeras för ett fall.

## Fungerar de avancerade alternativen för framgångsmått i Target med A4T? {#section_F060E3438F4144258BB95813EDEABDAA}

Dessa alternativ fungerar för närvarande inte med A4T.

## Vad är beräknade mätvärden och hur ersätter de SiteCatalyst:Event-rutan som jag använde tidigare? {#section_D59F4719E6B94758A2187427C17F8EF3}

Med beräknade mätvärden kan du skapa anpassade mätvärden som härleds från segment eller matematiska beräkningar. Tidigare när du kanske använde mbox där `SiteCatlayst:Event` och händelsen är `evar27=shoes` skulle du nu skapa ett segment där `purchase`och sedan skapa ett beräknat mått där händelsen är `evar27=shoes` `purchase` med segmentet tillämpat. Fördelen med detta är att dessa mätvärden kan skapas när som helst, även efter att aktiviteten har startats. De kan sedan användas på alla rapporter i Analytics.

## Attributar A4T konverteringar till flera kampanjer? {#section_7F15C727206440CD86B3A8CE77087DF9}

Ja. Detta görs med inställningen &quot;Full allokering&quot;.
