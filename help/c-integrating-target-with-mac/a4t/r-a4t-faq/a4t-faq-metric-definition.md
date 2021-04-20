---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;mått;måttdefinitioner
description: Hitta svar på frågor om metriska definitioner och användning av Analytics for Target (A4T). Med A4T kan ni använda Analytics-rapportering med Adobe Target-aktiviteter.
title: Var hittar jag information om metriska definitioner med A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: e45f0d2d2370f9c7aba2c2bd26afdd4c0e401db8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Måttdefinitioner - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om metriska definitioner och använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

## Vad gäller för aktivitetsmedlemskap? Hur lång tid efter att besökarna har gått in i aktiviteten räknas deras aktiviteter in om de inte ser den igen? {#section_41B4958F33534E4B96DEE0C981227A79}

Standardförfallotiden för aktiviteten är 90 dagar efter en besökares senaste interaktion med aktiviteten. Den här inställningen kan justeras av ClientCare vid behov. Den här inställningen är global för alla aktiviteter, så den bör inte justeras för ett fall.

## Varför har jag inte åtkomst till alternativen för Avancerade inställningar när jag konfigurerar mina målvärden? {#adv-settings}

Alternativen [!UICONTROL Advanced Settings] är inte tillgängliga för aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T).

För aktiviteter som använder A4T använder målmåttet alltid inställningarna [!UICONTROL Increment Count & Keep User in Activity] och [!UICONTROL On Every Impression]. Dessa inställningar är *inte* konfigurerbara.

För andra aktiviteter än A4T kan du använda [alternativen för avancerade inställningar](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) för att hantera hur du mäter framgång. Du kan lägga till beroenden, välja om du vill behålla användaren i aktiviteten eller ta bort dem och om mätvärdet ska räknas en gång per deltagare eller vid varje intryck. Du kommer åt alternativen för [!UICONTROL Advanced Settings] i en annan aktivitet än A4T genom att klicka på de lodräta ellipserna > [!UICONTROL Advanced Settings], vilket visas nedan:

![Avancerade inställningar](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## Vad är beräknade mätvärden och hur ersätter de SiteCatalyst:Event-rutan som jag använde tidigare? {#section_D59F4719E6B94758A2187427C17F8EF3}

Med beräknade mätvärden kan du skapa anpassade mätvärden som härleds från segment eller matematiska beräkningar. Tidigare när du kanske använde mbox `SiteCatlayst:Event` där `evar27=shoes` och händelsen är `purchase`, skulle du nu skapa ett segment där `evar27=shoes` och sedan skapa ett beräknat mått där händelsen är `purchase` med segmentet tillämpat. Dessa mätvärden kan skapas när som helst, även efter att aktiviteten pågår. De kan sedan användas på alla rapporter i Analytics.

## Attributar A4T konverteringar till flera kampanjer? {#section_7F15C727206440CD86B3A8CE77087DF9}

Ja, med inställningen &quot;Full allokering&quot;.
