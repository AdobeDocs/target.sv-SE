---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d0b6f81507cc5d5bc17d029c3d8f5b36c2c71a29
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 18 juli 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target Standard/Premium] 22.7.1 (20 juli 2022)

Den här versionen innehåller följande funktioner, förbättringar och korrigeringar:

| Funktion | Beskrivning |
| --- | --- |
| Förbättrad exakthet i målgruppsutvärderingen och fördröjning för slutanvändarna tack vare stödet för IPv6 | Besökarnas geografiska platser bestäms nu av IPv6-adresser, om sådana finns, i motsats till enbart IPv4-adresser. Leverans-API:er har också stöd för IPv6-indataparametrar. Filtrering och listning av tillåtna adresser har stöd för både IPv4- och IPv6-adresser. Det här IPv6-stödet i den här versionen innebär att besökare inkluderas mer korrekt i målgrupperna (mer korrekt kvalificerar sig för aktiviteter eller inkluderas i filtreringskriterierna). Det förbättrar också datalatensen eftersom IPv6-klienter dirigeras direkt och undviker overheadkostnaderna för IPv6-till-IPv4-gatewayen. |
| Förbättrad nyttolasthantering på klientsidan | Om Adobe Target identifierar att en begäran kommer från en robot, vidarebefordras inte nyttolasten till Analytics med A4T-integreringen på serversidan, och det finns ingen mod_stats-händelse i Target-loggarna. Före den här versionen skulle integreringar på A4T-klientsidan vidarebefordra nyttolasten till Analytics, även när de hade identifierats som både robottrafik. Denna inkonsekvens mellan server- och klientsidan skulle leda till avvikelser, eftersom A4T-rapporter för den senare inkluderade robottrafiken. Vidare identifierades inte och flaggerades inte nödvändigtvis, vilket innebär att det inte var möjligt att skilja ut eller ta bort robottrafiken från resten av trafiken. Och även om en kund enbart redovisar robottrafiken skulle det inte nödvändigtvis matcha den uppsättning trafik som Target identifierade och uteslöt som både robottrafik, vilket skulle leda till delade avvikelser eller andra problem. I den här versionen har A4T-loggning på klientsidan förbättrats så att beteendet för A4T-nyttolasten är detsamma som för A4T på serversidan: Besökare som identifieras som robotar exkluderas från Target-inventering/rapportering, för implementeringar både på serversidan och på klientsidan. |

## [!DNL Target Standard/Premium] 22.6.2 (30 juni 2022)

Den här versionen innehåller följande funktioner, förbättringar och korrigeringar:

| Funktion | Beskrivning |
| --- | ---  |
| Meddelanden i produkten | Få följande relevanta produktmeddelanden:<ul><li>**Verksamhet**: Meddelanden för alla aktivitetstyper när en aktivitet har godkänts eller inaktiverats, antingen manuellt eller när start- eller slutdatumet nås. Meddelandet innehåller namnet på aktiviteten med en länk till aktivitetens översiktssida.</li><li>**Profilskript** Meddelanden när ett profilskript aktiveras eller inaktiveras, antingen manuellt eller av Target.</li><li>**Recommendations-flöden**: Meddelanden när en Recommendations-feed aktiveras eller inaktiveras, antingen manuellt eller av Target. Meddelanden skickas också när en Recommendations-feed misslyckas.</li></ul> Som standard tas meddelanden emot av produktadministratörer, utgivare och godkännare. Meddelanden kan konfigureras i inställningarna för Experience Cloud.<br>Mer information finns i [Meddelanden](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Adobe Target Developer Guide* | The *Adobe Target Developer Guide* konsoliderar alla [!DNL Target] i en och samma guide. Handboken innehåller information om implementering [!DNL Target] och [!DNL Recommendations], [!DNL Target] SDK, och [!DNL Target] API:er.<br>Mer information finns i [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}. |

* Användare med [!UICONTROL Editor] kan inte längre redigera målgrupper i aktiva aktiviteter. (TGT-43582)
* Ett varningsmeddelande visas om en kund försöker spara en publik med ett utropstecken ( ! ) som första tecken i publikens namn (till exempel !London). (TGT-43643)
* Korrigerade ett problem som gjorde att vissa kunders definitionskort visade att en avslutad aktivitet fortfarande är aktiv. (TGT-43527)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
