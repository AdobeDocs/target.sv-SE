---
keywords: api;adobe i/o
description: Lär dig hur du går över från Adobe [!DNL Target] Klassiska äldre API:er till de nya API:erna på Adobe I/O.
title: Hur övergår jag från äldre API:er till Adobe I/O?
feature: Implement Server-side
role: Developer
exl-id: 4b4274a9-b91a-4a79-9b40-8b1909a2d1d1
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 0%

---

# Övergång från [!DNL Target] äldre API:er till Adobe I/O

Information som hjälper dig att använda övergången från Target-API:er till de nya API:erna på Adobe I/O.

När Adobe Target Classic har tagits bort har även de API:er som är anslutna till ditt Target Classic-konto gjorts otillgängliga. Det här dokumentet hjälper dig att övergå dina gamla API-baserade integreringar till Target-API:erna som drivs av Adobe I/O.

Mer information om Target API-dokumentationen finns i [Mål-API:er och NodeJS SDK](https://developer.adobe.com/target/implement/server-side/){target=_blank}.

## Terminologi {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| Villkor | Beskrivning |
|--- |--- |
| Äldre API | API:er som är länkade till ditt Target Classic-konto. Dessa API-anrop baseras på användarnamn och lösenordsbaserad autentisering och använder värdnamnet `testandtarget.omniture.com`. Om dina API-anrop innehåller ett användarnamn och lösenord i URL:en för begäran måste du gå över till API:er för Adobe I/O. |
| Adobe I/O | Adobe I/O är den nya gatewayen för mål-API:er. Dessa API:er är anslutna till ditt Target Standard-/Premium-konto. Target-API:erna på Adobe I/O använder en JWT-baserad autentisering, som är branschstandarden för säkra företags-API:er. |

## Tidslinje {#section_A478EBF637554A2DB5A31661955121ED}

De äldre API:erna kommer att tas bort när du stänger Target Classic:

| Datum | Detaljer |
|--- |--- |
| 17 oktober 2017 | Alla API-metoder som utför en write-åtgärd (`saveCampaign`, `copyCampaign`, `saveHTMLOfferContent`och `setCampaignState`) avvecklades.<br>Detta är samma datum som när alla användarkonton för Target Classic var skrivskyddade. |
| 14 november 2017 | De återstående API:erna har tagits bort. Det här är det datum då användargränssnittet för Target Classic togs bort |

Recommendations Classic-API:er påverkas inte av den här tidslinjen.

## Likvärdiga metoder {#section_DDB42CCC172545B09CB728D794CC466B}

I följande tabell visas de likvärdiga nya Target API-metoderna för de äldre API-metoderna. De nya API:erna returnerar JSON jämfört med det XML-svar som tillhandahålls av de äldre API:erna.

De nya API-metoderna är länkade till motsvarande avsnitt på API-dokumentationswebbplatsen. Ett exempel ges för varje API-metod. Du kan också använda Admin Postman Collection som innehåller exempel-API-anrop för alla nya Adobe API-metoder i Adobe I/O.

| Gruppering | Äldre API-metod | Ny API-metod | Anteckningar |
|--- |--- |--- |--- |
| Kampanj/aktivitet | Skapa kampanj | [Skapa AB-aktivitet](https://developers.adobetarget.com/api/#create-ab-activity)<br>[Skapa XT-aktivitet](https://developers.adobetarget.com/api/#create-xt-activity) | De nya API:erna har separata skapandemetoder för AB och XT |
|  | Kampanjuppdatering | [Uppdatera AB-aktivitet](https://developers.adobetarget.com/api/#update-ab-activity)<br>[Uppdatera XT-aktivitet](https://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | Kopiera kampanj | Ej tillämpligt | Använda API:er för att skapa aktivitet |
|  | Kampanjlista | [Listaktiviteter](https://developers.adobetarget.com/api/#list-activities) |  |
|  | Kampanjtillstånd | [Uppdatera aktivitetsstatus](https://developers.adobetarget.com/api/#update-activity-state) |  |
|  | Kampanjvy | [Hämta AB-aktivitet efter ID](https://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[Hämta XT Activity by ID](https://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | Kampanj-ID från tredje part | Ej tillämpligt | Om du använder ett tredjeparts-ID kan de relevanta aktivitetsmetoderna användas |
| Erbjudanden | Skapa erbjudande | [Skapa erbjudande](https://developers.adobetarget.com/api/#create-offer) |  |
|  | Erbjudande | [Erbjud via ID](https://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | Erbjudandelista | [Listerbjudanden](https://developers.adobetarget.com/api/#list-offers) |  |
|  | Mapplista | Ej tillämpligt | Mappar stöds inte i Target Standard/Premium |
| Rapportering | Kampanjresultatrapport | [Hämta prestandarapport för AB](https://developers.adobetarget.com/api/#get-ab-performance-report)<br>[Hämta XT-prestandarapport](https://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | Granskningsrapport | [Hämta revideringsrapport](https://developers.adobetarget.com/api/#get-audit-report) |  |
|  | 1-1 Innehållsrapport | [Hämta rapport för AP-prestanda](https://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| Kontoinställningar | Hämta värdgrupper | [Listmiljöer](https://developers.adobetarget.com/api/#list-environments) |  |

## Undantag {#section_09CF9A0E289149279783B4801D1B6D4C}

Kontakta din Customer Success Manager om du behöver ett undantag.

## Hjälp {#section_591F850E2B7A4342B1C233693425415C}

Kontakta Adobe Target Client Care (tt-support@adobe.com) om du har några frågor eller behöver hjälp med att gå över till de nya Target-API:erna på Adobe I/O.
