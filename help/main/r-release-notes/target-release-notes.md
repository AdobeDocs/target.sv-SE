---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 43dd8ac84e0dbd75bb17a425fe2fdd29a50f3b9e
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 19 oktober 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 22.10.3 (version 25-27 oktober 2022)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **25 oktober**: Europa, Mellanöstern och Afrika (EMEA)
* **26 oktober**: Asien-Stillahavsområdet (APAC)
* **27 oktober**: Amerika

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
| --- | --- |
| Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]<br>(Tillgängligt för utvalda kunder för testning. Kommer att vara tillgänglig för alla kunder i en framtida version.) | Tänk på följande ändringar:<ul><li>Stöd för binära värden och maximeringsvärden i [!UICONTROL Analytics for Target] A4T-rapportering för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet</li><li>Bevarat beteende för befintliga aktiviteter fram till februari 2023. Efter detta datum kommer aktiviteterna att avbrytas för att tvinga befintlig aktivitetsmigrering till nytt beteende</li><li>Från 20 februari 2023, stöd för `averagetimespentonsite`, `bouncerate`och `entries` mätvärden i [!DNL Target] aktiviteter kommer att bli inaktuella.</li></ul> |
| [!DNL Recommendations] egna namn | Egna namn har lagts till i [!UICONTROL Analytics for Target] A4T-rapportering. Tidigare [!DNL Target] visas endast med upplevelse-ID:n. Den här förbättringen justerar rapporteringen mellan [!DNL Adobe Analytics] och [!DNL Target] och hjälper kunderna att effektivisera arbetet med att skapa rapporter i A4T. (TGT-41853) |

* Fler verktygstips i [!DNL Target] Användargränssnitt som hjälper kunderna att navigera effektivare i målgruppsbyggaren och för att lära sig hur de använder funktioner som kanske inte är kända. (TGT-44139)
* Funktioner som förhindrar kunderna från att redigera en aktivitet som inaktiverats av [!DNL Target] eftersom det använder mätvärden som inte stöds. Ett meddelande i användargränssnittet uppmanar kunderna att duplicera aktiviteten och sedan uppdatera konverteringsmåttet.

   Med den här versionen `averagetimespentonsite`, `bouncerate`och `entries` mätvärden i [!DNL Target] aktiviteter kommer att bli inaktuella för nya aktiviteter. Befintliga aktiviteter kan fortsätta att använda dessa mått fram till februari 2023. (TGT-43860, TGT-43861 och TGT-43650)

* Ett verktygstips har lagts till i [!DNL Target] Användargränssnitt som hjälper kunderna att välja ett optimeringsvillkor när de skapar eller redigerar ett [!UICONTROL Auto-Target] aktivitet som använder A4T. (TGT-43713)

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |


## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
