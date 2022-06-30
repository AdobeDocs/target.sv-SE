---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fa6324606b32f265084615fd1c13ce6c49921b48
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 30 juni 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

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
