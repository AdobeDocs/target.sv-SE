---
keywords: system diagram;flicker;at.js;implementation;javascript library;js;atjs
description: Systemdiagram i Adobe Target som visar flödet av anrop och information som skickas eller samlas in för en automatiskt skapad global mbox med at.js.
title: Hur JavaScript-biblioteket Adobe Target at.js fungerar
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: a6bcaac474927ddd0a14d4cb274c0460e6002a9b
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 2%

---


# Hur at.js fungerar{#how-at-js-works}

För att implementera [!DNL Adobe Target] klientsidan måste du använda JavaScript-biblioteket at.js.

I en implementering av [!DNL Adobe Target][!DNL Target] på klientsidan levererar upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med en implementering på klientsidan kan du använda en WYSIWYG-redigerare, [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) eller ett icke-visuellt gränssnitt, den [formulärbaserade Experience Composer](/help/c-experiences/form-experience-composer.md), för att skapa test- och personaliseringsupplevelser.

## Vad är at.js?

Biblioteket [](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) at.js är det nya implementeringsbiblioteket för Target. at.js-biblioteket ger bättre sidladdningstider för webbimplementeringar och ger bättre implementeringsalternativ för enkelsidiga program. at.js är det rekommenderade implementeringsbiblioteket och uppdateras ofta med nya funktioner. Vi rekommenderar att alla kunder implementerar eller migrerar till den [senaste versionen av at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

Mer information finns i [Target JavaScript-bibliotek](/help/c-intro/how-target-works.md#libraries).

I den implementering som [!DNL Target] visas nedan har följande [!DNL Adobe Experience Cloud] lösningar implementerats: Analytics, Target och Audience Manager. Dessutom implementeras följande bastjänster från Experience Cloud: Adobe Launch, Audiences och Visitor ID Service.

## Vad är skillnaden mellan at.js 1?*x* och at.js 2.x arbetsflödesdiagram?

Se [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) för mer information om skillnaderna som introducerades i 2.O från 1.*x*.

Från en högnivåvy finns det några skillnader mellan de två versionerna:

* at.js 2.x har inte något globalt koncept för mbox-begäran utan snarare en sidinläsningsbegäran. En sidladdningsbegäran kan visas som en begäran om hämtning av innehåll som ska användas vid den första sidladdningen på webbplatsen.
* at.js 2.x hanterar koncepten Vyer, som används för SPA (Single Page Applications). at.js 1.*x* känner inte till detta koncept.

## at.js 2.x-diagram

Följande diagram hjälper dig att förstå arbetsflödet i at.js 2.x med Vyer och hur detta förbättrar SPA-integreringen. För att få en bättre introduktion till de koncept som används i at.js 2.x, se Implementering av [Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Target flow with at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Steg | Detaljer |
| --- | --- |
| 1 | Samtalet returnerar [!DNL Experience Cloud ID] om användaren är autentiserad. ett annat samtal synkroniserar kund-ID:t. |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>at.js kan också läsas in asynkront med ett valfritt predhide-fragment implementerat på sidan. |
| 3 | En sidinläsningsbegäran görs med alla konfigurerade parametrar (MCID, SDID och kund-ID). |
| 4 | Profilskript körs och matas sedan in i profilarkivet. Store begär kvalificerade målgrupper från Audience Library (till exempel målgrupper som delas från Adobe Analytics, Audience Management, etc.).<br>Kundattribut skickas till profilarkivet i en gruppbearbetning. |
| 5 | Baserat på parametrar för URL-begäran och profildata bestämmer du vilka aktiviteter och upplevelser som ska returneras till besökaren för den aktuella sidan och framtida vyer. [!DNL Target] |
| 6 | Målinriktat innehåll skickas tillbaka till sidan, eventuellt med profilvärden för ytterligare personalisering.<br>Målinriktat innehåll på den aktuella sidan visas så snabbt som möjligt utan att du behöver flimra standardinnehållet.<br>Målanpassat innehåll för vyer som visas som ett resultat av användaråtgärder i en SPA cachelagras i webbläsaren så att det kan tillämpas direkt utan ett extra serveranrop när vyerna aktiveras via `triggerView()`. |
| 7 | Analytics data skickas till datainsamlingsservrar. |
| 8 | Målinriktade data matchas mot Analytics-data via SDID och bearbetas till Analytics rapportlagring.<br>Analytics-data kan sedan visas i både Analytics och Target via Analytics for Target-rapporter (A4T). |

Nu hämtas vyer och åtgärder från cachen och visas för användaren utan ett serveranrop, oavsett var i SPA-filen `triggerView()` implementeras. `triggerView()` skickar också en meddelandebegäran till [!DNL Target] backend-objektet för att öka antalet och registrera antalet visningar. Mer information om at.js för SPA med vyer finns i Implementering [av](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)Single Page-program.

![Target flow at.js 2.x triggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Steg | Detaljer |
| --- | --- |
| 1 | `triggerView()` anropas i SPA för att återge vyn och tillämpa åtgärder för att ändra visuella element. |
| 2 | Målinnehåll för vyn läses från cachen. |
| 3 | Målinriktat innehåll visas så snabbt som möjligt utan att man behöver flimra standardinnehållet. |
| 4 | En meddelandebegäran skickas till [!DNL Target] Profile Store för att räkna besökaren i aktiviteten och ökningsvärdena. |
| 5 | Analytics-data skickas till datainsamlingsservrar. |
| 6 | Target data matchas mot Analytics-data via SDID och bearbetas till Analytics rapporteringslager. Analytics data kan sedan visas i både Analytics och Target via A4T-rapporter. |

### at.js 2.x Architecture Chart ![Overview badge](/help/assets/overview.png)

at.js 2.x förbättrar Adobe Target stöd för SPA och kan integreras med andra Experience Cloud-lösningar. Den här videon förklarar hur allt hänger ihop.

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Mer information finns i [Förstå hur at.js 2.x fungerar](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) .

## at.js 1.x-diagram

![Target flow - at.js 1.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/target-flow.png)

| Steg | Beskrivning | Utlysning | Beskrivning |
|--- |--- |--- |--- |
| 1 | Samtalet returnerar [!DNL Experience Cloud ID] (MCID) om användaren är autentiserad. ett annat samtal synkroniserar kund-ID:t. | 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext. |
| 3 | En global mbox-begäran görs med alla konfigurerade parametrar, MCID, SDID och kund-ID (valfritt). | 4 | Profilskript körs och matas sedan in i profilarkivet. Store begär kvalificerade målgrupper från [!UICONTROL Audience Library] (till exempel målgrupper som delas från [!DNL Adobe Analytics], [!DNL Audience Manager]osv.).<br>Kundattribut skickas till [!DNL Profile Store] i en gruppbearbetning. |
| 5 | Baserat på URL-adressen, mbox-parametrar och profildata bestämmer du vilka aktiviteter och upplevelser som ska returneras till besökaren [!DNL Target] . | 6 | Målinriktat innehåll skickas tillbaka till sidan, och eventuellt även profilvärden för ytterligare personalisering.<br>Upplevelsen visas så snabbt som möjligt utan att man behöver flimra standardinnehållet. |
| 7 | [!DNL Analytics] data skickas till datainsamlingsservrar. | 8 | [!DNL Target] data matchas mot [!DNL Analytics] data via SDID och bearbetas till [!DNL Analytics] rapportlagringen.<br>[!DNL Analytics] data kan sedan visas både [!DNL Analytics] och [!DNL Target] via [!DNL Analytics for Target] (A4T)-rapporter. |

### Kontorstid: at.js tips and overview (26 juni 2019) ![Tutorial badge](/help/assets/tutorial.png)

Den här videon är en inspelning av&quot;Office Hours&quot;, ett projekt som leds av Adobes kundtjänstteam.

* Fördelar med att använda at.js
* at.js-inställningar
* Hantering av flimmer
* Felsöka på.js
* Kända fel
* Vanliga frågor

>[!VIDEO](https://video.tv.adobe.com/v/27959)

## How at.js renders offers with HTML content {#render}

Vid återgivning av erbjudanden med HTML-innehåll använder at.js följande algoritm:

1. Bilder är förinlästa (om det finns några `<img>` taggar i HTML-innehåll).

1. HTML-innehåll är kopplat till DOM-noden.

1. Textbundna skript körs (koden omges av `<script>` taggar).

1. Fjärrskript läses in asynkront och körs (`<script>` taggar med `src` attribut).

Viktigt:

* at.js ger inga garantier i ordningen för fjärrexekvering av skript eftersom dessa läses in asynkront.
* Textbundna skript får inte ha några beroenden till fjärrskript eftersom de läses in och körs senare.