---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar,aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 15aa5cc44cd610dd330b5c1fb4f0a771f71b2f84
workflow-type: tm+mt
source-wordcount: '1670'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Borttagning av version av målgränssnitt (23 maj 2025) {#toggle}

Det nya [!DNL Target]-användargränssnittet kommer att vara klart den 27 maj 2025 **.** Då har alla kunder tillgång till den senaste gränssnittsversionen.

Från och med **22 juni 2025** tas gränssnittsversionen bort. Alla användare kommer att övergå permanent till det nya gränssnittet, utan möjlighet att återgå till den tidigare versionen.

**Viktig information om användargränssnittets versionsväxel**

Vi erbjuder en tillfällig funktion som gör att du kan växla mellan det uppdaterade [!DNL Target]-gränssnittet och den äldre versionen med en växlingsknapp. Det här alternativet är endast tillgängligt under den sista fasen av UI-utrullningen.

![Växla mellan målgränssnittsversion](/help/main/r-release-notes/assets/toggle.png)

När utrullningen är klar tas växlingsknappen bort och alla användare övergår permanent till det uppdaterade användargränssnittet den **22 juni 2025**. Adobe rekommenderar att du planerar i förväg eftersom den här funktionen kommer att fasas ut snart.

**Begränsningar för gränssnittets växlingsbeteende**

* **Synlighet för nya aktiviteter**: Aktiviteter som har skapats i det uppdaterade användargränssnittet visas inte om du växlar tillbaka till det gamla användargränssnittet.
* **Redigera befintliga aktiviteter**: Ändringar som gjorts i befintliga aktiviteter (som ursprungligen skapades i det äldre användargränssnittet) när det uppdaterade användargränssnittet används kommer att publiceras på webbplatsen. De här uppdateringarna visas dock inte i det gamla användargränssnittet om du byter tillbaka. Endast de senaste uppdateringarna från det gamla användargränssnittet visas där.
* **Enhetlig aktivitetsinformation**: De senaste ändringarna, oavsett vilket användargränssnitt du använder, visas på din aktiva webbplats. Det gamla användargränssnittet visar dock endast de senaste ändringarna som gjorts i den versionen. Detta kan orsaka förvirring om aktiviteter som redigeras i det uppdaterade användargränssnittet ser annorlunda ut än i det äldre användargränssnittet.

Mer information om det uppdaterade användargränssnittet finns i följande kommentarer för tidigare versioner:

* [Versionsinformation om [!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)
* [Versionsinformation om [!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)

## [!DNL Target Standard/Premium] 25.5.3 (22 maj 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem har korrigerats där funktionen Sök efter namn i listan [!UICONTROL Activities] inte fungerade korrekt med flerordsfrågor. (TGT-52529)
* Ett problem som förhindrade att upplevelser från [!UICONTROL Automated Personalization] (AP)-aktiviteter exkluderades har korrigerats. (TGT-52383)
* Ett problem har korrigerats där alternativet [!UICONTROL Contains] saknades i [!UICONTROL Filter Rules] vid hantering av innehåll i AP-aktiviteter. (TGT-52384)
* Korrigerade en rapportinkonsekvens i [!UICONTROL Automated Personalization] (AP)-aktiviteter, specifikt relaterat till hur standarderbjudanden spåras och rapporteras med hjälp av `optionLocalId`-värden från [!DNL Target]:s interna system.
* Korrigerade ett problem där QA-länkar inte kunde leverera den avsedda aktivitetsupplevelsen. (TGT-52163)
* Ett problem har korrigerats där användare med [!UICONTROL Approver] behörigheter felaktigt blockerades från redigering av aktiva aktiviteter och ett felmeddelande om nekad åtkomst mottogs. (TGT-52416)
* Ett problem har korrigerats där målgruppsförbättringar inte kunde visas för vissa aktiviteter i det uppdaterade användargränssnittet för [!DNL Target]. (TGT-52057)
* Korrigerade ett problem som medförde att målgruppsförbättringar och aktivitetspubliker hämtades i det uppdaterade användargränssnittet. (TGT-52158)
* Korrigerade ett problem där generering av ad hoc-erbjudanden resulterade i dubbla erbjudanden. (TGT-51938)
* Korrigerade ett problem som blockerade uppdateringar av erbjudanden och felaktigt visade ett fel av typen&quot;Ogiltig användare&quot;. (TGT-52361)
* Ett problem som gjorde att befintliga aktiviteter inte kunde sparas har korrigerats. Felet &quot;Ogiltigt användarindata&quot; utlöstes. (TGT-52422)
* Korrigerade ett problem som blockerade redigering av befintliga HTML-erbjudanden och utlöste ett fel av typen&quot;Ogiltig användarinmatning&quot; vid sparande, även när inga kodändringar gjordes. (TGT-52351)
* Korrigerade ett fel som gjorde att [!DNL Target] inte kunde identifiera tecknet&quot;#&quot; i webbplatsens URL. (TGT-52093)
* Korrigerade ett problem som förhindrade redigering av [!DNL Recommendations] aktiviteter för att lägga till eller uppdatera kampanjer, vilket orsakade fel vid sparande och dubblettkampanjer. (TGT-52343)
* Korrigerade ett problem som förhindrade ändringar av villkor eller design i [!DNL Recommendations]-aktiviteter, vilket resulterade i ett &quot;ogiltigt JSON: okänt egenskapsnamn&quot;-fel. (TGT-52375)
* Ett problem har korrigerats där sekvensvillkor inte kunde visas korrekt i [!UICONTROL Visual Experience Composer] (VEC) för [!DNL Recommendations]-aktiviteter. (TGT-52435)
* Ett problem har korrigerats där vyer inte identifierades korrekt på SPA-sidor när [!DNL Adobe Experience Platform Web SDK] användes. (TGT-52106)
* Ett problem har korrigerats där ODS-information (On-Device Decisioning) inte sparades korrekt trots att den ingick i batchdriftens nyttolast. (TGT-52406)
* Ett `audienceMetadata`-fält har lagts till i aktiviteter, vilket gör att det kan läsas och uppdateras under redigeringen. (TGT-51004)
* Ett felmeddelande har lagts till för att varna användare när en målgruppstid är ogiltig. (TGT52522)
* Aktivitetsstrukturen har uppdaterats med stöd för duplicerade målgrupper av olika typer. (TGT-51200)

## [!DNL Adobe Target] [!DNL AI Assistant] (16 maj 2025)

Vi är glada över att kunna meddela att [!DNL AI Assistant] har startats i [!DNL Adobe Target]! Den här kraftfulla gränssnittsfunktionen är utformad för att hjälpa dig att enkelt navigera och förstå [!DNL Target]-koncept. Finns för flera produkter i [!DNL Adobe Experience Cloud], inklusive [!DNL Target], [!DNL AI Assistant] är här för att revolutionera din upplevelse.

[!DNL AI Assistant] i [!UICONTROL Target] är ett konversationsverktyg som du kan använda för att snabba upp dina arbetsflöden med [!DNL Experience Platform] program och tjänster. Använd [!DNL AI Assistant] för att öka produktiviteten och förbättra din förståelse för produktkunskaper

I [!DNL Target] innehåller den första fasen av [!DNL AI Assistant] ovärderlig produktkunskap baserad på [!DNL Experience League]-dokumentation. Oavsett om du konfigurerar ett profilskript, felsöker fel eller funderar på att uppgradera till AEP Web SDK har [!DNL AI Assistant] det som behövs.

Mer information finns i [Översikt över Adobe Experience Platform AI Assistant](/help/main/c-intro/ai-assistant.md).

## [!DNL Target Standard/Premium] 25.5.2 (8 maj 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* [!DNL Target] användare med [!UICONTROL Product Administrator]- och [!UICONTROL System Administrator]-behörighet kan nu redigera alla inställningar på [!UICONTROL Administration]-sidorna, oavsett deras roll i [!DNL Target]. Användare utan dessa behörigheter har skrivskyddad åtkomst till de här inställningarna. Den här uppdateringen ger striktare åtkomstkontroll över [administrationsinställningarna](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Korrigerade ett cachelagringsproblem som förhindrade att aktiviteten [Webbplatsinställningar](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) sparades. (TGT-52213)
* Ett problem har korrigerats där kunderna inte kunde aktivera val efter ID och klass i avsnittet [!UICONTROL Site Preferences] efter att webbplatsen lästs in i VEC. Inställningen [!UICONTROL Site Preferences] återställs automatiskt till inaktiverad även efter att den har aktiverats. (TGT-52207)
* Ett problem har korrigerats där [!UICONTROL Visual Experience Composer] (VEC) inte kunde visa rätt sida när [URL:er för sidleverans](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) avslutades med ett snedstreck (/). (TGT-52237)
* Ett problem som förhindrade borttagning av anpassade kodändringar när upplevelser ändrades har åtgärdats. (TGT-52240)
* Ett problem har korrigerats där HTML ändringar i VEC överlappade befintliga sidelement. (TGT-52265)
* Ett problem har korrigerats som gjorde att det inte gick att redigera anpassad kod i den uppdaterade VEC-koden eftersom den befintliga anpassade koden inte var synlig i redigeraren. (TGT-52272)
* Korrigerade ett problem som orsakade felmeddelandet&quot;Duplicerade namn är inte tillåtna&quot; när en rekommendationsaktivitet sparades. (TGT-52318)
* Ett problem i den uppdaterade VEC som gjorde att kunderna inte kunde redigera textelement eller ta bort behållarobjekt har åtgärdats. (TGT-52348)
* Ett problem som gjorde att [!DNL Customer Journey Analytics] inte kunde visas korrekt på en aktivitetssida för [!UICONTROL Overview] har korrigerats. (TGT-52359)
* Korrigerade ett problem som förhindrade rapportgrupper från att finnas kvar i [!UICONTROL Automated Personalization] (AP) aktiviteter. (TGT-52368)
* Korrigerade ett problem som förhindrade att aktiviteter som innehöll offertsbeslut sparades. (TGT-52390)
* Ett problem har korrigerats där standarderbjudandet valdes, men annat erbjudandeinnehåll visades i [!UICONTROL Automated Personalization] (AP)- och [!UICONTROL Multivariate Test] (MVT)-aktiviteter. (TGT-52372)
* GET-behörighetslogik för kontroll med OR har korrigerats mellan fullständig organisationsåtkomst och specifik åtkomst för organisation + användare. (TGT-52374)
* Korrigerade ett problem där målgruppsnamn inte visades efter att en målgrupp har valts för [!UICONTROL Managed Content] och [!UICONTROL Reporting Audiences], trots att [!UICONTROL Show Only Selected] var aktiverat. (TGT-52393)

## [!DNL Target Standard/Premium] 25.5.1 (5 maj 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som hindrade målgruppsförbättringar från att visas för vissa aktiviteter i det uppdaterade användargränssnittet. (TGT-52057)
* Ett problem som förhindrade användning av kombinerade målgrupper i aktiviteter har korrigerats. (TGT-52346)
* Ett problem som gjorde att det inte gick att skapa en ny aktivitet på en arbetsyta som inte är standard med en målgrupp som bara har aktiviteten från samma arbetsyta har åtgärdats. (TGE-52349)
* Korrigerade ett problem som gjorde att målgrupper med endast aktivitet försvann från det uppdaterade användargränssnittet efter att ha skapat och valt en ny målgrupp. (TGT=52091)
* Ett problem som förhindrade användning av dubblettmålgrupper i aktiviteter har korrigerats. (TGT-51200 &amp; TGT-52057)
* Korrigerade ett problem som medförde att målgruppsförbättringar och aktivitetspubliker hämtades i det uppdaterade användargränssnittet. (TGT-52158)
* Korrigerade ett problem som förhindrade att en ny aktivitet skapades på grund av användarindatafel: &quot;icke-standardarbetsyta tillåts inte för den här användaren.&quot; (TGT-52267)
* Korrigerade ett problem som förhindrade att erbjudanden visas i det uppdaterade användargränssnittet för både standardarbetsytor och icke-standardarbetsytor. [!DNL Target] visar nu erbjudanden från båda arbetsytorna. (TGT-52339)
* Ett problem har korrigerats där [!DNL Target] inte varnade kunderna när de redigerade en aktivitet och ändrade ett ändrat webbplatselement. (TGT-52100)
* Ett problem har korrigerats där ett erbjudande med ad hoc-erbjudanden skapade ett nytt erbjudande i stället för att uppdatera det befintliga. (TGT-52135)
* Korrigerat ett problem som orsakade ett ogiltigt nyttolastfel när erbjudanden flyttades till mappar. (TGT-52325)
* Korrigerat ett problem som orsakade ett användarindatafel när erbjudanden flyttades till mappar. (TGT-52296)
* Ett `audienceMetadata`-fält har lagts till för varje aktivitet och det har lästs och uppdaterats när aktiviteten redigeras. (TGT-51004)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=sv-SE) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, Versionsinformation om tidigare versioner och Experience Cloud Versionsinformation

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv-SE){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Adobe Priority-produktuppdatering](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
