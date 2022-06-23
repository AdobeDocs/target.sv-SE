---
keywords: systemdiagram;flimmer;at.js;implementation;javascript library;js;atjs
description: Se hur [!DNL Target] at.js JavaScript-biblioteksfunktioner, inklusive systemdiagram, som hjälper dig förstå arbetsflödet när sidorna läses in.
title: Hur fungerar biblioteket at.js Javascript?
feature: at.js
role: Developer
exl-id: 2193c02a-2a85-4ae1-bfbd-40fa7b87f0a0
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 2%

---

# Hur at.js fungerar

Att implementera [!DNL Adobe Target] på klientsidan måste du använda JavaScript-biblioteket at.js.

I en implementering på klientsidan av [!DNL Adobe Target], [!DNL Target] levererar upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med en implementering på klientsidan kan du använda en WYSIWYG-redigerare, [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC), eller ett icke-visuellt gränssnitt, [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md), för att skapa test- och personaliseringsupplevelser.

## Vad är at.js?

at.js-biblioteket är det nya implementeringsbiblioteket för Target. at.js-biblioteket ger bättre sidladdningstider för webbimplementeringar och ger bättre implementeringsalternativ för enkelsidiga program. at.js är det rekommenderade implementeringsbiblioteket och uppdateras ofta med nya funktioner. Vi rekommenderar att alla kunder implementerar eller migrerar till [senaste versionen av at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/).

Mer information finns i [Mål-JavaScript-bibliotek](/help/main/c-intro/how-target-works.md#libraries).

I [!DNL Target] implementering som visas nedan, följande [!DNL Adobe Experience Cloud] lösningar implementeras: Analytics, Target och Audience Manager. Dessutom implementeras följande bastjänster från Experience Cloud: [!DNL Adobe Experience Platform], [!DNL Audiences]och [!DNL Visitor ID Service].

## Vad är skillnaden mellan at.js 1?*x* och arbetsflödesdiagram i at.js 2.x?

Se [Uppgradera från at.js 1.x till at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) för mer information om skillnaderna som introducerades i 2.O från 1.*x*.

Från en högnivåvy finns det några skillnader mellan de två versionerna:

* at.js 2.x har inte något globalt koncept för mbox-begäran utan snarare en sidinläsningsbegäran. En sidladdningsbegäran kan visas som en begäran om hämtning av innehåll som ska användas vid den första sidladdningen på webbplatsen.
* at.js 2.x hanterar koncepten Vyer, som används för Single Page-program (SPA). at.js 1.*x* är inte medveten om detta koncept.

## at.js 2.x-diagram

Följande diagram hjälper dig att förstå arbetsflödet för at.js 2.x med Vyer och hur detta förbättrar SPA integrering. Om du vill få en bättre introduktion till de koncept som används i at.js 2.x kan du läsa [Implementering av Single Page-program](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/).

![Målflöde med at.js 2.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Steg | Detaljer |
| --- | --- |
| 1 | Samtalet returnerar [!DNL Experience Cloud ID] om användaren är autentiserad, ett annat samtal synkroniserar kund-ID:t. |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>at.js kan också läsas in asynkront med ett valfritt predhide-fragment implementerat på sidan. |
| 3 | En sidinläsningsbegäran görs med alla konfigurerade parametrar (MCID, SDID och kund-ID). |
| 4 | Profilskript körs och matas sedan in i profilarkivet. Store begär kvalificerade målgrupper från Audience Library (till exempel målgrupper som delas från Adobe Analytics, Audience Management, osv.).<br>Kundattribut skickas till profilarkivet i en gruppbearbetning. |
| 5 | Baserat på parametrar för URL-begäran och profildata, [!DNL Target] bestämmer vilka aktiviteter och upplevelser som ska återsändas till besökaren för den aktuella sidan och framtida vyer. |
| 6 | Målinriktat innehåll skickas tillbaka till sidan, eventuellt med profilvärden för ytterligare personalisering.<br>Målinriktat innehåll på den aktuella sidan visas så snabbt som möjligt utan att du behöver flimra standardinnehållet.<br>Målanpassat innehåll för vyer som visas som ett resultat av användaråtgärder i en SPA cachelagras i webbläsaren så att det kan tillämpas direkt utan ett extra serveranrop när vyerna aktiveras via `triggerView()`. |
| 7 | Analysdata skickas till datainsamlingsservrar. |
| 8 | Målinriktade data matchas mot analysdata via SDID och bearbetas till lagringsplatsen för analysrapporter.<br>Analysdata kan sedan visas i både Analytics- och Target-rapporter via Analytics for Target-rapporter (A4T). |

Nu, var `triggerView()` är implementerat på SPA, hämtas vyer och åtgärder från cachen och visas för användaren utan ett serveranrop. `triggerView()` skickar även en meddelandebegäran till [!DNL Target] för att öka och registrera antalet intryckta. Mer information om at.js för SPA med vyer finns i [Implementering av Single Page-program](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/).

![Målflöde at.js 2.x triggerView](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Steg | Detaljer |
| --- | --- |
| 1 | `triggerView()` anropas i SPA för att återge vyn och använda åtgärder för att ändra visuella element. |
| 2 | Målinnehåll för vyn läses från cachen. |
| 3 | Målinriktat innehåll visas så snabbt som möjligt utan att man behöver flimra standardinnehållet. |
| 4 | Begäran om meddelande skickas till [!DNL Target] Profilarkiv för att räkna besökaren i aktiviteten och öka mätvärden. |
| 5 | Analysdata skickas till datainsamlingsservrar. |
| 6 | Måldata matchas mot Analytics-data via SDID och bearbetas till lagringsplatsen för analysrapporter. Analysdata kan sedan visas både i Analytics och Target via A4T-rapporter. |

### Video - at.js 2.x - arkitekturdiagram

at.js 2.x förbättrar Adobe Target stöd för SPA och kan integreras med andra Experience Cloud-lösningar. Den här videon förklarar hur allt hänger ihop.

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Se [Så här fungerar at.js 2.x](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) för mer information.

## at.js 1.x-diagram

![Målflöde - at.js 1.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/target-flow.png)

| Steg | Beskrivning | Utlysning | Beskrivning |
|--- |--- |--- |--- |
| 1 | Samtalet returnerar [!DNL Experience Cloud ID] (MCID) om användaren är autentiserad, ett annat samtal synkroniserar kund-ID:t. | 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext. |
| 3 | En global mbox-begäran görs med alla konfigurerade parametrar, MCID, SDID och kund-ID (valfritt). | 4 | Profilskript körs och matas sedan in i profilarkivet. Store begär kvalificerade målgrupper från [!UICONTROL Audience Library] (till exempel målgrupper som delas från [!DNL Adobe Analytics], [!DNL Audience Manager], osv.).<br>Kundattribut skickas till [!DNL Profile Store] i en gruppbearbetning. |
| 5 | Baserat på URL, mbox-parametrar och profildata, [!DNL Target] bestämmer vilka aktiviteter och upplevelser som ska returneras till besökaren. | 6 | Målinriktat innehåll skickas tillbaka till sidan, och eventuellt även profilvärden för ytterligare personalisering.<br>Upplevelsen visas så snabbt som möjligt utan att man behöver flimra standardinnehållet. |
| 7 | [!DNL Analytics] data skickas till datainsamlingsservrar. | 8 | [!DNL Target] data matchas mot [!DNL Analytics] data via SDID och bearbetas till [!DNL Analytics]  rapporterar lagring.<br>[!DNL Analytics] data kan sedan visas i båda [!DNL Analytics] och  [!DNL Target] via [!DNL Analytics for Target] (A4T)-rapporter. |

### Video - kontorstid: at.js tips och översikt (26 juni 2019)

Den här videon är en inspelning av&quot;Office Hours&quot;, ett projekt som leds av kundtjänstteamet på Adobe.

* Fördelar med att använda at.js
* at.js-inställningar
* Hantering av flimmer
* Felsöka på.js
* Kända fel
* Vanliga frågor

>[!VIDEO](https://video.tv.adobe.com/v/27959)

## How at.js renders offers with HTML content {#render}

Vid återgivning av erbjudanden med HTML-innehåll använder at.js följande algoritm:

1. Bilderna är förinlästa (om det finns några) `<img>` -taggar i HTML).

1. HTML-innehåll är kopplat till DOM-noden.

1. Textbundna skript körs (koden omges av `<script>` taggar).

1. Fjärrskript läses in asynkront och körs (`<script>` taggar med `src` attribut).

Viktigt:

* at.js ger inga garantier i ordningen för fjärrexekvering av skript eftersom dessa läses in asynkront.
* Textbundna skript får inte ha några beroenden till fjärrskript eftersom de läses in och körs senare.
