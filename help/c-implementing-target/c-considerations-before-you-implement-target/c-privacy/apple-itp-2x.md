---
keywords: apple;ITP;intelligent tracking prevention
description: Information om Adobe Target-stöd för Apples ITP 2.1 och ITP 2.2 via Experience Cloud ID-biblioteket (ECID) 4.3.
title: Stöd för Adobe Target och Apple ITP
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

ITP (Intelligent Tracking Prevention) är Apples initiativ att skydda Safaris integritet. Den första releasen av ITP, som var 2017, var inriktad på användning av cookies från tredje part. Faktum är att Apple blockerade cookies från tredje part i sin helhet, vilket i sin tur orsakade stor huvudvärk för reklamtekniker och reklamtekniker eftersom cookies från tredje part i allmänhet används för att spåra besökare och samla in besöksdata. Nu är Apple på språng för att införa begränsningar och begränsningar för hur cookies från första part används i Safari.

Dessa versioner av ITP innehåller följande begränsningar:

| Version | Detaljer |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Klickade på cookies på klienten som placerats i webbläsaren med API:t till ett sjudagars förfallodatum. `document.cookie`<br>Sändes 21 februari 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Drastiskt reducerade 7- dagars utgångsvärdet till en dag.<br>Utgiven 24 april 2019. |

## Vilken inverkan har jag som Adobe Target-kund?

[!DNL Target] innehåller JavaScript-bibliotek som du kan använda på dina sidor för att [!DNL Target] leverera personalisering i realtid till besökarna. Det finns tre JavaScript-målbibliotek ([at.js 1).*x* och at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)och[mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) som placerar cookies på klientsidan[!DNL Target]i besökarnas webbläsare via`document.cookie`API. Detta innebär att[!DNL Target]cookies påverkas av Apples ITP 2.1 och 2.2 och upphör att gälla efter sju dagar (med ITP 2.1) och efter en dag (med ITP 2.2).

Apple ITP 2.1 och 2.1 påverkar [!DNL Target] följande områden:

| Effekt | Detaljer |
| --- | --- |
| Möjlig ökning av antalet unika besökare | Eftersom förfallotiden är inställd på sju dagar (med ITP 2.1) och en dag (med ITP 2.2) kan det hända att antalet unika besökare i webbläsarna Safari ökar. Om dina besökare återbesöker din domän efter sju dagar (ITP 2.1) eller en dag (ITP 2.2) [!DNL Target] tvingas att placera en ny [!DNL Target] cookie på din domän i stället för den utgångna cookien. Den nya [!DNL Target] cookie-filen innebär en ny unik besökare även om användaren är densamma. |
| Minskade uppslagsperioder för [!DNL Target] aktiviteter | Besöksprofiler för aktiviteter kan ha en reducerad uppslagsperiod för beslut. [!DNL Target] [!DNL Target] cookies används för att identifiera en besökare och lagra användarprofilattribut för personalisering. Eftersom cookies kan upphöra att gälla på Safari efter sju dagar (ITP 2.1) eller en dag (ITP 2.2), kan de användarprofildata som var knutna till den rensade [!DNL Target] [!DNL Target] cookien inte användas för beslut. |

## Påverkas min nuvarande implementering av [!DNL Target] ?

I en Safari-webbläsare navigerar du till den webbplats där du har ett [!DNL Target] JavaScript-bibliotek. Om du ser en cookie som har angetts i samband med en CNAME, till exempel [!DNL Target] `analytics.company.com`, påverkas du inte av ITP 2.1 eller 2.2.

Om du använder Experience Cloud ID-biblioteket (ECID) förutom JavaScript-målbiblioteket påverkas implementeringen på de sätt som anges i den här artikeln: [Safari ITP 2.1 - Effekt på kunder](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)med Adobe Experience Cloud och Experience Platform.

## Hur kan jag minska effekterna av ITP 2.1, ITP 2.2 och framtida ITP-releaser för [!DNL Target]?

Utför följande uppgifter för att minska verkningarna av ITP 2.1, ITP 2.2 och framtida ITP-releaser [!DNL Target]:

1. Distribuera Experience Cloud ID-biblioteket (ECID) till era sidor.

   ECID-biblioteket aktiverar ramverket för personidentifiering för Experience Cloud-kärnlösningar. Med ECID-biblioteket kan du identifiera samma webbplatsbesökare och deras data i olika Experience Cloud-lösningar genom att tilldela permanenta och unika identifierare. ECID-biblioteket uppdateras ofta för att hjälpa dig att minska eventuella ITP-relaterade ändringar som påverkar implementeringen.

   För ITP 2.1 och ITP 2.2 måste [ECID-biblioteket 4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) användas för att reducera.

1. Använd Adobes CNAME och registrera dig i Adobe Analytics program för hanterade certifikat.

   När du har installerat ECID-biblioteket 4.3.0+ kan du använda Adobe Analytics CNAME och Managed Certificate Program. Med det här programmet kan du utan kostnad implementera ett förstahandscertifikat för cookies från första part. Tack vare CNAME kan [!DNL Target] kunderna minska effekterna av ITP 2.1 och ITP 2.2.

   Om du inte utnyttjar CNAME kan du påbörja processen genom att prata med din kontorepresentant och registrera dig i [Adobes program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)för hanterade certifikat.

När du har distribuerat ett Target JavaScript-bibliotek tillsammans med ECID-biblioteket v4.3.0+ och registrerat dig för Adobe Managed Certificate Program för att utnyttja CNAME får du en robust och långsiktig reduceringsplan för ITP-relaterade ändringar.

I takt med att branschen strävar efter att skapa en säkrare webbsajt för konsumenterna är den helt engagerad i att leverera personaliserade upplevelser och samtidigt uppfylla och överträffa besökarnas förväntningar på integritetsskydd. [!DNL Adobe Target] [!DNL Adobe Target] har redan meddelat stöd för [Googles Policy](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) för samma webbplats, förutom stöd för Apples ITP 2.1 och ITP 2.2.

I takt med att politiken utvecklas för att skydda våra kunder fortsätter den också att stödja dessa initiativ i [!DNL Adobe] [!DNL Target], samtidigt som våra kunder får de bästa personaliserade upplevelserna i sin klass.
