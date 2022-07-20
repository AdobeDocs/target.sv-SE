---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d54f3c4c75031788316a94acf3d14a8db2a17366
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 20 juli 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] plattformsrelease (20 juli 2022)

Den här versionen innehåller följande funktioner, förbättringar och korrigeringar:

| Funktion | Beskrivning |
| --- | --- |
| Förbättrad noggrannhet vid utvärdering av målgrupper och reducerad fördröjning för slutanvändare via IPv6-stöd (TNT-43364, TNT-44692) | Besökarnas geografiska platser bestäms nu av IPv6-adresser, om sådana finns, i motsats till enbart IPv4-adresser. Leverans-API:er har också stöd för IPv6-indataparametrar. Filtrering och listning av tillåtna adresser har stöd för både IPv4- och IPv6-adresser. IPv6-stödet i den här versionen innebär att besökare inkluderas mer korrekt i målgrupperna (mer korrekt kvalificerar sig för aktiviteter eller inkluderas i filtreringskriterierna). Det förbättrar också datalatensen eftersom IPv6-klienter dirigeras direkt och undviker overheadkostnaderna för IPv6-till-IPv4-gatewayen. |
| Korrigerat problem med hantering av nyttolast på klientsidan (TNT-44926) | Om Adobe Target identifierar att en begäran kommer från en robot, vidarebefordras nyttolasten inte till Analytics med A4T-integrering på serversidan, och det finns ingen mod_stats-händelse som spelats in i [!DNL Target] loggar. &lt;!— Före den här versionen skulle integreringar på A4T-klientsidan vidarebefordra nyttolasten till [!DNL Analytics], även om det hade identifierats som robottrafik. Denna inkonsekvens mellan server- och klientsidan skulle leda till avvikelser, eftersom A4T-rapporter för den senare inkluderade robottrafiken. Vidare identifierades inte och flaggerades inte nödvändigtvis, vilket innebär att det inte var möjligt att skilja ut eller ta bort robottrafiken från resten av trafiken. Och även om en kund enbart redovisar robottrafiken skulle det inte nödvändigtvis matcha den uppsättning trafik som [!DNL Target] identifieras och utesluts som både och, vilket leder till delade avvikelser eller andra problem. —> I den här versionen har A4T-loggning på klientsidan förbättrats så att beteendet för A4T-nyttolasten är detsamma som för A4T på serversidan: Besökare som identifieras som robotar exkluderas från [!DNL Target] inventering/rapportering. (Observera att det aktuella problemet var begränsat till implementeringar som använde hantering av nyttolast på klientsidan. serversidan påverkades inte. I den här versionen är funktionen nu konsekvent för hantering av nyttolast på både serversidan och klientsidan.) |


## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
