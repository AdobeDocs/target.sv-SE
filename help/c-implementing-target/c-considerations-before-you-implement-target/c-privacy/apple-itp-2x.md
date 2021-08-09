---
keywords: äpple;ITP;intelligent tracking prevent;experience cloud id;ecid
description: Läs om Adobe [!DNL Target] och effekten av Apple Intelligent Tracking Prevention (ITP) som syftar till att skydda Safaris integritet.
title: Hur hanterar [!DNL Target] Apple ITP stöd?
feature: Integritet och säkerhet
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 083a92c53d11d865738b456acf47cf9663fddcd1
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 0%

---

# Apple Intelligent Tracking Prevention (ITP) 2.x

ITP (Intelligent Tracking Prevention) är Apples initiativ att skydda Safaris integritet. Den första releasen av ITP, som var 2017, var inriktad på användning av cookies från tredje part. Faktum är att Apple blockerade cookies från tredje part i sin helhet, vilket i sin tur orsakade stor huvudvärk för reklamtekniker och reklamtekniker eftersom cookies från tredje part i allmänhet används för att spåra besökare och samla in besöksdata. Nu är Apple på språng för att införa begränsningar och begränsningar för hur cookies från första part används i Safari.

Dessa versioner av ITP innehåller följande begränsningar:

| Version | Detaljer |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Klientsidans cookies som placeras i webbläsaren med `document.cookie` API har fästs vid ett sjudagars förfallodatum.<br>Sändes 21 februari 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Drastiskt reducerade 7- dagars utgångsvärdet till en dag.<br>Utgiven 24 april 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Eliminerade flera tillfälliga lösningar, som att använda localStorage eller JavaScript `Document.referrer property`.<br>Utgiven 23 september 2019.<br>CNAME-klädd försvarsfunktion till ITP släppt i Safari 14, macOS Big Sur, Catalina, Mojave, iOS 14 och iPadOS 14. Alla cookies som skapas av ett CNAME-insvept HTTP-svar från tredje part kommer att upphöra om sju dagar.<br>Den 12 november 2020. |

## Vad har jag för effekt som kund av Adobe [!DNL Target]? {#impact}

[!DNL Target] innehåller JavaScript-bibliotek som du kan använda på dina sidor för att  [!DNL Target] kunna leverera personalisering i realtid till besökarna. Det finns tre JavaScript-målbibliotek på .js 1.x, at.js 2.x som placerar [!DNL Target]-cookies på klientsidan i besökarens webbläsare via API:t `document.cookie`. Därför påverkas [!DNL Target]-cookies av Apples ITP 2.1, 2.2 och 2.3 och upphör att gälla efter sju dagar (med ITP 2.1) och efter en dag (med ITP 2.2 och ITP 2.3).

Apple ITP 2.x påverkar [!DNL Target] inom följande områden:

| Effekt | Detaljer |
| --- | --- |
| Möjlig ökning av antalet unika besökare | Eftersom förfallotiden är inställd på sju dagar (med ITP 2.1) och en dag (med ITP 2.2 och ITP 2.3) kan det hända att antalet unika besökare i Safari ökar. Om besökarna återbesöker din domän efter sju dagar (ITP 2.1) eller en dag (ITP 2.2 och ITP 2.3) tvingas [!DNL Target] att placera en ny [!DNL Target]-cookie på din domän i stället för den utgångna cookien. Den nya [!DNL Target]-cookien översätts till en ny unik besökare även om användaren är densamma. |
| Minskade uppslagsperioder för [!DNL Target]-aktiviteter | Besöksprofiler för [!DNL Target]-aktiviteter kan ha en reducerad uppslagsperiod för beslut. [!DNL Target] cookies används för att identifiera en besökare och lagra användarprofilattribut för personalisering. Eftersom [!DNL Target]-cookies kan upphöra på Safari efter sju dagar (ITP 2.1) eller en dag (ITP 2.2 och 2.3), kan de användarprofildata som var knutna till den rensade [!DNL Target]-cookien inte användas för beslut. |
| Profilskript baserade på 3rdPartyID | På grund av att utgångsfönstret anges till sju dagar (med ITP 2.1) och en dag (med ITP 2.2 och ITP 2.3) kommer [profilskript](/help/c-target/c-visitor-profile/profile-parameters.md) som baseras på cookien 3rdPartyID att sluta fungera när det förfaller. |
| QA/Preview URLs in iOS devices | På grund av att förfallotiden är inställd på sju dagar (med ITP 2.1) och en dag (med ITP 2.2 och ITP 2.3) kommer [URL:er för QA/Preview](/help/c-activities/c-activity-qa/activity-qa.md) att sluta fungera när de upphör att gälla eftersom URL:erna är baserade på cookien för 3rdPartyID. |

## Påverkas min nuvarande implementering av [!DNL Target]?

Om du använder Experience Cloud ID-biblioteket (ECID) förutom JavaScript-biblioteket [!DNL Target] kommer implementeringen att påverkas på de sätt som anges i den här artikeln: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).
