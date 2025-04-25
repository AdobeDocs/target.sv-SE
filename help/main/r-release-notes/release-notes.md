---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar,aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 579ebd9bebd3faa724f0d1d542f4d23766adefe3
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## [!DNL Target Standard/Premium] 25.4.5 (25 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som orsakade skillnader i målgruppslistor mellan inställningssidan [!UICONTROL Activity] och översiktssidan [!UICONTROL Reporting]. (TGT-52203)
* Korrigerade ett problem som förhindrade att en ny sida lades till i en aktivitet på grund av ett ogiltigt användarinmatningsfel. (TGT-52263)
* Korrigerade ett problem som gjorde att `OptionLocalIDs` ökade felaktigt när alternativet inte ändrades. (TGT-52187)
* Korrigerade ett problem som gjorde att `location` och `OptionLocalIDs` ökade felaktigt när alternativet inte ändrades. (TGT-52188)
* Ett problem som gjorde att platsen på aktivitetens [!UICONTROL Overview]-sida blev felaktig har korrigerats. (TGT-52182)
* Korrigerade ett problem där en ogiltig väljarvarning inte visades för en ogiltig plats. (TGT-52110)
* Ett problem har korrigerats så att hämtade rapportfiler korrekt visar data i rapportgränssnittet. (TGT-52068)
* Ett problem har korrigerats så att gruppåtgärder inte misslyckas efter att sidleveransregler har lagts till. (TGT-52097)
* Ett problem som gjorde att [!DNL Target] trimmade alla frågeparametrar från webbplatsens URL har åtgärdats. (TGT-52100)
* Ett konsolfel som hindrade kunder från att skapa aktiviteter i det gamla och uppdaterade [!DNL Target]-gränssnittet har åtgärdats. (TGT-52181)
* Korrigerade ett problem som hindrade kunder från att lägga till nya sidor, vilket orsakade ett ogiltigt användarinmatningsfel. (TGT-52258)
* Korrigerade ett problem som gjorde att ändringar försvann efter att du lagt till ytterligare sidor och sedan navigerade tillbaka till fliken [!UICONTROL Experiences]. (TGT-52264)
* Korrigerade ett problem som hindrade kunder från att ändra målgrupp i en [!UICONTROL Experience Targeting] (XT)-aktivitet. (TGT-52191)
* Korrigerade ett fel som förhindrade redigering av en XT-aktivitet på grund av en gränssnittsregel som inte stöds. (TGT-52273)
* Korrigerade ett fel i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) där vägbeskrivningar inte alltid visades längst ned i redigeraren, vilket medförde problem med att välja element exakt. (TGT-52169)
* Ett problem har korrigerats där listrutan [!UICONTROL Audience] inte kunde visa alla målgrupper på grund av sidnumrering. (TGT-52204)
* Ett problem som orsakade ett ogiltigt användarindatameddelande när nya erbjudanden lades till i [!UICONTROL Automated Personalization] (AP)-aktiviteter har åtgärdats. (TGT-52210)
* Korrigerade ett problem där [!UICONTROL Analytics for Target] (A4T) felaktigt valdes som rapportkälla, trots att kunden inte hade åtkomst till A4T. (TGT-52226)
* Ett problem som gjorde att en aktivitet med URL-måttet [!UICONTROL View a Page] inte kunde sparas har åtgärdats. (TGT-52260)
* Korrigerade ett problem som hindrade kunder från att välja arbetsytor när de skapade erbjudanden i en aktivitet. (TGT-52289)
* Ett problem som hindrade kunder från att skapa aktiviteter på alla arbetsytor har korrigerats. (gt-52218)
* Ett problem har korrigerats där ändringar från en upplevelse visades felaktigt när de växlades till en annan upplevelse. (TGT-52184)
* Ett problem har korrigerats där standarderbjudandet felaktigt visades i användargränssnittet för [!DNL Target] när aktiviteten öppnades. (TGT-52198)

## Uppdatering av målbehörigheter (22 april 2025)

Den här framtida uppdateringen förbättrar organisationskontrollen över [!DNL Target] instanskonfigurationer och förhindrar oavsiktliga uppdateringar som kan påverka aktivitetsleveransen i olika testnings- och personaliseringsteam.

Från och med den 22 april 2025 kan bara [!UICONTROL Product]- och [!UICONTROL Solutions]-administratörer uppdatera inställningarna i [!UICONTROL Administration] -avsnitten, oavsett vilka roller de har i [!DNL Target] -arbetsytorna. Användare utan den här behörigheten har skrivskyddad åtkomst till [!UICONTROL Administration]-avsnitten.

Mer information finns i [Administrera mål](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.4 (17 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett felmeddelande har lagts till som hjälp för användarna när de vill lösa dubblettalternativ i en aktivitet. (TGT-51927)
* Ett problem har korrigerats där `ClickTrack` väljare inte togs bort när sidor eller upplevelser med omdirigeringserbjudanden togs bort. (TGT-51952)
* Ett problem som orsakats av att tomma `ClickTrack` väljare tillåts har korrigerats. [!DNL Target] kräver nu att väljarfältet inte får vara tomt. (TGT-52107)
* Korrigerade ett problem som felaktigt tillät mätvärden med dubblettnamn. Mätvärden kräver nu unika namn. (TGT-52201)
* Ett problem har korrigerats där målgruppsdefinitioner inte var synliga vid redigering av målgruppsanpassning på erbjudandenivå i [!UICONTROL Automated Personalization] (AP)-aktiviteter. (TGT-52148)
* Ett problem som gjorde att kunder med [!UICONTROL Editor] rättigheter inte kunde spara aktiviteter har korrigerats. (TGT-5227)
* `OptionLocalIDs` ökar inte längre felaktigt när alternativet inte ändras. (TGT-52139)
* Korrigerade ett problem som orsakade ett ogiltigt `optionLocalIds`-meddelande när en aktivitet skulle skapas. (TGT-52154)
* Skillnader mellan `OptionLocalIDs` som har definierats för en aktivitet och de som används för att definiera upplevelser har korrigerats. (TGT-52215)
* Korrigerade ett problem som orsakade ett valideringsfel som inträffade när en A/B-aktivitet skulle skapas. (TGT-51923)

## [!DNL Target Standard/Premium] 25.4.3 (11 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett fel som gjorde att kunderna inte kunde öppna popup-fönstret för målgruppsinformation för vissa [!UICONTROL Experience Targeting] (XT)-aktiviteter har åtgärdats. (TGT-52049)
* Ett problem har korrigerats där målgruppsinställningen återgick till [!UICONTROL All Visitors] efter ändringar i [!UICONTROL Visual Experience Composer] (VEC). (TGT-52132)
* Ett problem har korrigerats där målgruppsförbättringar inte visades för specifika aktiviteter (TGT-52057)
* Ett problem som gjorde att kunder inte kunde infoga [!UICONTROL Experience Fragment] i standardarbetsytan har korrigerats. (TGT-52073)
* Korrigerade ett problem där ett erbjudande visades som &quot;Innehåll hittades inte&quot; och inte visades på sidan [!UICONTROL Offers] för en [!UICONTROL Automated Personalization]-aktivitet (AP). (TGT-52150)
* Lagt till möjlighet att tillåta duplicerade målgrupper inom en aktivitet. (TGT-51200)
* Ett problem har korrigerats där fel mbox-namn visades på sidan [!UICONTROL Goals & Settings] för en XT-aktivitet efter redigering. (TGT-52026)
* Ett problem har korrigerats där `defaultContent` visades i alternativ trots att `experiences/optionLocations` inte fanns. (TGT-52036)
* Ett problem har korrigerats som säkerställer att tomma strängar inte konverteras till null-värden. (TGT-52037)
* Korrigerade ett problem som krävde att kunderna konfigurerade om [!UICONTROL Optimization Goal] i [!UICONTROL Reporting Settings] på sidan [!UICONTROL Goals & Settings] efter redigeringar. (TGT-52071)
* Ett problem har korrigerats där en aktivitet utan sidleveransregler visade flera regler på sidan [!UICONTROL Overview]. (TGT-52084)
* Ett felmeddelande har lagts till för användare som försöker spara ett erbjudande med tecken utanför det grundläggande flerspråkiga planet, till exempel känslolägesikoner. (TGT-52105)
* Ett problem har korrigerats där öppnandet av en aktivitet utlöste felmeddelandet:&quot;Den här aktiviteten använder en eller flera målgrupper som har tagits bort från källan.&quot; (TGT-52120)
* Ett problem har korrigerats där ClickTrack-mått inte visades i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) under redigeringen. (TGT-52152)
* Ett problem har korrigerats där en URL med en frågeparameter som aktivitetsplatsen inte visade frågeparametern på aktivitetens [!UICONTROL Overview]-sida. (TGT-51635)
* Korrigerade ett problem som förhindrade att hela upplevelsens URL visades i [!UICONTROL Browse mode] i [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Korrigerade ett problem där redigering av en aktivitet orsakade att sidans leverans lade till &quot;/&quot; i slutet av URL:en, vilket gjorde den ogiltig. (TGT-52114)
* Ett problem har korrigerats där länken [!UICONTROL Activity QA] i [!UICONTROL Form-Based Experience Composer] felaktigt omdirigerades till hemsidan [!DNL Adobe Experience Cloud]. (TGT-52055)
* Ett problem har korrigerats där ytterligare sidor som lagts till i aktiviteten [!UICONTROL A/B Test] inte sparades när de sparades och öppnades igen. (TGT-51994)
* Ett problem som gjorde att kunder inte kunde ta bort format i avsnittet med infogade format har korrigerats. (TGT-52070)
* Åtkomsten till [målgruppsdefinitionskort](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) i dialogrutan [!UICONTROL Activity QA] återställdes, ungefär som det gamla användargränssnittet. (TGT-52056)
* Det uppdaterade användargränssnittet sparade inte sidor eller målgrupper utan ändringar. Om kunderna har lagt till nya sidor eller målgrupper i en aktivitet men inte har gjort några ändringar i dem, ignorerade [!DNL Target] de oförändrade målgrupperna när de sparades. Meddelanden har lagts till på relevanta platser för att informera användarna om detta. (TGT-52104)

## [!DNL Target Standard/Premium] 25.4.1 (2 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som gjorde att upplevelsemålgrupperna försvann från aktiviteter. (TGT-52003)
* Korrigerade ett problem som orsakade oväntade element under leveransen. (TGT-52011)
* Korrigerade ett problem som hindrade kunder från att visa målgruppen i måldiagrammet på Ove[!UICONTROL r]view-sidan och under aktivitetsredigering. (TGT-52050)
* Ett problem som gjorde att kunderna inte kunde ändra ordning på upplevelserna har korrigerats i prioritetsordning i [!UICONTROL Experience Targeting] (XT)-aktiviteter har åtgärdats. (TGT-52054)
* Korrigerade ett problem som orsakade felaktig återgivning när textstilen ändrades. (TGT-51876)
* Ett problem har korrigerats som innebär att när ett omdirigeringserbjudande ändras tas även alla [!UICONTROL ClickTrack]-väljare som är associerade med det erbjudandet bort av [!DNL Target]. (TGT-51936)
* Korrigerade ett problem som gjorde att [!DNL Target] felaktigt sparade väljaren när [!UICONTROL ClickTrack] avbröts. (TGT-51937)
* Korrigerade ett problem som utlöste ett ogiltigt namnfel efter att mbox-väljaren öppnats och stängts på sidan [!UICONTROL Goals & Settings] utan att några ändringar gjorts. (TGT-51983)
* Korrigerade ett problem som blockerade redigering av ad hoc-erbjudanden som skapades i det gamla [!DNL Target]-gränssnittet. (TGT-51984)
* Ett problem som blockerade redigeringsaktiviteter med ad hoc-erbjudanden som innehåller anpassad kod har korrigerats. (TGT-51995)
* Korrigerade ett problem som gjorde att undantagsregler visades som inkluderingsregler när kombinerade målgruppsdefinitioner redigerades. (TGT-51999)
* Ett problem som gjorde att anpassad kod inte kunde visas korrekt vid redigering av upplevelser har åtgärdats. (TGT-52005)
* Ett problem som gjorde att alternativet [!UICONTROL Insert Before] inte var tillgängligt för infogning av innehåll före navigeringsfältet har korrigerats. (TGT-52031)
* Korrigerade ett problem som förhindrade att standardupplevelsen markerades korrekt vid rapportering. (TGT-51716)
* Korrigerade ett problem som utlöste ett `default message [Invalid optionLocalIds: xx]]`-meddelande när en aktivitet skapades. (TGT-52038)

## at.js version 2.11.8 (31 mars 2025)

* Åtgärdade en CodeQL-identifierad säkerhetslucka i strängsuffixvalidering för att förhindra kantfall vid storleksändrings- och flyttningsåtgärder. (TNT-51516)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, Versionsinformation om tidigare versioner och Experience Cloud Versionsinformation

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Adobe Priority-produktuppdatering](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
