---
keywords: dynamic data;assets;data;offers;personalized offers;personal offers;token replace
description: Du kan visa profilvärden och aktivitetsinformation direkt i ett HTML- eller JSON-erbjudande i Adobe Target.
title: Överför dynamiska data till erbjudanden
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 59605f220884c74ec43b8b2a47f36ba32120ae2a
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 0%

---


# Överför dynamiska data till erbjudanden

Du kan dynamiskt visa besökarinformation som lagras i profilen [!DNL Adobe Target]. På samma sätt kan aktivitetsinformation (som namnet på aktiviteten eller namnet på upplevelsen) också användas för att skapa ett enda erbjudande som dynamiskt returnerar personaliserat innehåll baserat på besökarens intressen, tidigare beteende och övergripande profil.

## Affärsärenden

* Erbjud ett rabatterat erbjudande om att&quot;fylla på&quot; eller&quot;fylla på&quot; den senast köpta produkten. I stället för att skapa ett separat erbjudande för varje objekt i din katalog kan du skapa ett erbjudande med dynamisk text som läser den&quot;senaste köpta produkten&quot; från profilen och visar en länk i erbjudandet.
* En besökare kommer till din landningssida med `keyword=world` `cup`. Du visar termen *World Cup* i erbjudandet.
* Anpassa en rekommendationsetikett med t.ex. (1) det sista objektet som läggs till i en besökares kundvagn (Nike Air Max 1000-tal), (2) besökarens färgpreferens (svart) och (3) besökarens favoritkategori utanför sko (hoodies). Exempel: &quot;Tillbehör din &#39;Nike Air Max 1000s&#39; med dessa coola &#39;svarta&#39; &#39;hookaler&#39;!&quot;

## Tekniska fördelar

Eftersom användarspecifika inställningar, beteenden, status osv. kan lagras i användarens profil, du kan upprepa det här meddelandet vid hans eller hennes nästa besök. Dynamiska erbjudanden ger större skala genom att ni kan skapa ett enda erbjudande inom en aktivitet som visar personaliserade meddelanden för alla era besökare. När besökarens avsikt ändras återspeglas dessa ändringar automatiskt i webbplatsens innehåll.

## Exempel

* `mboxCreate("landingpage"`,  `"profile.keyword=World Cup");`

* HTML-erbjudandekod: `Get your ${profile.keyword} information here!`
* Användaren ser: Hämta information om World Cup här!

Följande värden kan vara &quot;token replace&quot;:

| Värde | Exempel |
|--- |--- |
| Profilparametrar i mbox | `${profile.age}` |
| Skriptprofilparametrar | `${user.lifetimeSpend}` |
| Mbox-parametrar | `${mbox.favoriteColor}` |
| Kampanjinformation | `${campaign.name}`,  `${campaign.recipe.name}`,  `${campaign.id}`,  `${campaign.recipe.id}`och  `${campaign.recipe.trafficType}` |
| Unikt besökar-ID | `${user.pcId}` |
| Unikt sessions-ID | `${user.sessionId}` |
| Besökarens första session (true eller false) | `${user.isFirstSession}` |
| Tidigare beteende | `${user.endpoint.lastPurchasedEntity}`, `${user.endpoint.lastViewedEntity}`, `${user.endpoint.mostViewedEntity}`, `${user.endpoint.categoryAffinity}` |

Logga information i konsolen i felsökningssyfte, t.ex. `${campaign.name}`, `${campaign.id}`, `${campaign.recipe.name}`, `${campaign.recipe.id}`, `${offer.name}`, `${offer.id}`, `${campaign.name}`

För Recommendations-designer finns ytterligare exempel i [Designöversikt](/help/c-recommendations/c-design-overview/design-overview.md).

## Implementering

Använd syntaxen för profilparametrar som skickas till en mbox: `${profile.parameter}` Använd syntaxen för profilparametrar som skapats i ett profilskript:

`${user.parameter}`

När du använder dynamiska attribut i en Recommendations-design måste du infoga ett omvänt snedstreck ( \ ) före dollartecknet ( $ ) för att det dynamiska värdet ska återges korrekt: `\${user.endpoint.lastViewedEntity}`

Variablerna ersätts med värdet på serversidan, så det behövs inga citattecken eller andra JavaScript för att visningen ska bli korrekt.

Standardvärden kan också anges för värden som du vill exponera för erbjudanden. Syntaxen är följande:

`${user.testAttribute default="All Items!"}`

När `testAttribute` inte finns eller är tom, &quot;Alla objekt!&quot; kommer att skrivas ut. Om ett tomt attributvärde är giltigt och du vill skriva ut det i stället för att visa standardvärdet, kan du använda:

`${user.testAttribute default="All Items!" show_blank="true"}`

Du kan också visa värden för escape och unescape. Om värdet till exempel har en apostrof vill du undvika värdet så att det inte bryter JavaScript-koden på sidan. (Erbjudandena är skrivna i JavaScript, vilket innebär att en enda apostrof kan blandas ihop som citat.) Exempel:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`