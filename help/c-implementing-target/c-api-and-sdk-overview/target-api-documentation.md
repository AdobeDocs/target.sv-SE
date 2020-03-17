---
keywords: api;adobe i/o
description: Information som hjälper dig att använda övergång från äldre Target-API:er till nya API:er i Adobe I/O.
title: Övergång från äldre Target-API:er till Adobe I/O
topic: Standard
uuid: f8a0ab54-5840-4430-b9be-19e689b1c09a
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Övergång från äldre Target-API:er till Adobe I/O{#transition-from-target-legacy-apis-to-adobe-i-o}

Information som hjälper dig att använda övergång från äldre Target-API:er till nya API:er i Adobe I/O.

När Adobe Target Classic har tagits bort har även de API:er som är anslutna till ditt Target Classic-konto gjorts otillgängliga. Det här dokumentet hjälper dig att övergå dina gamla API-baserade integreringar till Target-API:erna som drivs av Adobe I/O.

Mer information om Target API-dokumentationen finns i [Target API:er och NodeJS SDK](../../c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md#concept_5718EC1FF2ED4436935D0BCCD7AA29A6).

## Terminologi {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| Villkor | Beskrivning |
|--- |--- |
| Äldre API | API:er som är länkade till ditt Target Classic-konto. Dessa API-anrop baseras på användarnamn och lösenordsbaserad autentisering och använder värdnamnet `testandtarget.omniture.com`. Om dina API-anrop innehåller ett användarnamn och lösenord i URL:en för begäran måste du gå över till API:er för Adobe I/O. |
| Adobe I/O | Adobe I/O är den nya gatewayen för mål-API:er. Dessa API:er är anslutna till ditt Target Standard-/Premium-konto. Target-API:erna på Adobe I/O använder en JWT-baserad autentisering, som är branschstandarden för säkra företags-API:er. |

## Tidslinje {#section_A478EBF637554A2DB5A31661955121ED}

De äldre API:erna kommer att tas bort när du stänger Target Classic:

| Datum | Detaljer |
|--- |--- |
| 17 oktober 2017 | Alla API-metoder som utför en write-åtgärd (`saveCampaign`, `copyCampaign`, `saveHTMLOfferContent`och `setCampaignState`) har tagits bort.<br>Detta är samma datum som när alla användarkonton för Target Classic var skrivskyddade. |
| 14 november 2017 | De återstående API:erna har tagits bort. Det här är det datum då användargränssnittet för Target Classic togs bort |

Rekommendationer i klassiska API:er påverkas inte av den här tidslinjen.

## Likvärdiga metoder {#section_DDB42CCC172545B09CB728D794CC466B}

I följande tabell visas de likvärdiga nya Target API-metoderna för de äldre API-metoderna. De nya API:erna returnerar JSON jämfört med det XML-svar som tillhandahålls av de äldre API:erna.

De nya API-metoderna är länkade till motsvarande avsnitt på API-dokumentationswebbplatsen. Ett exempel ges för varje API-metod. Du kan också använda Admin Postman Collection som innehåller exempel-API-anrop för alla nya Adobe API-metoder i Adobe I/O.

| Gruppering | Äldre API-metod | Ny API-metod | Anteckningar |
|--- |--- |--- |--- |
| Kampanj/aktivitet | Skapa kampanj | [Skapa AB-](http://developers.adobetarget.com/api/#create-ab-activity)<br>[aktivitetSkapa XT-aktivitet](http://developers.adobetarget.com/api/#create-xt-activity) | De nya API:erna har separata skapandemetoder för AB och XT |
|  | Kampanjuppdatering | [Uppdatera AB](http://developers.adobetarget.com/api/#update-ab-activity)<br>[ActivityUpdate XT-aktivitet](http://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | Kopiera kampanj | Ej tillämpligt | Använda API:er för att skapa aktivitet |
|  | Kampanjlista | [Listaktiviteter](http://developers.adobetarget.com/api/#list-activities) |  |
|  | Kampanjtillstånd | [Uppdatera aktivitetsstatus](http://developers.adobetarget.com/api/#update-activity-state) |  |
|  | Kampanjvy | [Hämta AB Activity av](http://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[IDGet XT Activity by ID](http://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | Kampanj-ID från tredje part | Ej tillämpligt | Om du använder ett tredjeparts-ID kan de relevanta aktivitetsmetoderna användas |
| Erbjudanden | Skapa erbjudande | [Skapa erbjudande](http://developers.adobetarget.com/api/#create-offer) |  |
|  | Erbjudande | [Erbjud via ID](http://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | Erbjudandelista | [Listerbjudanden](http://developers.adobetarget.com/api/#list-offers) |  |
|  | Mapplista | Ej tillämpligt | Mappar stöds inte i Target Standard/Premium |
| Rapportering | Kampanjresultatrapport | [Hämta Prestandarapport för AB](http://developers.adobetarget.com/api/#get-ab-performance-report)<br>[Få XT-prestandarapport](http://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | Granskningsrapport | [Hämta revideringsrapport](http://developers.adobetarget.com/api/#get-audit-report) |  |
|  | 1-1 Innehållsrapport | [Hämta rapport för AP-prestanda](http://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| Kontoinställningar | Hämta värdgrupper | [Listmiljöer](http://developers.adobetarget.com/api/#list-environments) |  |

## Undantag {#section_09CF9A0E289149279783B4801D1B6D4C}

Kontakta din Customer Success Manager om du behöver ett undantag.

## Hjälp {#section_591F850E2B7A4342B1C233693425415C}

Kontakta Adobe Target Client Care (tt-support@adobe.com) om du har några frågor eller behöver hjälp med att gå över till de nya Target-API:erna i Adobe I/O.
