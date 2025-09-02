---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 223a0f62bcd9a52bd9181e0a439e02164abbfec4
workflow-type: tm+mt
source-wordcount: '7159'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Utforska de senaste funktionerna, förbättringarna och korrigeringarna i [!DNL Adobe Target]. Versionsinformationen omfattar även uppdateringar av [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformskomponenter när det är tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Tidskänsliga uppdateringar som du behöver känna till {#time-sensitive}

[!BADGE Viktigt]{type=Informative}

För tidskänsliga uppdateringar relaterade till [!DNL Adobe Target] och din implementering innehåller [!DNL Adobe] detaljerade versionsinformation och dokumentation via [!UICONTROL Experience League]. Här är några viktiga punkter som är relevanta för implementeringen:

### [!DNL Target]-gränssnittsversion växlar borttagning

+++Se detaljer
[!DNL Target]-teamet erbjuder en tillfällig funktion som gör att du kan växla mellan det uppdaterade [!DNL Target]-användargränssnittet och den äldre versionen med en växlingsknapp. Det här alternativet är endast tillgängligt under den sista fasen av UI-utrullningen.

![Växla mellan målgränssnittsversion](/help/main/r-release-notes/assets/toggle.png)

När utrullningen är klar tas växlingsknappen bort och alla användare övergår permanent till det uppdaterade användargränssnittet. [!DNL Adobe] rekommenderar planering i förväg eftersom den här funktionen kommer att fasas ut snart.

#### Tidslinje för borttagning

På grund av nyligen identifierade problem, som främst gäller komplexa kundanpassningar, har [!DNL Target]-teamet justerat tidslinjen för borttagning:

* **17 juni 2025**: Alla IMS-organisationer har aktiverats för det uppdaterade [!DNL Target] användargränssnittet, antingen för specifika användare eller för hela organisationen, för att börja testa den nya upplevelsen.

* **30 juni 2025**: [Uppdaterat [!DNL Target] användargränssnitt](/help/main/c-intro/understand-the-target-ui.md) blev standardupplevelse för alla IMS-organisationer som har aktiverat versionsväxling för användargränssnittet.

   * Kunder som för närvarande ser det gamla användargränssnittet ser nu det uppdaterade användargränssnittet vid inloggning som standard.
   * Användargränssnittets versionsknapp är tillgänglig till och med slutet av juli, så att användare kan växla tillbaka vid behov.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] rekommenderar starkt att det uppdaterade [!DNL Target]-gränssnittet används. Växla bara tillbaka till det gamla användargränssnittet om ett problem med blockering inträffar på grund av [begränsningar i växlingsbeteendet](#limitations).

* **15 juli till 30 juli 2025**: Användargränssnittets versionsväxel inaktiveras permanent i faser. Påverkade IMS-organisationer kan inte längre återgå till det gamla användargränssnittet.

   * Undantag granskas från fall till fall.
   * Förseningar av avaktiveringen ges endast kortvarigt (några dagar) medan problem med blockering har åtgärdats.

Kontakta [Adobe kundtjänst](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) om du har några frågor eller om du förväntar dig problem under den här övergången.

#### Begränsningar för användargränssnittets växlingsbeteende {#limitations}

Följande information beskriver de begränsningar som du bör vara medveten om när du väljer att använda versionsväxlingen:

* **Synlighet för nya aktiviteter**: Aktiviteter som har skapats i det uppdaterade användargränssnittet visas inte om du växlar tillbaka till det gamla användargränssnittet.
* **Redigera befintliga aktiviteter**: Ändringar som gjorts i befintliga aktiviteter (som ursprungligen skapades i det äldre användargränssnittet) när det uppdaterade användargränssnittet används publiceras på webbplatsen. Dessa uppdateringar visas dock inte i det gamla användargränssnittet om du byter tillbaka. Där visas bara de senaste uppdateringarna från det gamla användargränssnittet.
* **Enhetlig aktivitetsinformation**: De senaste ändringarna, oavsett vilket användargränssnitt du använder, visas på din aktiva webbplats. Det gamla användargränssnittet visar dock bara de senaste ändringarna som gjorts i den versionen. Den här situationen kan orsaka förvirring om aktiviteter som redigeras i det uppdaterade användargränssnittet ser annorlunda ut än i det äldre användargränssnittet.

#### Fler resurser att lära sig om det uppdaterade användargränssnittet

* [[!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md): Här behandlas vanliga frågor om det nya [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC), inklusive navigeringsändringar, funktionsplatser och borttagning av den tillfälliga användargränssnittsversionen. Vare sig du är marknadsförare, utvecklare eller administratör kan du med de här vanliga frågorna få en smidig övergång och få ut det mesta av det uppdaterade användargränssnittet.
* Versionsinformation för [[!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Activities], [!UICONTROL Recommendations] och [!UICONTROL Visual Experience Composer] (VEC).
* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].
* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.
* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.
* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

+++

## [!DNL Target Standard/Premium] 25.8.4 (1 september 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**[!UICONTROL Activities]**

+++Se detaljer
* **Kunder kunde inte kopiera aktivitets- eller dokumentnamn från[!UICONTROL Activity Overview]**: Tidigare kunde kunderna inte kopiera namnet på en aktivitet eller det associerade erbjudandet/dokumentet direkt från [!UICONTROL Activity overview] i den uppdaterade processen för att skapa aktiviteter. Den här begränsningen påverkar användbarheten, särskilt på mindre skärmar. Kunderna kan nu enkelt kopiera både aktivitets- och dokumentnamn utan temporära lösningar. (TGT-51850)
* **Proaktiv inmatning av förvaltade [!DNL Target] kunddata när aktiviteter skapades**: Förbättrade processen för att skapa aktivitet genom att aktivera proaktiv insamling av rapporter, innehåll och skärmbilder från [!DNL Target]-kunder. Den här förbättringen åtgärdar luckor i data som identifierats i befintliga användningsfall och hjälper till att få exaktare insikter under aktiviteten och experimentera med inställningarna. (TGT-52415)
* **AP-aktiviteter hämtade inte modellfärdiga data i [!UICONTROL Reports] section**: Kunder som visar Automated Personalization-aktiviteter (AP) i [!UICONTROL Reports]-avsnittet kunde inte se modellfärdiga indikatorer på rapportgrupps- och erbjudandenivå. Problemet uppstod eftersom modellfärdiga data inte hämtades korrekt från backend-objektet. Funktionen har återställts och modellfärdiga data visas nu som förväntat. (TGT-53600 &amp; TGT-53601)
* **Aktiviteter som schemalagts för framtiden visade felaktigt statusen [!UICONTROL Live] i [!UICONTROL Activity] översikten**: Kunder observerade att aktiviteter som schemalagts att starta i framtiden felaktigt markerades som [!UICONTROL Live] i översikten [!UICONTROL Activity]. Den här statusfelmatchningen löstes och schemalagda aktiviteter visas nu korrekt som [!UICONTROL Scheduled] utan att en siduppdatering krävs. (TGT-52835)

+++

**[!UICONTROL Recommendations]**

+++Se detaljer
* **Produktlistan var inte synlig i dialogrutan [!UICONTROL View Collection]:** Tidigare kunde kunderna inte se produktlistan när de visade en samling på fliken [!UICONTROL Recommendations]. Dialogrutan [!UICONTROL View Collection] visar nu de associerade produkterna korrekt, vilket förbättrar genomskinlighet och användbarhet i det uppdaterade [!UICONTROL Recommendations]-gränssnittet. (TGT-50531)
* **Korrigerade ett problem som orsakade skiftlägeskänslig filtrering i [!UICONTROL Product Catalog Search] avancerad sökning**: Den avancerade sökfiltreringen på [!UICONTROL Product Catalog Search]-sidan ignorerar nu skiftlägeskänslighet, vilket överensstämmer med beteendet hos både backend- och GraphQL-tjänster. Denna uppdatering ger enhetliga och korrekta förslagsresultat för kunder oavsett textindrag. (TGT-53585)
* **Avancerad sökning i det uppdaterade [!UICONTROL Product Catalog Search] användargränssnittet gav inga förslag**: Kunder som använder den avancerade sökfunktionen i det uppdaterade [!UICONTROL Product Catalog Search] användargränssnittet behövde ange exakta värden med korrekt stavning eftersom inga förslag visades. Det här problemet gjorde det svårt att hitta produkter på ett effektivt sätt. Förslag visas nu som förväntat vid avancerade sökningar. (TGT-52008)
* **Vissa godkännare kunde inte visa produkter i[!UICONTROL Product Catalog Search]**: Kunder med [!UICONTROL Approver] behörighet kunde inte se några produkter i [!UICONTROL Product Catalog Search], trots att andra användare med identiska roller har åtkomst. Problemet uppstod på grund av en behörighetsinkonsekvens som påverkar katalogsynligheten. Alla godkännare kan nu visa produkter i avsnittet [!UICONTROL Recommendations] som förväntat. (TGT-53617)

+++

**[!UICONTROL Reports]**

+++Se detaljer
* **Rapporterna kunde inte läsas in för målgruppen på skrivbordet på grund av ett ogiltigt målgruppsnamnfel**: Kunderna påträffade ett GraphQL-fel när de försökte visa rapporter för en målgrupp i processen att skapa aktiviteter. Systemet returnerade meddelandet&quot;Ogiltigt målgruppsnamn: XXXXX&quot;, vilket förhindrar åtkomst till rapportdata. Rapporterna läses nu in korrekt för datormålgruppen. (TGT-53371)
* **Om du växlar målgrupper på rapportsidan uppstod fel i målgränssnittet**: Kunderna påträffade fel när de valde vissa målgrupper i avsnittet [!UICONTROL Reports]. Problemet uppstod på grund av ogiltig målgruppshantering i GraphQL-anrop, vilket resulterade i oväntade fel och saknade data. Problemet har lösts och datormålgrupperna läses nu in utan fel - även när inga data är tillgängliga. (TGT-53370)
* **[!UICONTROL Graph view]i avsnittet [!UICONTROL Reports] visade inga värden från[!DNL Analytics]**: Kunder som använder [!UICONTROL Graph view] i avsnittet om eportar påträffade saknade data, och alla värden visade sig vara noll. Problemet orsakades av felaktig datahämtning från [!UICONTROL Analytics]. [!UICONTROL Graph view] visar nu exakta värden som förväntat. (TGT-52792)
+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Se detaljer
* **Det gick inte att klicka på Acceptera cookies med [!UICONTROL Enhanced Experience Composer] (EEC) eftersom en funktion saknas**: Kunder rapporterade att försök att acceptera cookies via EEC resulterade i ett konsolfel: `handleclickAcceptAllButton is not defined`. Funktionen för godkännande av cookies fungerar nu som förväntat och ger en smidigare upplevelse när aktiviteter skapas i det uppdaterade användargränssnittet. (TGT-52794)
* **Det nya EEG-gränssnittet kunde inte läsa in vissa sidor som tidigare hade stöd i det gamla användargränssnittet**: Kunder rapporterade att det nya EEG-gränssnittet inte kunde läsa in vissa sidor som var tillgängliga i det gamla användargränssnittet trots att det fanns kod för iframe-busting på webbplatsen. Den uppdaterade processen för att skapa aktivitet har nu stöd för inläsning av dessa sidor och återställer kompatibilitet för arbetsflöden som skapar aktiviteter. (TGT-53061)
* **VEC visade en tom vita skärm när upplevelser redigerades**: Kunder från en viss klientorganisation rapporterade att VEC-skärmen blev tom när de försökte redigera upplevelser i den uppdaterade VEC-webbplatsen. Problemet påverkade både nyskapade och äldre aktiviteter och förhindrar kontinuitet i arbetsflödet. VEC läses nu in korrekt, vilket gör att kunderna kan redigera upplevelser utan avbrott. (TGT-53547)
* **VEC kraschade och visade en tom skärm vid inläsning av vissa aktiviteter**: Kunder från en viss klientorganisation rapporterade att VEC inte kunde läsa in specifika aktiviteter. Experience Editor fastnade fortfarande i&quot;Använda initiala ändringar&quot; innan det kraschade och en tom skärm visades. Konsolfel indikerade ett fel vid läsning av odefinierade egenskaper. Redigeraren läser nu in de aktiviteter som påverkas utan fel i den uppdaterade VEC:n. (TGT-53548)
* **Om alla datumvärden rensades med Backsteg kraschade sidan**: Kundernas schemaläggningsaktiviteter i avsnittet [!UICONTROL Goals & Settings] kraschade när Backsteg användes för att rensa alla värden från fälten [!UICONTROL Specified Date & Time]. Problemet orsakades av ett null-referensfel i datumhanteringslogiken. Sidan hanterar nu tomma datuminmatningar utan att krascha. (TGT-53624)
* **Inga produkter visades i [!UICONTROL Product Catalog Search] på grund av en ogiltig nyttolast**: Kunder som öppnar avsnittet [!UICONTROL Recommendations] i [!UICONTROL Product Catalog Search] påträffade tomma resultat som orsakats av en ogiltig GraphQL-nyttolast. Det här serverdelsfelet förhindrade att produktdata lästes in korrekt. Produkterna visas nu som förväntat i det uppdaterade användargränssnittet. (TGT-53630)
* **[!DNL Scene7]bilder sparades med lägre upplösning i den uppdaterade VEC**: Kunder som redigerar upplevelser i den uppdaterade VEC märkte att [!UICONTROL Scene7] bild-URL:er sparades utan upplösningsparametrar, vilket resulterade i att bilder med låg kvalitet levererades (400 × 400 istället för de avsedda 800 × 800). Bild-URL:er behåller nu rätt parametrar för att säkerställa rätt upplösning. (TGT-52631)
* **live-aktiviteter kunde fortfarande redigeras i VEC**: Kunderna kunde komma åt redigeringsalternativ för live-aktiviteter i den uppdaterade VEC:n, vilket kunde leda till oavsiktliga ändringar. Problemet har åtgärdats genom att inaktivera redigeringsfunktionen för aktiva aktiviteter. Redigeringsknapparna är nu dolda i aktivitetslistan och översikten för redigerare, medan godkännare och andra roller inte påverkas. (TGT-53055)
* **Avbröt avsnittet [!UICONTROL Failed] och [!UICONTROL Draft] aktiviteter i det uppdaterade VEC**: Alternativen [!UICONTROL Failed] och [!UICONTROL Draft] aktiviteter har tagits bort från det uppdaterade VEC:t. Det nya användargränssnittet stöder inte längre utkastlägen och misslyckade kampanjer lagras inte i serverdelen. Dessa alternativ är inte längre relevanta. Relaterade filter och backend-fält (till exempel `uiSyncFailed`, `errorMessage`) har också tagits bort för att effektivisera aktivitetshanteringen. (TGT-53150)
* **Det går inte att logga in på VEC för en aktivitet**: Kunder som försöker logga in på sin webbplats via VEC omdirigerades upprepade gånger till inloggningssidan, vilket förhindrar åtkomst till aktivitetsredigering. Detta problem kunde inte reproduceras internt och kan ha relaterats till sessionshantering på plats. Inloggningsflödet har stabiliserats och kunderna kan nu komma åt VEC utan omdirigeringsfel. (TGT-53524)
* **Om du dubbeltryckte på bakåtknappen i [!UICONTROL Browse] -läge kraschade VEC**: Kunder som navigerade i [!UICONTROL Browse]-läget i VEC upplevde krascher när de tryckte på webbläsarens bakåtknapp två gånger. Det här problemet gjorde att redigeraren låstes och krävde en uppdatering av sidan. Redigeraren hanterar nu navigeringen på ett tillförlitligt sätt utan att krascha. (GT-53568)
* **Det gick inte att redigera aktiviteter på grund av odefinierade platsmappningar**: Kunderna påträffade ett fel när de försökte redigera aktiviteter, som orsakas av odefinierade plats-ID:n i logiken `LocationMapping.behaviorTargetedActivity`. Problemet resulterade i ett 400-fel och blockerade aktivitetsuppdateringar. Aktiviteter kan nu redigeras utan platsrelaterade valideringsfel. (TGT-53607)
* **När aktiviteter sparades utlöstes ett ogiltigt användarindatafel**: Kunderna påträffade ett ogiltigt användarindatafel när de försökte spara aktiviteter efter att ha gjort mindre ändringar i den uppdaterade VEC:n. Felet orsakades av felmatchade platsmappningar i serverdelens valideringslogik. Det går nu att spara aktiviteter utan att utlösa platsrelaterade fel. (TGT-53603)

+++

## [!DNL Target Standard/Premium] 25.8.3 (21 augusti 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**[!UICONTROL Activities]**

+++Se detaljer
* **Ett problem har korrigerats där sparande aktiviteter utlöste ett ogiltigt användarindatafel på grund av felaktiga egenskapsdata**: Kunderna påträffade ett kritiskt fel när de försökte spara befintliga aktiviteter. Felmeddelandet indikerade ogiltiga användarindata, som specifikt refererar till ett okänt egenskapsnamninnehåll i JSON-nyttolasten. Nya aktiviteter som använder samma egenskap sparades, vilket tyder på att problemet isolerades till äldre aktivitetsdata. Processen för att skapa aktivitet hanterar nu äldre egenskapskonfigurationer korrekt, vilket förhindrar ogiltiga indatafel och säkerställer konsekvent sparfunktion för nya och befintliga aktiviteter. (TGT-53507)
* **Ett fel som gjorde att kunderna inte kunde spara en aktivitet på grund av felet InvalidProperty.Json** har korrigerats: Kunderna påträffade ett fel när de försökte spara en aktivitet i det uppdaterade användargränssnittet, även utan att göra några ändringar. Felmeddelandet visade en ogiltig JSON-struktur: &quot;Ogiltig Json. Okänt egenskapsnamn &#39;content&#39;. Plats: rad - 1, kolumn - 432.&quot; Problemet orsakades av en okänd egenskap i nyttolasten för begäran och har nu lösts. Kunder kan spara aktiviteter utan att det här felet uppstår. (TGT-53513)
* **Korrigerade ett fel där schemalagda aktiviteter felaktigt visade statusen [!UICONTROL Live] tills sidan uppdaterades**: Kunder observerade att när de schemalägger en aktivitet att publiceras vid ett framtida datum och en framtida tidpunkt visades statusen omedelbart som [!UICONTROL Live] i stället för [!UICONTROL Scheduled]. Detta orsakade förvirring även om bekräftelsemeddelandet korrekt indikerade att aktiviteten schemalagdes. Om du uppdaterar sidan har statusvisningen korrigerats. Problemet har nu lösts och schemalagda aktiviteter visar korrekt schemalagd status utan att en uppdatering krävs. (TGT-52937)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++Se detaljer
* **Ett problem har korrigerats där kunder inte kunde skriva rapportsvitnamn under processen för att skapa aktivitet**: Kunder som använder [!DNL Adobe Analytics] som rapportkälla under processen för att skapa aktivitet kunde inte skriva i listrutan [!UICONTROL Report Suite] för att söka efter specifika rapportsviter. Detta påverkade arbetsflödena för organisationer med ett stort antal rapportsviter, där manuell bläddring försenade konfigurationen avsevärt. Listrutan sorterades inte i bokstavsordning och svarade inte konsekvent på inmatningar, vilket gjorde det svårt att hitta rapportsviter som &quot;Office + Store - Webb - Produkt&quot;. Problemet har åtgärdats och kunderna kan nu söka effektivt genom att skriva namnen på rapportsviterna. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Se detaljer
* **Korrigerade ett problem där målgrupper som gått ut med tidsram blockerade aktivitetssparande även efter borttagning**: Kunderna kunde inte spara aktiviteter i det uppdaterade användargränssnittet på grund av ett fel relaterat till utgångna målgrupper med tidsram. Felmeddelandet kvarstår även efter att den berörda publiken har tagits bort: &quot;Aktiviteten innehåller publik med ogiltig tidsram.&quot; Problemet uppstod eftersom systemet fortsatte att validera målgruppen med endast aktivitet, även när det inte längre användes. Beteendet komplicerades ytterligare av tidszonsavvikelser. Valideringslogiken har korrigerats och kunderna kan nu spara aktiviteter utan att detta fel uppstår. (TGT-53517)

+++

**[!UICONTROL Experience Fragment]s**

+++Se detaljer
* **Korrigerade ett fel som förhindrade kunder från att infoga Experience Fragments med [!UICONTROL Insert Before] eller [!UICONTROL Insert After] i användargränssnittet**. Ett fel uppstod när kunder försökte infoga [!UICONTROL Experience Fragments] i en aktivitet med hjälp av alternativen Infoga före eller Infoga efter i det uppdaterade användargränssnittet. Felmeddelandet som visades var:&quot;Erbjudandeinnehåll måste innehålla exakt ett HTML-element.&quot; Problemet var specifikt för det uppdaterade användargränssnittet och uppstod inte i den tidigare versionen. Problemet har nu lösts och kunderna kan infoga [!UICONTROL Experience Fragments] utan att detta fel uppstår. (TGT-53442)

+++

**[!UICONTROL Offer decisions]**

+++Se detaljer
* **Ett problem som hindrade kunder från att redigera beslutserbjudanden och välja specifika sidelement i det uppdaterade användargränssnittet** har korrigerats: I den uppdaterade processen för att skapa aktiviteter kunde kunderna inte redigera befintliga beslutserbjudanden eller välja specifika sidelement i Visual Experience Composer (VEC). Beslutserbjudandena visades felaktigt som erbjudanden från HTML och de ändringar som gjordes under redigeringen sparades inte. Dessutom gick det inte att läsa in vissa regionala URL:er, till exempel den japanska webbplatsen, korrekt i VEC, vilket blockerar skapande och uppdatering av aktiviteter. Besluten visas nu korrekt, sidelementen kan markeras som förväntat och regionala URL:er läses in korrekt i VEC, vilket återställer redigeringsfunktionerna. (TGT-53425)
* **Ett problem har korrigerats där [!UICONTROL Offer Decision] väljare inte kunde ändras och ändras oväntat efter att** sparats: I den uppdaterade processen för att skapa aktivitet kunde kunderna inte ändra [!UICONTROL Offer Decision]-väljaren som det var tänkt. Försöken att ändra väljaren misslyckades och väljaren återgick till ett felaktigt värde efter att den sparats. Detta beteende gjorde att beslutserbjudandet försvann från Visual Experience Composer (VEC), vilket blockerade ytterligare redigeringar. Ändringarna av väljaren bevaras nu korrekt, och beslutserbjudandena förblir synliga och redigerbara i VEC när de har sparats.(TGT-53433)
* **Korrigerade ett fel där [!UICONTROL Offer Decisions] försvann från aktiviteten efter att** sparats: [!UICONTROL Offer Decisions] som lades till under processen för att skapa aktivitet sparades inte efter att aktiviteten sparats och öppnats igen. Det här problemet uppstod när dynamiskt innehåll redigerades och [!UICONTROL Offer Decisions] infogades med specifika väljare och egenskaper. [!UICONTROL Offer Decisions] bevaras nu korrekt efter att du har sparat och väljarna förblir intakta, vilket garanterar konsekvent målinriktning och redigeringsbeteende. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Se detaljer
* **Ett problem i [!DNL Recommendations]-gränssnittet där CSV-hämtning med anpassade villkor returnerade 404-fel** har korrigerats där kunderna inte kunde hämta CSV-filen med anpassade villkor i processen för att skapa aktiviteter. Hämtningslänken fungerar nu korrekt, så att kunderna kan exportera anpassade villkor som förväntat. (TGT-51966)
* **Inkonsekvent inläsning av bilder i[!UICONTROL Catalog Search]** har korrigerats: Ett problem där miniatyrbilder och bilder i [!UICONTROL  Catalog Search] inte lästes in konsekvent i processen där aktiviteten skapades har åtgärdats. Det gick inte att visa bilder om inte kolumnen &quot;Miniatyrbilds-URL&quot; var synlig och vissa produktbilder lästes in delvis eller inte alls efter navigerings- eller sökåtgärder. Bildinläsningsbeteendet har stabiliserats och miniatyrerna visas nu tillförlitligt oavsett om kolumnerna visas eller navigeras. (TGT-52778)
* **Ett problem har korrigerats där redigering av en rekommendation i en duplicerad upplevelse påverkade den ursprungliga upplevelsen**: Kunderna rapporterade att en rekommendation i en duplicerad upplevelse oavsiktligt ändrade den ursprungliga upplevelsen. I synnerhet efter att ha duplicerat Experience B i processen för att skapa aktiviteter och redigerat dess design eller kriterier, återspeglades samma ändringar i den ursprungliga Experience B, trots att de var separata enheter. Dubblerade upplevelser behåller nu separata konfigurationer, vilket säkerställer att redigeringar av en upplevelse inte påverkar originalet. (TGT-53369)
* **Ett problem har korrigerats där ändringar i en dubblerad upplevelse oavsiktligt påverkade den ursprungliga upplevelsen i en aktivitet**: Kunderna rapporterade att när de duplicerade en upplevelse i en aktivitet och tilldelar en ny publik, speglades även ändringar i den duplicerade upplevelsens design eller kriterier i den ursprungliga upplevelsen. Problemet uppstod trots att inga ändringar gjordes direkt i den ursprungliga versionen, vilket påverkade möjligheten att skapa oberoende variationer inom samma aktivitet. Processen för att skapa aktivitet isolerar nu duplicerade upplevelser korrekt och ser till att ändringar som görs i en upplevelse inte påverkar originalet. (TGT-53361)
* **Korrigerade ett fel där [!UICONTROL Recommendation Catalog] ibland inte kunde visa fullständiga produktattributdata**: I det uppdaterade [!DNL Recommendations] användargränssnittet uppstod ett problem där vissa produktattribut, som meddelande, inte visades konsekvent i [!UICONTROL Catalog Search]-resultaten, trots att data fanns i feeden. Det här problemet innebar att kunderna måste konfigurera om kolumnsynligheten manuellt för att kunna hämta de värden som saknas. [!UICONTROL Catalog Search] visar nu alla konfigurerade attribut på ett tillförlitligt sätt, vilket eliminerar behovet av manuella kolumnåterställningar. (TGT-52769)
* **Korrigerade ett problem där [!UICONTROL Front Promotion] inte kunde inaktiveras i en aktiv aktivitet**: Försök att inaktivera [!UICONTROL Front Promotion] i en aktiv aktivitet sparades inte. När du har markerat [!UICONTROL Change Promotion] och inaktiverat den förblev kampanjen aktiv när aktiviteten redigerades om, vilket förhindrar uppdateringar av rekommendationskonfigurationer. Kampanjinställningarna sparas nu korrekt så att kunderna kan inaktivera eller ändra kampanjer i aktiva aktiviteter som förväntat. (TGT-53231)
* **Ett problem har korrigerats där aktiveringen av [!DNL Recommendations] [!UICONTROL Promotion] utan data utlöste ett oklart felmeddelande**: Om du aktiverar [!UICONTROL Front] eller [!UICONTROL Back Promotion] i en [!DNL Recommendations]-aktivitet utan att ange obligatoriska värden, resulterade det i ett allmänt meddelande om&quot;Ogiltigt indatafel&quot;. Det underliggande problemet var ett saknat konfigurationsfält, men felmeddelandet visade inte orsaken, vilket gjorde felsökningen svår. Processen för att skapa aktivitet ger nu ett tydligt och åtgärdbart felmeddelande när obligatoriska fält, som `collectionId` eller regler, saknas, vilket hjälper kunderna att snabbt identifiera och lösa konfigurationsproblem. (TGT-52616)
* **Korrigerade ett fel som förhindrade att listan [!UICONTROL Product] visades i [!UICONTROL Edit] modal på fliken [!UICONTROL Recommendations]**: Kunderna kunde inte visa den filtrerade produktlistan när de redigerade en [!UICONTROL collection] eller [!UICONTROL exclusion] på fliken [!UICONTROL Recommendations]. Listan förväntades uppdateras i realtid baserat på tillämpade regler, men den såg inte ut som den var tänkt. Problemet har åtgärdats och produktlistan visas nu korrekt och uppdateras dynamiskt när reglerna ändras. (TGT-53481)
* **Ett problem med layouten i dialogrutan Visa detaljer i det uppdaterade användargränssnittet** har korrigerats: Layouten för spärrning av vydetaljer i det uppdaterade användargränssnittet har ändrats för att förbättra tydligheten och användbarheten. Dialogrutan innehåller nu två flikar:
   * Fliken [!UICONTROL Details]: Visar all relevant information för det markerade objektet.
   * Fliken [!UICONTROL Inventory]: Visar alla produkter som filtrerats enligt de aktuella reglerna för samling och undantag.

  Den här förbättringen gör det enklare för kunderna att navigera och förstå artikelspecifika data och lagersammanhang i aktivitetsskapandeprocessen. (TGT-53503)

   * **Korrigerade ett problem där borttagna erbjudanden i rekommendationsaktiviteter återkom efter att ha sparat**: Kunder rapporterade att när [!UICONTROL front] eller [!UICONTROL back] erbjudanden togs bort från [!DNL Recommendations] aktiviteter och aktiviteten sparades, fortsatte kampanjerna att visas när de öppnades igen. Problemet uppstod både i staging- och produktionsmiljöer och påverkade den uppdaterade processen att skapa aktivitet. Problemet har lösts. Kampanjer som tas bort från en aktivitet bevaras nu korrekt när de har sparats. (TGT-53490)

+++

**Rapporter**

+++Se detaljer
* **Ett problem har korrigerats där [!UICONTROL Automated Segments]-rapporten visade null-målgruppsvärden**: Kunderna rapporterade att [!UICONTROL Automated Segments] i aktivitetsrapporter visade null för målgruppsdata, vilket förhindrar en korrekt analys av segmentets prestanda. Det här problemet uppstod vid åtkomst till avsnittet [!UICONTROL Reports] och val av [!UICONTROL Automated Segments], även om giltiga målgruppsdata förväntades. [!UICONTROL Automated Segments] visar nu målgruppsvärden korrekt, vilket ger tillförlitliga rapporter och segmenteringsinsikter. (TGT-52793)

+++

**Single Page Applications (SPA)**

+++Se detaljer
* **Korrigerade ett problem där växling mellan [!UICONTROL Browse] - och [!UICONTROL Design]-lägen återställde SPA-läget i det uppdaterade användargränssnittet**: Kunder rapporterade att växling mellan [!UICONTROL Browse] - och [!UICONTROL Design] -lägen i det uppdaterade användargränssnittet gjorde att webbredigeraren lästes in igen och att SPA-lägena återställdes. Detta störde arbetsflödena och krävde att kunderna skrev in informationen igen. Problemet har lösts. SPA-läget bevaras nu när du växlar mellan lägen, vilket ger en jämnare och mer konsekvent upplevelse när du skapar aktiviteter. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Se detaljer
* **Ett problem har korrigerats i processen för att skapa aktivitet som blockerade progression till [!UICONTROL Targeting]-steget i AP-aktiviteter**: Ett fel i processen för att skapa aktivitet där kunderna inte kunde fortsätta till [!UICONTROL Targeting]-steget i [!UICONTROL Automated Personalization]-aktiviteter (AP) har korrigerats om inte två platser lades till. Detta beteende skilde sig från den tidigare upplevelsen, där en enda plats med flera erbjudanden var tillräckligt. Kravet har korrigerats, vilket gör att kunderna kan fortsätta använda inställningar för en plats som en del av sina AP-arbetsflöden. (TGT-53426)
* **Ett problem har korrigerats där den nya processen för att skapa aktivitet inte angav parametern fmt=png-alpha för genomskinliga bilder**: I det uppdaterade användargränssnittet ingick parametern `fmt=png-alpha` inte längre i bilder som infogades under processen för att skapa aktivitet. Detta resulterar i att genomskinligheten går förlorad. Det här beteendet skiljer sig från det tidigare användargränssnittet, som automatiskt lägger till parametern i bild-URL:er och bevarar genomskinliga bakgrunder. Processen för att skapa aktivitet använder nu parametern `fmt=png-alpha` korrekt på bild-URL:er när genomskinlighet krävs, vilket ger en konsekvent återgivning av genomskinliga resurser. (TGT-52615)
* **Korrigerade ett problem som hindrade kunder från att söka efter rapportsviter i det uppdaterade användargränssnittet**: i det uppdaterade användargränssnittet tillät inte listrutan [!UICONTROL Report Suites] i avsnittet [!UICONTROL Goals & Settings] kunderna att skriva och söka, vilket gjorde det svårt att hitta specifika rapportsviter, särskilt för klientorganisationer med ett stort antal poster. Till skillnad från det tidigare användargränssnittet sorterades inte listan och ingen indatabaserad filtrering saknades. Problemet har åtgärdats. Kunder kan nu skriva för att söka efter och filtrera rapportsviter och återställa de funktioner som finns i det gamla användargränssnittet. (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++Se detaljer
* **Ett problem har korrigerats där en kund som är begränsad till en enda arbetsyta kunde visa aktiviteter från andra arbetsytor**: Kunder med begränsad åtkomst till en arbetsyta kunde oväntat visa aktiviteter över alla arbetsytor när de valde [!UICONTROL All Workspaces] i processen för att skapa aktiviteter. Detta innebar en risk för oavsiktliga ändringar i andra arbetsytor, vilket kan påverka webbplatsens prestanda. Åtkomstkontrollerna i Workspace har förbättrats för att säkerställa att kunderna bara kan visa och interagera med aktiviteter på sin tilldelade arbetsyta. (TGT-53101)
* **Korrigerade ett problem där en kund kunde visa aktiviteter från [!UICONTROL Default Workspace] utan åtkomst:** En kund med begränsad åtkomst till arbetsytan för mellanlagring kunde visa aktiviteter från [!UICONTROL Default Workspace] via processen för att skapa aktiviteter. Detta beteende inträffade trots korrekt serverdelskonfiguration och åtkomsträttigheter. Åtkomstkontrollerna i Workspace har förbättrats för att säkerställa att kunderna bara kan visa aktiviteter på sin tilldelade arbetsyta.(TGT-53297)

+++

## [!DNL Target Standard/Premium] 25.8.2 (14 augusti 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

**[!UICONTROL Activities]**

+++Se detaljer
* **Ett problem med aktivitetsinläsning i det uppdaterade [!DNL Target] användargränssnittet** har korrigerats i det uppdaterade användargränssnittet i [!DNL Target] där vissa aktiviteter inte kunde läsas in vid redigering. Det här problemet gjorde att kunderna lämnade användarna på en obegränsad inläsningsskärm. Problemet påverkade flera aktiviteter och rapporterades inträffa inkonsekvent mellan olika kunder. Med den här korrigeringen läses de påverkade aktiviteterna in korrekt, vilket ger smidig redigering och minskar störningarna i aktivitetsarbetsflödena. (TGT-53209)
* **Ett fel vid sparande i aktivitetsskapandeprocessen på grund av `optionLocalId` validering** har korrigerats: Ett fel i aktivitetsskapandeprocessen som gjorde att kunder inte kunde spara ändringar på grund av ett serverdelsvalideringsfel har korrigerats: `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` Detta problem uppstod när specifika element i en aktivitet ändrades, vilket resulterade i en misslyckad sparningsåtgärd. Korrigeringen ser till att `optionLocalId`-referenser nu valideras korrekt, vilket gör att kunder kan spara aktiviteter utan att detta fel påträffas. (TGT-53293)
* **Korrigerad krasch i process för att skapa aktivitet på grund av ogiltiga alternativreferenser vid växling av sidor**: Korrigerade ett fel i processen för att skapa aktivitet som gjorde att användargränssnittet kraschade efter växling av sidor tre gånger under redigering. Kraschen utlöstes av ogiltiga alternativreferenser, vilket resulterade i konsolfel som &quot;Option with localId &#39;7&#39; not found.&quot; Med den här uppdateringen kan kunderna nu växla mellan sidor och tillämpa ändringar utan att stöta på systemfel eller avbrott. (TGT-53295)
* **Ett fel vid sparande i aktivitetsskapandeprocessen som orsakades av ogiltig användarinmatning vid redigering av upplevelser** har korrigerats i aktivitetsskapandeprocessen där kunderna inte kunde spara ändringar i en aktivitet på grund av ett ogiltigt användarinmatningsfel. Felet uppstod när upplevelser i det uppdaterade användargränssnittet ändrades, vilket förhindrar att uppdateringar implementeras. Aktiviteten kan nu sparas utan avbrott så att kunderna kan redigera och publicera. (TGT-53267)
* **Ett inläsningsproblem i en aktivitetsskapandeprocess som blockerade redigering i det uppdaterade användargränssnittet** har korrigerats: ett fel i aktivitetsskapandeprocessen där kunderna inte kunde redigera aktiviteter i det uppdaterade användargränssnittet på grund av en kontinuerlig inläsningsskärm har åtgärdats. Kunder kan nu öppna och ändra aktiviteter utan att stöta på inläsningsfel. (TGT-53415)
* **Kravet på åtgärdad upplevelse i processen för att skapa aktivitet för AP-aktiviteter i det uppdaterade användargränssnittet**: Korrigerade ett fel i processen för att skapa aktivitet där [!UICONTROL Automated Personalization] (AP)-aktiviteter krävde två platser i stället för två upplevelser i det uppdaterade användargränssnittet. Detta beteende blockerade användningsfall där kunderna konfigurerade en enda plats med flera erbjudanden, som tidigare stöddes. Kravet har korrigerats så att det matchar den ursprungliga funktionen, vilket gör att kunderna kan fortsätta med AP-aktiviteter med två upplevelser oavsett antalet platser. (TGT-53429)
* **Spårat elementfältbeteende i läget Klickspår har korrigerats för att förhindra osparade indata och för att förbättra klarheten**: Korrigerat ett problem i processen där fältet [!UICONTROL Tracked Element] i läget [!DNL Click Track] kunde redigeras men det angivna namnet inte kunde sparas, vilket orsakade förvirring för kunderna. Fältet är nu inaktiverat för att förhindra indata som inte har sparats, och namngivningen av valda element har klargjorts för att förbättra målkonfigurationen och spårningskvaliteten.** (TGT-53458)
* **Ett problem har korrigerats i aktivitetsskapandeprocessen som blockerade namngivning av spårade komponenter i [!UICONTROL Click Track] mode**: Korrigerade ett fel i aktivitetsskapandeprocessen där kunderna inte kunde namnge spårade komponenter i [!UICONTROL Click Track]-läge. När du angett ett namn verkade fältet redigerbart, men innehöll inte indata. Som standard används generiska etiketter som &quot;MY PRIMARY GOAL 0&quot; i redigeringsläge. Det spårade elementfältet är nu inaktiverat och namnbeteendet har klargjorts för att förbättra målkonfigurationen och spårningsnoggrannheten. (TGT-51396)

+++

**Upplevelsefragment (XF)**

+++Se detaljer
* **Ett problem har korrigerats i aktivitetsskapandeprocessen som tillät oavsiktlig HTML-redigering av AEM-exporterade fragment**: Korrigerade ett fel i aktivitetsskapandeprocessen som gjorde att kunder kunde redigera HTML för [!DNL Experience Fragments] (XF) som exporterades från [!DNL Adobe Experience Manager] (AEM) i [!DNL Target]. Detta beteende var oavsiktligt eftersom XF:er ska förbli låsta för redigering när de har publicerats från AEM. Korrigeringen ser till att alternativet&quot;Redigera HTML&quot; inte längre är tillgängligt för AEM-exporterade fragment, vilket bevarar innehållets integritet och förväntade styrning. (TGT-53286)
* **Ett intermittent förhandsgranskningsproblem för XF-innehåll i aktivitetsskapandeprocessen i det uppdaterade användargränssnittet har korrigerats**: Ett fel i aktivitetsskapandeprocessen där XF-innehåll ibland inte kunde återges i förhandsgranskningsläge i det uppdaterade användargränssnittet har korrigerats. Även om innehållet levererades korrekt visades inte förhandsgranskningen konsekvent, vilket gjorde det svårt för kunderna att validera konfigurationen av erbjudandet. XF-förhandsgranskningar läses nu in tillförlitligt, vilket ökar förtroendet och effektiviteten under aktivitetskonfigurationen. (TGT-53318)

+++

**QA-läge**

+++Se detaljer
* **Korrigerat problem i aktivitetsskapandeprocessen där inledande mellanslag i URL:er orsakade brutna QA-länkar**: Korrigerade ett fel i aktivitetsskapandeprocessen där inledande mellanslag i aktivitets-URL:en inte trimmades korrekt när de sparades. Detta orsakade ogiltiga QA-länkar och felaktig formatering i serverdelen. Efter uppdateringen sparas URL:er nu korrekt, vilket förhindrar brutna länkar och förbättrar tillförlitligheten i QA-arbetsflöden för kunder. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Se detaljer
* **Korrigerat problem i katalogsökgränssnittet där avancerad sökning inte gav några förslag**: Korrigerade ett fel i det nya [!UICONTROL Catalog Search]-gränssnittet där [!UICONTROL Advanced Search]-funktionen inte gav några förslag. Användarna måste ange exakta värden med exakt stavning, vilket gör sökningen krånglig och felbenägen. Med den här korrigeringen ger [!UICONTROL Advanced Search] nu relevanta förslag när användare skriver, vilket förbättrar användbarheten och minskar friktionen vid sökning av produkter. (TGT-52008)
* **Flera användargränssnittsproblem och filtreringsproblem har åtgärdats för att förbättra svarstiderna och entitetsinteraktionen**: Flera problem har åtgärdats, bl.a. bristande svarstider för villkorsinformation på enheter med liten skärm, brist på resultat när du valde Alla värdgrupper i miljöfiltret samt oförmåga att interagera med entiteter som inte har något namn. Dessa korrigeringar förbättrar användbarheten i olika skärmstorlekar, säkerställer korrekt filtrering och möjliggör fullständig interaktion med alla produktenheter, vilket förbättrar den övergripande upplevelsen för användarna. (TGT-52992)
* **Saknade produkt-ID:n i vyn Rekommendationer har korrigerats när aktiviteten skapades**: Ett problem i [!DNL Recommendations]-processen där produkt-ID:n saknades i skärmen med produktinformation har korrigerats, vilket gör det svårt för kunder att kopiera eller referera till produkt-ID:n under arbetsflöden. Produkt-ID:n visas nu tydligt i detaljvyn, vilket ger bättre synlighet och stöd för effektivare produkthantering för kunder. (TGT-51964)
* **Ett problem har korrigerats i aktivitetsskapandeprocessen där produktmeddelanden inte kunde visas i rekommendationsvyn**: Korrigerade ett fel i aktivitetsskapandeprocessen där [!UICONTROL Message] -kolumnen i [!DNL Recommendations]-vyn inte visade produktdata trots att meddelanden fanns. Kunderna var tvungna att ta bort kolumnen manuellt och lägga till den på nytt för att tillfälligt visa innehållet, som ofta skulle försvinna igen vid bläddring eller sökning. Den här uppdateringen återställer konsekvent synlighet för produktmeddelanden, vilket förbättrar katalognavigering och arbetsflöden för granskning. (TGT-52777)
* **Ett problem i aktivitetsskapandeprocessen där alternativet Alla värdgrupper returnerades inga resultat i rekommendationsvyn** har korrigerats i aktivitetsskapandeprocessen där det inte gick att få några resultat när miljön Alla värdgrupper valdes i vyn [!DNL Recommendations]. Kunderna kan nu visa produktdata i alla värdgrupper som förväntat, vilket förbättrar synligheten och filtreringsnoggrannheten under aktivitetsinställningarna. (TGT-53006)
* **Ett problem i aktivitetsskapandeprocessen där växling mellan framhävning inte kvarstod efter att** sparats har korrigerats: Ett fel i aktivitetsskapandeprocessen där inaktiveringen av växling mellan framhävning och aktivitetsinställningar inte kvarstod efter att aktivitetsinställningarna sparats har åtgärdats. Kunder som försökte ta bort frontkampanjen återaktiverades när aktiviteten granskades, vilket förhindrade en korrekt anpassning. Med den här uppdateringen kan ändringar sparas på ett tillförlitligt sätt, vilket ger kunderna full kontroll över kampanjinställningarna. (TGT-53215)
* **En inkonsekvent sortering efter [!UICONTROL Last Updated] kolumn:** har korrigerats i aktivitetsskapandeprocessen där sortering av katalogen efter [!UICONTROL Last updated]-kolumnen gav inkonsekventa resultat. Kunderna kunde inte på ett tillförlitligt sätt organisera produktdata baserat på tidsstämplar för uppdateringar, vilket försvårade granskning och hantering av kataloger. Nu fungerar sorteringen som förväntat, vilket förbättrar noggrannheten och användbarheten i det uppdaterade användargränssnittet. (TGT-53116)

+++

**Visual Experience Composer (VEC)**

+++Se detaljer
* **Åtgärdad inläsning av aktivitet och [!UICONTROL Cancel] knappproblem i process för att skapa aktivitet**: Korrigerade ett fel i processen för att skapa aktivitet där vissa aktiviteter inte kunde läsas in, vilket medförde att kunderna inte kunde komma åt ändringarna. Dessutom svarade inte knappen [!UICONTROL Cancel], vilket förhindrar kunder från att stoppa inläsningen eller avsluta redigeringsvyn. Med den här korrigeringen kan du nu läsa in aktiviteter tillförlitligt och knappen [!UICONTROL Cancel] fungerar som förväntat, vilket förbättrar den övergripande stabiliteten och användarupplevelsen i Visual Experience Composer. (VEC)(TGT-53218)
* **Ett problem med växling av upplevelser i det uppdaterade VEC-gränssnittet som blockerade redigering och inaktiverade [!UICONTROL Cancel] button** har åtgärdats i det uppdaterade VEC-gränssnittet där ändringar inte lästes in när de växlade mellan upplevelser i en XT-aktivitet (Experience Targeting). Kunderna kunde inte redigera upplevelser utöver den som de ursprungligen angav, och knappen [!UICONTROL Cancel] saknades eller svarade inte. Den här korrigeringen ser till att ändringar nu läses in korrekt i alla upplevelser och att knappen [!UICONTROL Cancel] fungerar tillförlitligt, även utan tillägget Helper, vilket förbättrar redigeringsarbetsflödena och minskar frustrationen. (TGT-53256)
* **Ett problem med vita skärmar när du växlade mellan flera upplevelser i en process som skapats med aktivitet har åtgärdats**: Ett problem där växling mellan olika upplevelser orsakade en vita skärm har korrigerats. Dessutom har ett problem korrigerats i processen där kunderna skapade en vitskärm när de försökte ändra flera upplevelser i en aktivitet. Detta problem uppstod efter att ändringar gjorts i två upplevelser och sedan valt en tredje upplevelse, vilket förhindrar ytterligare redigeringar. Uppdateringen säkerställer smidiga övergångar mellan upplevelserna, så att kunderna kan göra ändringar utan avbrott. (TGT-53266)
* **Ett problem har korrigerats i VEC där anpassade kodändringar inte sparades på ett tillförlitligt sätt under redigeringssessioner**: Ett problem har korrigerats där anpassade kodändringar som gjorts i VEC (Visual Experience Composer) inte sparades på ett tillförlitligt sätt i ett enda försök. Kunder rapporterade att ändringar, som formatuppdateringar eller HTML-redigering, ibland saknades på webbplatsen och i QA-URL:er, även efter att ha använt både [!UICONTROL Edit Content]- och [!UICONTROL Save]-knapparna. Den här regressionen har åtgärdats och säkerställer att alla anpassade kodändringar bevaras som förväntat mellan redigeringssessionerna.** (TGT-53418)
* **Korrigerade saknad `triggerViews` i uppdaterat användargränssnitt när aktiviteten skapades**: Korrigerade ett fel i aktivitetsskapandeprocessen där `triggerViews` inte visades i det uppdaterade användargränssnittet, trots att de implementerades korrekt på sidan. Detta påverkade flera kunder och gjorde det svårt att validera vybaserade utlösare under aktivitetsinställningarna. `TriggerViews` visas nu som förväntat, vilket gör att kunderna kan slutföra och testa sina konfigurationer på ett tillförlitligt sätt. (TGT-53239)
* **Ett problem med inläsning av vy i aktivitetsskapandeprocessen för specifika webbsidor i det uppdaterade användargränssnittet** har korrigerats i aktivitetsskapandeprocessen där vyer inte lästes in i det uppdaterade användargränssnittet för specifika webbsidor, trots att de implementerats korrekt och är synliga vid leverans- eller interaktionsanrop. Detta påverkade flera kunder och gjorde det svårt att validera vybaserad målgruppsanpassning. Vyer visas nu enhetligt på alla sidor som stöds, vilket ökar tillförlitligheten under aktivitetsinställningarna. (TGT-53246)
* **Ett problem med inläsning av intermittent vy i aktivitetsskapandeprocessen i det uppdaterade användargränssnittet** har korrigerats i aktivitetsskapandeprocessen där det ibland inte gick att visa vyer i det uppdaterade användargränssnittet vid aktivitetsredigering. Även om rätt vynamn fanns i nätverksnyttolasten identifierades det inte konsekvent i gränssnittet, vilket påverkade kundernas möjlighet att konfigurera vybaserad personalisering. Vyer visas nu på ett tillförlitligt sätt, med stöd för smidigare arbetsflöden för konfiguration och validering. (TGT-53223)
* **Korrigerat problem i aktivitetsskapandeprocessen där spårade åtgärdsnamn inte sparades i det uppdaterade användargränssnittet**: Korrigerade ett fel i aktivitetsskapandeprocessen där spårade åtgärdsmått inte kunde sparas i det uppdaterade användargränssnittet. När du har namngett ett spårat element och sparat aktiviteten återställs namnet till en standardetikett när det öppnas igen, vilket kan orsaka förvirring och störa målkonfigurationen. Spårade åtgärder behåller nu sina tilldelade namn, vilket gör att kunderna kan ange och hantera konverteringsvärden korrekt. (TGT-53453)

+++

## [!DNL Target Standard/Premium] 25.8.1 (7 augusti 2025)

Den här versionen innehåller följande förbättringar och korrigeringar:

**Aktiviteter**

+++Se detaljer
* Korrigerade flera problem med det uppdaterade användargränssnittet, bland annat fel vid borttagning av sidtyper på grund av mellanrum i indatavärden, otillförlitlig aktivitetskopiering mellan arbetsytor och felfungerande regler för sidleverans i QA-miljöer. (TGT-52703)
* Ett problem har korrigerats i det uppdaterade användargränssnittet för [!DNL Target] där användare med rollen [!UICONTROL Editor] kunde komma åt och försöka redigera aktiva aktiviteter, vilket borde begränsas. Aktivitetslistan och översiktsskärmarna visade felaktigt redigeringsalternativ för aktiva aktiviteter, vilket kan leda till oavsiktliga ändringar. (TGT-53055)
* Ett problem har korrigerats i användargränssnittet för [!UICONTROL Advanced Search] där användaren uppmanades att ange en operand genom att välja &quot;värdet finns&quot; eller &quot;värdet finns inte&quot;, vilket inte bör vara nödvändigt för dessa villkor. (TGT-51961)
* Korrigerade ett problem i det uppdaterade användargränssnittet där försök att kopiera aktiviteter från mellanlagringen till produktionsytan genomgående misslyckades, även i sandlådemiljöer. Kunderna fick olika felmeddelanden, bland annat&quot;Anonym publik som redan används av aktiviteten&quot; och&quot;Ogiltigt målar-ID&quot;, trots att giltiga konfigurationer och lämpliga behörigheter för arbetsytan används. (TGT-52394)

+++

**Upplevelsefragment (XF)**

+++Se detaljer
* Ett problem har korrigerats där Experience Fragment-innehåll (XF) inte kan återges i förhandsvisningen av [!UICONTROL Visual Experience Composer] (VEC) trots att det fungerar korrekt vid innehållsleverans. (TGT-53318)

+++

**Lokalisering**

+++Se detaljer
* Ett lokaliseringsfel har korrigerats där knappen&quot;Lägg till erbjudande&quot; i avsnittet&quot;Kampanjer&quot; inte fanns översatt i flera språkmiljöer i QA-klienten. (TGT-53263)

+++

**Erbjudanden**

+++Se detaljer
* Ett problem har korrigerats där redigering av ett befintligt HTML-erbjudande via Visual Experience Composer (VEC) gjorde att alla ändringar togs bort från innehållsleveransen. Ändringarna visas som nedtonade på ändringsfliken och återspeglas inte i QA-förhandsvisningar, trots att de tillämpas korrekt i det äldre användargränssnittet. (TGT-52863)
* Korrigerade ett fel i det uppdaterade användargränssnittet för [!DNL Target] där HTML inte längre erbjuder ändringar gjorda i [!UICONTROL Visual Experience Composer] (VEC) efter att du navigerat från fliken [!UICONTROL Targeting] till [!UICONTROL Experiences]. (TGT-52874)
* Korrigerade ett fel i det uppdaterade användargränssnittet för [!DNL Target] där infogning av ett HTML-erbjudande före och ett annat efter samma väljare orsakade felaktig platsgenerering. När kunder returnerades från fliken [!UICONTROL Targeting] till fliken [!UICONTROL Experience] kvarstod bara en väljare, vilket resulterade i förlorade ändringar och bruten innehållsleverans. Det här beteendet skiljer sig från det gamla användargränssnittet, som bevarar båda ändringarna korrekt med distinkta platsidentifierare. (TGT-52891)
* Korrigerade ett problem i det uppdaterade användargränssnittet för [!DNL Target] där ett klickat på ett tillagt erbjudande i [!UICONTROL Modifications] -rälen fick den högra panelen [!UICONTROL Configuration] att visas och försvinna då och då, vilket gjorde det svårt att interagera med erbjudandeinställningarna. (TGT-53288)
* Ett problem har korrigerats där HTML erbjudanden som lagts till i målgruppsspecifika variationer i en aktivitet inte sparades konsekvent eller visades i ändringsavsnittet. Efter att ha växlat mellan olika målgrupper under redigeringen försvinner eller misslyckas tidigare erbjudanden, vilket stör valideringen och försenar beredskapen för aktiviteter. (TGT-53440)
* Ett problem har korrigerats där kopiering av en aktivitet som innehöll erbjudanden resulterade i att dubblerade erbjudanden skapades i den nya aktiviteten. Det här beteendet orsakade onödig störning och förvirring, särskilt när du flyttade aktiviteter mellan arbetsytor. Korrigeringen säkerställer att [!DNL Target] erbjudanden nu kopieras korrekt till målarbetsytan utan dubbletter, vilket effektiviserar aktivitetshanteringen och förbättrar arbetsflödets effektivitet. (TGT-53454)

+++

**Single Page Applications (SPA)**

+++Se detaljer
* Korrigerade ett fel i den uppdaterade VEC som förhindrade kunder från att tillämpa ändringar i [!UICONTROL Single Page Application]-vyer (SPA). Aktiviteter som skapats i det gamla användargränssnittet har stöd för vyspecifik målanpassning, men det nya användargränssnittet kunde inte identifiera eller tillåta redigering av dessa vyer. Kontrollerna för visningsväxling är inaktiverade. (TGT-52556)

+++

**Visual Experience Composer (VEC)**

+++Se detaljer
* Ett problem har korrigerats där ändringar som gjorts i upplevelser i [!UICONTROL Visual Experience Composer] antingen inte var synliga eller visades inkonsekvent i användargränssnittet. (TGT-TGT-53381)
* Korrigerade ett fel i den uppdaterade VEC där avsnittet [!UICONTROL Manage Content] inte kunde visa alternativ text för upplevelseminiatyrer. Det här problemet gjorde det svårt för användare att identifiera dokument, särskilt när filnamnen var långa eller trunkerade. (TGT-52291)
* Ett fel har korrigerats där kunder påträffade felaktiga valideringsfel när [!UICONTROL page delivery]-regler konfigurerades i VEC-aktiviteter. Operatorer som &quot;equals any of&quot; och &quot;does not equal any of&quot; utlöste &quot;Invalid input for the operator type&quot; vid inmatning av textvärden, trots att text bör stödjas. (TGT-52629)
* Korrigerade flera problem som orsakade inkonsekvent beteende på panelen [!UICONTROL Modifications] i det uppdaterade användargränssnittet när erbjudanden valdes med knappen Välj ett erbjudande. I stället för att ersätta det befintliga erbjudandet lade användargränssnittet till en dubblett, och försöket att interagera med båda erbjudandena resulterade i konsolfel som `selectorNotFound`. Dessutom visas inte knappen Välj ett erbjudande i vissa erbjudanden, där endast redigerbara egenskaper visas. (TGT-53321)
* Korrigerade ett fel i det uppdaterade användargränssnittet för [!DNL Target] där HTML-kodändringar som gjorts under aktivitetsinställningarna inte fanns kvar på variantsidorna trots att de sparades korrekt för kontrollgrupper. Trots flera försök och återskapande av tester utan sidgrupperingar misslyckades variationssidorna genomgående att behålla ändringarna, vilket påverkade innehållsleveransen och QA-valideringen. (TGT-53436)
* Korrigerade ett fel i den uppdaterade VEC där &quot;equals any of&quot;-operatorn i regler för sidleverans inte accepterar indatavärden. När kundparametrar konfigurerades för alla kryssrutor resulterade valet av den här operatorn i felet&quot;Ogiltig inmatning&quot;, vilket förhindrar att regler skapas. (TGT-52623)

+++

**Arbetsytor**

+++Se detaljer
* Förbättrat arbetsflöde vid kopiering av aktiviteter mellan arbetsytor. Kopiera aktiviteter mellan arbetsytor som tidigare ledde till synkroniseringsfel på grund av att målgrupper saknas och egenskaper som inte tilldelats. Uppdateringen innehåller ett smartare och mer intuitivt arbetsflöde som säkerställer att kopierade aktiviteter är korrekt konfigurerade och klara för publicering. (TGT-47094)
* Ett problem har korrigerats där kunder inte kunde kopiera aktiviteter mellan arbetsytor på grund av ett fel i mutationen `copyActivityBatchOperations`. Försök att duplicera aktiviteter resulterade i ett serverfel (500) och en nyttolast som var null. (TGT-52405)
* Korrigerade ett problem där aktiviteter inte kunde synkroniseras när erbjudanden som refereras i konfigurationen inte var tillgängliga på den valda arbetsytan. Detta orsakade publiceringsfel och lämnade aktiviteter i ett felaktigt tillstånd. (TGT-52535)
* Flera problem har korrigerats vid kopiering av aktiviteter mellan arbetsytor i det uppdaterade [!DNL Target]-gränssnittet. Kunderna påträffade fel relaterade till målgruppsåtkomst, särskilt med liveaktiviteter, och felaktig behörighetsvalidering, även när användaren hade [!UICONTROL Approver]-roller i både käll- och målarbetsytan. (TGT-53002)
* Korrigerade ett problem i det uppdaterade användargränssnittet där kopieringsaktiviteter inom samma arbetsyta i onödan duplicerade associerade erbjudanden och målgrupper. (TGT-53457)
* Ett problem har korrigerats som åtgärdar fall där ad hoc-målgrupper (anonyma) inte kopierades korrekt mellan icke-standardarbetsytor eller från icke-standardarbetsytor. Tidigare uppdateringar säkerställde korrekt duplicering för standardscenarier och scenarier med samma arbetsyta, men förbättringen fokuserade på att bevara kombinerade målgruppskonfigurationer som sträcker sig över flera arbetsytor. Korrigeringen säkerställer ett konsekvent målgruppsbeteende och korrekt målgruppsanpassning för alla arbetsyteövergångar. (TGT-53268)

+++

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
