---
keywords: character limit;mbox parameters;batch delivery api;profile parameters;limits;built in profiles;maximum;limit;constraint;character;best practice;orderid;orderTotal;mbox3rdPartyID;category;categoryID
description: Information om teckenbegränsningar och andra begränsningar (erbjudandestorlek, målgrupper, profiler, värden, parametrar etc.) som påverkar aktiviteter och andra element i Adobe Target.
title: Gränser
feature: reference general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 0%

---


# Gränser{#limits}

Information om teckenbegränsningar och andra begränsningar (erbjudandestorlek, målgrupper, profiler, värden, parametrar etc.) som påverkar aktiviteter och andra element i Adobe Target.

>[!NOTE]
>
>De gränsvärden som anges nedan skall betraktas som &quot;hårda&quot;, såvida inte annat anges som &quot;rekommenderat&quot;.
>
>När de gränser som anges som&quot;rekommenderas&quot; närmar sig eller överskrids kan prestandan bli långsam. Långsamma inläsningstider för gränssnittet kan också orsakas av en mycket komplex aktivitet, som många målgrupper, mål och upplevelser, allt i en och samma aktivitet.
>
>Mycket komplexa verksamheter bör granskas med Adobe Consulting och testas i en begränsad miljö innan de släpps till produktion.

## Verksamhet

**Rekommenderad gräns**: 10 000 aktiva aktiviteter.

**Rekommenderad gräns**: 10 000 aktiva sparade (och inte avslutade) aktiviteter.

## Aktivitetsnamn

**Gräns**: 250 tecken.

## Målgruppsnamn

**Gräns**: 255 tecken.

## Målgrupper

**Gräns**: 50 målgrupper per mbox, metric eller upplevelse.

## Målgrupper, återanvändbara per konto

**Rekommenderad gräns**: 20 000 målgrupper.

## categoryId-parameter

**Gräns**: 128 tecken.

## Namn på kundattribut

**Gräns**: 250 tecken genom feed eller API.

## ID för kundattributalias

**Max** 50 tecken.

## Kundattribut, överföra

* **Maximal filstorlek för varje överföring med HTTP-metoden**: 100 MB.
* **maximal filstorlek för varje överföring med FTP-metoden**: 4 GB.
* **Antal attribut som tillåts prenumerera**: 5 for [!DNL Target Standard] och 200 for [!DNL Target Premium].

## Enheter

Det högsta antalet enheter som kan refereras i en design, antingen hårdkodade eller via slingor, är 99.

## Anpassade attribut för entitet

Du kan inkludera upp till 100 anpassade entitetsattribut

**Gräns**: Den maximala teckenlängden beror på språket.

* 15 000 tecken (språk med ett värde, en och två byte)
* 500 värden, 100 tecken per värde (flervärde)

Den maximala längden för anpassade attribut för en entitet med ett värde är 15 000 tecken (för UTF-8-kodade språk med en byte och två byte, som engelska och andra latinska skriftspråk) eller 10 000 tecken (för UTF-8-kodade språk med tre byte som kinesiska, japanska och koreanska).

Anpassade attribut för entiteter med flera värden får inte innehålla fler än 500 värden. Varje enskilt värde är begränsat till 100 tecken. Det totala antalet tecken i alla värden måste uppfylla begränsningarna för den maximala längden för anpassade entitetsattribut med ett värde (se ovan).

## entityID-parametrar

**Gräns**: 1 000 tecken.

## excludeIds {#excludedid}

**Gräns**: 5 kB för förfrågningar om POST. 2 083 tecken minus längden på URL:en för GET-begäranden.

För GET-förfrågningar gäller att även om gränsen för backend är 5 kB, eftersom Microsoft Internet Explorer begränsar URL:en till 2 083 tecken, är den realistiska gränsen 2 083 tecken minus URL:ens aktuella längd.

## Experience names

**Gräns**: 50 tecken.

## Erfarenheter per aktivitet

**Gräns**: 2 000 upplevelser per aktiviteten Experience Targeting (XT), A/B Test, Multivariate Test (MVT) och Auto-Target.

30 000 upplevelser per Automated Personalization-aktivitet (AP).

## Attributvärde för profil i rutan

**Gräns**: 256 tecken.

Värden som är längre än detta trunkeras.

## Profilnamn i mbox

**Gräns**: 128 tecken.

## mbox names

**Gräns**: 250 tecken.

## mbox-parametrar

**Gräns**: Följande begränsningar gäller för mbox-parametrar:

För vanliga mbox-anrop:
* mbox-parametrar: 500 parametrar per mbox.
* Profilparametrar: 500 parameterprofilparametrar per mbox.
* Andra parametrar (URL, refererande URL, osv.): 50 per mbox för varannan parametertyp.

Dessa begränsningar gäller såvida inte begäran förkortas på grund av webbläsarbegränsningar.

Om du använder API:t för gruppleverans är gränsen 50 mbox per batch-begäran.

Om du använder API:t för [gruppleverans](https://developers.adobetarget.com/api/#server-side-batch-delivery) i SDK för mobila tjänster är begränsningen 50 mbox-parametrar, 50 profilparametrar och 50 för andra parametertyper begränsningar i själva API:t. Det går inte att skicka en begäran som innehåller fler än dessa nummer med API:t för gruppleverans. Om en begäran innehåller fler än dessa begränsningar returnerar API:t följande felmeddelande:

&quot;Antalet mboxParameters får inte överskrida 50.&quot;

Begränsningar för slutpunkter:

Batchruta v2:
* mbox parameters 100
* mbox-parameternamn max length 128
* mbox-parametervärdet får inte vara null
* mbox-parametervärde 5000
* profilparametrar 50
* profilparameternamn max längd 128
* profilparametervärdet får inte vara null
* maxlängd för profilparametervärde 256

Slutpunkt för leverans-API
* mbox parameters 50
* mbox-parameternamn max length 128
* mbox-parametervärdet får inte vara null
* mbox-parametervärde 5000
* profilparametrar 50
* profilparameternamn max längd 128
* profilparametervärdet får inte vara null
* maxlängd för profilparametervärde 256

## URL för mbox-begäran

**Gräns**: 2 083 tecken.

Den här gränsen beror på längdbegränsningar i URL:en för Microsoft Internet Explorer.

## parametern mbox3rdPartyId

**Gräns**: 60 tecken.

## Erbjudandenamn

**Gräns**: 250 tecken.

## Erbjudandestorlek

**Gräns**: Följande storleksbegränsningar gäller för erbjudanden:

* 256 kB för HTML-erbjudanden.
* 64 kB för visuella erbjudanden från användargränssnittet.
* 512 kB från API:t.

Om du använder en global mbox är gränsen för hela den innehållsuppsättning som returneras för sidan. Genom att begränsa erbjudandestorleken förbättras sidinläsningstiden. Om gränsen överskrids visas följande meddelande:

&quot;Innehållet i upplevelsen är för stort för att kunna leverera. Ändra upplevelsen så att den påverkar mindre sidkod.&quot;

## Erbjudanden

**Rekommenderad gräns**: Totalt 50 000 erbjudanden.

## orderId-parameter

**Rekommenderad gräns**: 120 tecken.

## orderTotal-parameter

**Rekommenderad gräns**: 120 tecken.

## productPurchasedId, parameter

**Gräns**: 47 tecken per kommaavgränsat värde.

Allt längre trunkeras av systemet.

## Profilskript

**Rekommenderad gräns för aktiva profilskript**: 300

**Rekommenderad gräns för totalt antal profilskript per konto**: 2 000

**Recommendations för att begränsa komplexiteten** i profilskript: Profilskript kan köra ett begränsat antal instruktioner. Mer information finns i [God praxis](/help/c-target/c-visitor-profile/profile-parameters.md#best) i *Profilattribut*.

## Egenskaper

**Rekommenderad gräns**: 5 000 egenskaper.

## Rapportera målgrupper/segment

**Gräns**: 50 rapportmålgrupper/segment per verksamhet.

## Skriptprofilens inmatningsruta i målgränssnittet

**Rekommenderad gräns**: 2 000 tecken.

Beroende på storleken på den kodade strängen, som kan vara mycket längre än Raw-strängen. Om strängen är för stor misslyckas den innan den kommer till Adobe Target.

## Skriptprofilnamn

**Gräns**: 50 tecken.

## Värden för skriptprofil

**Gräns**: 2 048 tecken.

Av prestandaskäl rekommenderar vi ett returvärde som inte är längre än 256 tecken.

Om returvärdet för ett String-returvärde är större än 2 048 tecken inaktiveras skriptet av systemet.

Om storleken på de sammanfogade värdena i arrayen överstiger 2 048 tecken inaktiveras skriptet av systemet för ett arrayreturvärde.

## Framgångsmått

**Gräns**: 200 per aktivitet.

## Målförhållanden

**Rekommenderad gräns**: 1 000 värden.

Det här refererar till antalet radavgränsade värden i måltextområdet. Du kan till exempel ange 1 000 postkoder i ett postnummermål.

## Riktningsregler

**Rekommenderad gräns**: 2 500 tecken per målregelvärde.

**Rekommenderad gräns**: 30 000 unika värden per målgrupp över målinriktningsreglerna.

**Rekommenderad gräns**: 100 000 unika målregelvärden per aktivitet.

