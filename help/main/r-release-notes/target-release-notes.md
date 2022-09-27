---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 07d71ccf934a1c638c37285372c3ec3199ec2000
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 7 september 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 22.10.1 (version 4-6 oktober 2022)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **4 oktober**: Europa, Mellanöstern och Afrika (EMEA)
* **5 oktober**: Asien-Stillahavsområdet (APAC)
* **6 oktober**: Amerika

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
| --- | --- |
| Nytt [!UICONTROL Visual Experience Composer] tillägg för Google Chrome | En ny [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)-tillägget för Chrome finns i Chrome Web Store.<br>Från och med januari 2023 är den nuvarande [!DNL Target] Tillägget VEC Helper slutar fungera i Google Chrome eftersom Google inte tillåter tillägg med Manifest V2. Ladda ned det nya tillägget för att fortsätta att visuellt utveckla dina webbplatser i [!DNL Target] från och med det nya året. |
| Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]<br>(Exakt utgivningsdatum ska fastställas.) | Tänk på följande ändringar:<ul><li>Stöd för binära värden och maximeringsvärden i [!UICONTROL Analytics for Target] A4T-rapportering för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet</li><li>Varningsmeddelandet för binära mått har tagits bort för [!UICONTROL Auto-Target] verksamhet</li><li>Bevarar befintliga aktiviteter fram till 20 februari 2023. Efter detta datum kommer aktiviteterna att avbrytas för att tvinga befintlig aktivitetsmigrering till nytt beteende</li><li>Från 20 februari 2023, stöd för `averagetimespentonsite`, `bouncerate`och `entries` mätvärden i [!DNL Target] aktiviteter kommer att bli inaktuella.</li></ul> |

* Ett problem som gjorde att målgruppsinformation inte kunde visas korrekt i dialogrutan har korrigerats [!UICONTROL Audiences Refinements] informationsfönstret. (TGT-43917)
* Förbättrade prestanda för [!DNL Target] Gränssnitt vid inläsning av målgrupper som närmar sig [rekommenderad gräns för målinriktningsregler](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Ett problem som gjorde att vissa komponenter inte visades korrekt i [!UICONTROL Modifications] på [!UICONTROL Experiences] sida när du skapar eller redigerar aktiviteter i VEC efter byte från [!UICONTROL Compose] till [!UICONTROL Browse] läge. (TGT-43300)
* Ett problem som gjorde att vissa kunder inte kunde arkivera har åtgärdats [!UICONTROL A/B Test] aktiviteter som använder [!UICONTROL Auto-Target]. (TGT-40978)
* Lagt till möjlighet att automatiskt använda ett enda erbjudande på flera platser inom en enda rapporteringsgrupp. (TGT-43974)
* Lagt till möjlighet att filtrera upplevelsefragment efter typ (HTML eller JSON) i [!UICONTROL Offers] lista. (TGT-43121)
* Ett problem som gjorde att kunder kunde infoga JSON har korrigerats [!UICONTROL Experience Fragment] erbjudanden när VEC används. JSON-erbjudanden kan bara infogas med [!UICONTROL Form-Based Experience] disposition. (TGT-43846)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
