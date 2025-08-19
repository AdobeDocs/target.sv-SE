---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;mått;måttdefinitioner
description: Hitta svar på frågor om måttdefinitioner och användning av Analytics för  [!DNL Target] (A4T). Med A4T kan du använda Analytics-rapportering med Adobe [!DNL Target] aktiviteter.
title: Var hittar jag information om metriska definitioner med A4T?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Måttdefinitioner - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om måttdefinitioner och som använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

## Vad gäller för aktivitetsmedlemskap? Hur lång tid efter att besökarna har gått in i aktiviteten räknas deras aktiviteter in om de inte ser den igen? {#section_41B4958F33534E4B96DEE0C981227A79}

+++Svar
Standardförfallotiden för aktiviteten är 90 dagar efter en besökares senaste interaktion med aktiviteten. Den här inställningen kan justeras av ClientCare vid behov. Den här inställningen är global för alla aktiviteter, så den bör inte justeras för ett fall.

+++

## Varför har jag inte åtkomst till alternativen för Avancerade inställningar när jag konfigurerar mina målvärden? {#adv-settings}

+++Svar
Alternativen [!UICONTROL Advanced Settings] är inte tillgängliga för aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T).

För aktiviteter som använder A4T använder målmåttet alltid inställningarna [!UICONTROL Increment Count & Keep User in Activity] och [!UICONTROL On Every Impression]. Dessa inställningar är *inte* konfigurerbara.

För andra aktiviteter än A4T kan du använda [Avancerade inställningar](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) för att hantera hur du mäter framgång. Du kan lägga till beroenden, välja om du vill behålla användaren i aktiviteten eller ta bort dem och om mätvärdet ska räknas en gång per deltagare eller vid varje intryck. Du kommer åt alternativen för [!UICONTROL Advanced Settings] i en annan aktivitet än A4T genom att klicka på de lodräta ellipserna > [!UICONTROL Advanced Settings], vilket visas nedan:

![Avancerade inställningar](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## Vad är beräknade mätvärden och hur ersätter de den SiteCatalyst:Event-mbox som jag använde tidigare? {#section_D59F4719E6B94758A2187427C17F8EF3}

+++Svar
Med beräknade mätvärden kan du skapa anpassade mätvärden som är härledda från segment eller matematiska beräkningar. Tidigare, när du kanske använde mbox `SiteCatlayst:Event` där `evar27=shoes` och händelsen är `purchase`, skulle du nu skapa ett segment där `evar27=shoes` och sedan skapa ett beräknat mått där händelsen är `purchase` med segmentet tillämpat. Dessa mätvärden kan skapas när som helst, även efter att aktiviteten pågår. De kan sedan användas på alla rapporter i Analytics.

+++

## Attributar A4T konverteringar till flera kampanjer? {#section_7F15C727206440CD86B3A8CE77087DF9}

+++Svar
Ja, med inställningen &quot;Full allokering&quot;.

+++
