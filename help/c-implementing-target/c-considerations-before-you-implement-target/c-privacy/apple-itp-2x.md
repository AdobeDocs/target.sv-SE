---
keywords: apple;ITP;intelligent tracking prevention;experience cloud id;ecid
description: Information om Adobe Target stöd för Apples ITP 2.x via Experience Cloud ID-biblioteket 4.3.
title: Stöd för Adobe Target och Apple ITP
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 0%

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

Information om [!DNL Adobe Target]-stöd för Apples ITP 2.x via Experience Cloud ID-biblioteket 4.3.

ITP (Intelligent Tracking Prevention) är Apples initiativ att skydda Safaris integritet. Den första releasen av ITP, som var 2017, var inriktad på användning av cookies från tredje part. Faktum är att Apple blockerade cookies från tredje part i sin helhet, vilket i sin tur orsakade stor huvudvärk för reklamtekniker och reklamtekniker eftersom cookies från tredje part i allmänhet används för att spåra besökare och samla in besöksdata. Nu är Apple på språng för att införa begränsningar och begränsningar för hur cookies från första part används i Safari.

Dessa versioner av ITP innehåller följande begränsningar:

| Version | Detaljer |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Klientsidans cookies som placeras i webbläsaren med `document.cookie`-API har fästs vid ett sjudagars förfallodatum.<br>Sändes 21 februari 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Drastiskt reducerade 7- dagars utgångsvärdet till en dag.<br>Utgiven 24 april 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Eliminerade flera tillfälliga lösningar, som att använda localStorage eller JavaScript `Document.referrer property`.<br>Utgiven 23 september 2019. |

## Vilken inverkan har jag som Adobe Target-kund? {#impact}

[!DNL Target] innehåller JavaScript-bibliotek som du kan använda på dina sidor för att  [!DNL Target] kunna leverera personalisering i realtid till besökarna. Det finns tre JavaScript-målbibliotek ([at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) som placerar [!DNL Target]-cookies på dina besökares webbläsare via API:t `document.cookie`. Därför påverkas [!DNL Target]-cookies av Apples ITP 2.x och upphör att gälla efter sju dagar (med ITP 2.1) och efter en dag (med ITP 2.2 och ITP 2.3).

Apple ITP 2.x påverkar [!DNL Target] inom följande områden:

| Effekt | Detaljer |
| --- | --- |
| Möjlig ökning av antalet unika besökare | Eftersom förfallotiden är inställd på sju dagar (med ITP 2.1) och en dag (med ITP 2.2 och ITP 2.3) kan det hända att antalet unika besökare i Safari ökar. Om besökarna återbesöker din domän efter sju dagar (ITP 2.1) eller en dag (ITP 2.2 och ITP 2.3) tvingas [!DNL Target] att placera en ny [!DNL Target]-cookie på din domän i stället för den utgångna cookien. Den nya [!DNL Target]-cookien översätts till en ny unik besökare även om användaren är densamma. |
| Minskade uppslagsperioder för [!DNL Target]-aktiviteter | Besöksprofiler för [!DNL Target]-aktiviteter kan ha en reducerad uppslagsperiod för beslut. [!DNL Target] cookies används för att identifiera en besökare och lagra användarprofilattribut för personalisering. Eftersom [!DNL Target]-cookies kan upphöra på Safari efter sju dagar (ITP 2.1) eller en dag (ITP 2.2 och 2.3), kan de användarprofildata som var knutna till den rensade [!DNL Target]-cookien inte användas för beslut. |
| Profilskript baserade på 3rdPartyID | På grund av att utgångsfönstret anges till sju dagar (med ITP 2.1) och en dag (med ITP 2.2 och ITP 2.3) kommer [profilskript](/help/c-target/c-visitor-profile/profile-parameters.md) som baseras på cookien 3rdPartyID att sluta fungera när det förfaller. |
| QA/Preview URLs in iOS devices | På grund av att förfallotiden är inställd på sju dagar (med ITP 2.1) och en dag (med ITP 2.2 och ITP 2.3) kommer [URL:er för QA/Preview](/help/c-activities/c-activity-qa/activity-qa.md) att sluta fungera när de upphör att gälla eftersom URL:erna är baserade på cookien för 3rdPartyID. |

## Påverkas min nuvarande implementering av [!DNL Target]?

I en Safari-webbläsare navigerar du till den webbplats där du har ett JavaScript-bibliotek. [!DNL Target] Om du ser en [!DNL Target]-cookie som angetts i en CNAME-kontext, till exempel `analytics.company.com`, påverkas du inte av ITP 2.x.

Om du använder Experience Cloud ID-biblioteket (ECID) förutom JavaScript-biblioteket Target, påverkas implementeringen av de sätt som anges i den här artikeln: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## Hur kan jag minska effekten av framtida versioner av ITP 2.x till Target?

Utför följande uppgifter för att minska verkningarna av framtida versioner av ITP 2.x till Target:

1. Distribuera Experience Cloud ID-biblioteket (ECID) till dina sidor.

   ECID-biblioteket möjliggör ett ramverk för identifiering av människor för Experience Cloud Core-lösningar. Med ECID-biblioteket kan du identifiera samma webbplatsbesökare och deras data i olika Experience Cloud-lösningar genom att tilldela permanenta och unika identifierare. ECID-biblioteket uppdateras ofta för att hjälpa dig att minska eventuella ITP-relaterade ändringar som påverkar implementeringen.

   För ITP 2.x måste [ECID-bibliotek 4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html) användas för att reducera.

1. Använd Adobe CNAME och registrera dig i Adobe Analytics program för hanterade certifikat.

   När du har installerat ECID-biblioteket 4.3.0+ kan du använda Adobe Analytics CNAME och Managed Certificate Program. Med det här programmet kan du utan kostnad implementera ett förstahandscertifikat för cookies från första part. Tack vare CNAME kan [!DNL Target]-kunder minska påverkan av ITP 2.x.

   Om du inte utnyttjar CNAME kan du starta processen genom att prata med din kontorepresentant och registrera dig i [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

När du har distribuerat ett Target JavaScript-bibliotek i samband med ECID-biblioteket v4.3.0+ och registrerat dig för programmet för hanterat certifikat i Adobe för att utnyttja CNAME får du en robust och långsiktig reduceringsplan för ITP-relaterade ändringar.

I takt med att branschen strävar efter att skapa en säkrare webbsajt för konsumenterna är [!DNL Adobe Target] helt engagerat i att leverera personaliserade upplevelser och samtidigt uppfylla och överträffa besökarnas förväntningar på integriteten. [!DNL Adobe Target] har redan meddelat att det finns stöd för  [Googles ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Chrome-policy för SameSite förutom stöd för Apples ITP 2.x.

I takt med att politiken utvecklas för att skydda våra kunder fortsätter [!DNL Adobe] att stödja dessa initiativ i [!DNL Target], samtidigt som våra kunder får de bästa personaliserade upplevelserna i sin klass.
