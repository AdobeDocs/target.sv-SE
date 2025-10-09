---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f0536e466d59fc4e3cccd61c25b7fe7f48f03954
workflow-type: tm+mt
source-wordcount: '4858'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Utforska de senaste funktionerna, förbättringarna och korrigeringarna i [!DNL Adobe Target]. Versionsinformationen omfattar även uppdateringar av [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformskomponenter när det är tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Tidskänsliga uppdateringar som du behöver känna till {#time-sensitive}

[!BADGE Viktigt]{type=Informative}

För tidskänsliga uppdateringar relaterade till [!DNL Adobe Target] och din implementering, ger [!DNL Adobe] detaljerade versionsinformation och dokumentation via [!UICONTROL Experience League]. Här är några viktiga punkter som är relevanta för implementeringen:

### [!DNL Target]-gränssnittsversion växlar borttagning

Mer information finns i [[!DNL Target] Vanliga frågor om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.9.3 (30 september 2025)

Den här versionen innehåller följande förbättringar och korrigeringar.

+++[!UICONTROL Audiences]

* **Reglerna för uteslutning av målgrupper visades felaktigt som inkludering i användargränssnittet i [!DNL Target].** Publiker som konfigurerats med undantagsregler visade sig vara inkluderade vid redigering av mål inom en aktivitet. Trots att exkluderingslogiken tillämpades korrekt under körningen kunde inte användargränssnittet återge regeln korrekt och utelämnade undantagsetiketten. Gränssnittet [!DNL Target] visar nu exkluderingsregler korrekt i både målgruppskonfigurationen och arbetsflöden för målinriktning, vilket ger tydlighet och konsekvens vid kampanjkonfigurationen. (TGT-53808)
* **Avsnittet [!UICONTROL Targeting] indikerade inte att en målgruppsregel har angetts till exclude.** Publiker som konfigurerats med exkluderingslogik visades felaktigt som inkludering i avsnittet [!UICONTROL Targeting] i användargränssnittet som skapats med aktivitet. Trots att backend-objektet tillämpade exkluderingsregeln korrekt kunde det inte representeras visuellt i användargränssnittet, och etiketten&quot;Uteslut&quot; utelämnades, vilket orsakade förvirring under kampanjkonfigurationen. Avsnittet [!UICONTROL Targeting] visar nu tydligt exkluderingsregler, vilket säkerställer konsekvens mellan målgruppskonfigurationen och målinriktningsvisualisering. (TGT-53809)

+++

+++Lokalisering

* **Korrigerade en terminologisk inkonsekvens i den förenklade kinesiska översättningen av vyn &quot;Fullständig information&quot;.**
Tidigare översattes termen &quot;Detaljer&quot; felaktigt som &quot;详 情&quot; i språket zh_CN (Simplified Chinese), vilket bröt mot vedertagna terminologinstruktioner. Detta har korrigerats till &quot;详 细 信 息&quot; för att säkerställa överensstämmelse med termbasen. (TGT-53741)

+++

+++[!UICONTROL Recommendations]

* **Det var svårt att hitta rekommendationsrutorna och välja dem i VEC.** När du har lagt till ett rekommendationserbjudande i (VEC) markerades eller rullades inte ändringen i den vänstra panelen till motsvarande rekommendationsruta på sidan. Det gjorde det svårt att hitta och redigera erbjudandet, särskilt när det är dolt under väljare eller formaterat minimalt. När du klickar på en rekommendationsändring markeras och rullas nu korrekt till det associerade elementet, vilket förbättrar användbarheten och redigeringseffektiviteten i den uppdaterade processen för att skapa aktiviteter. (TGT-52571)
* **Rekommendationsväljarna skrevs om felaktigt efter att en aktivitet sparats.** När du lade till en rekommendation till ett element i VEC var väljaren från början korrekt, men när aktiviteten sparades och öppnades igen ändrades den till en allmän väljare. Försök att manuellt återställa den ursprungliga väljaren resulterade i valideringsfel. Rekommendationsväljarna bevaras nu korrekt efter att de sparats, vilket garanterar tillförlitlig målinriktning och redigerbarhet i den uppdaterade processen för att skapa aktiviteter. (TGT-53709)
* **Det gick inte att redigera villkorsinnehållet när en befintlig aktivitet ändrades.** När en aktivitet redigerades inaktiverades innehållsavsnittet i [!UICONTROL Criteria], med knappar nedtonade och svarar inte. Problemet löstes genom att se till att [!UICONTROL Criteria] konfigurationer är fullt redigerbara under aktivitetsuppdateringar. Kunder kan nu ändra [!UICONTROL Criteria]-innehåll utan att behöva växla markeringar eller använda tillfälliga lösningar, vilket ökar flexibiliteten och användbarheten i den uppdaterade processen för att skapa aktiviteter. (TGT-53812)
* **Kriterierna kunde inte redigeras i en aktivitet.** Alternativen [!UICONTROL Edit Criteria] och [!UICONTROL Remove Criteria] inaktiverades vid åtkomst av villkor från en aktivitet. Samma villkor kan dock redigeras via fliken [!UICONTROL Recommendations]. Kriterierna är nu fullt redigerbara både från aktivitetsredigeringsarbetsflödet och fliken [!UICONTROL Recommendations], vilket ger en konsekvent och effektiv redigeringsupplevelse. (TGT-53814)

+++

+++[!UICONTROL Reports]

* **Generering av ad hoc-erbjudanden i A[!UICONTROL utomated Personalization]-aktiviteter orsakade inkonsekvenser i rapporteringen.** Användningen av funktionen Generera ad hoc-erbjudanden i [!UICONTROL Automated Personalization]-aktiviteter (AP) ledde till felaktig rapportering. Erbjudande-ID återanvändes i synnerhet på olika platser, vilket ledde till att rapporteringsdata skrevs fel eller skrevs över. Ad-hoc-erbjudanden genereras nu med distinkta identifierare per plats, vilket ger korrekt spårning och rapportering för alla konfigurerade upplevelser. (TGT-53757)
* **Det gick inte att läsa in aktivitetsrapporter på grund av ett JavaScript-fel.**-kunder påträffade ett meddelande om att något gick fel vid åtkomst till fliken [!UICONTROL Reports] för vissa aktiviteter. Felet orsakades av ett JavaScript-undantag: Det går inte att läsa egenskaper för undefined (läsa indexOf), som utlöstes under GraphQL-anropet `getAnalyticsReportSummary`. Rapporterna läses nu in korrekt och felhanteringen har förbättrats för att förhindra liknande fel i det uppdaterade arbetsflödet som skapar aktiviteter. (TGT-53797)
* **Rapporterna kraschar efter interaktion med rullningslisten.** När du klickade på rullningslisten på fliken [!UICONTROL Reports] kraschade sidan, följt av ett JavaScript-fel:
  `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.` rapporter läses nu in och rullas korrekt utan att utlösa fel eller krascher. (TGT-53828)
* **Rapporterna visade inte det primära måttet.** Det primära måttet, som konfigurerats som ett konverteringsmått med en mbox, saknades i aktivitetsrapporterna. Sökning efter metriskt namn eller mbox-namn gav inga resultat, vilket förhindrar synlighet i viktiga prestandadata. Primära mätvärden visas nu korrekt på fliken [!UICONTROL Reports], vilket ger korrekt spårning och analys av kampanjresultat. (TGT-53773)
* **Fliken [!UICONTROL Reports] i det uppdaterade användargränssnittet kraschade när den interagerade med den vågräta rullningslisten.** Vyn [!UICONTROL Reports] kraschade ibland med ett felmeddelande om att något gick fel när den vågräta rullningslisten användes för att visa mätvärden. Rullningslisten fungerar nu på ett tillförlitligt sätt, så att kunderna kan visa och analysera all mätinformation utan att behöva använda tillfälliga lösningar som att zooma ut eller använda skiftrullning. (TGT-53824)

+++

+++[!UICONTROL Visual Experience Composer] (VEC)

* **Redigeringsmenyn visades inte konsekvent när du klickade på vägbeskrivningar i VEC.**
När du markerar HTML-element via vägbeskrivningar i (VEC) kommer redigeringsmenyn ibland att misslyckas eller försvinna snabbt, vilket gör att elementmarkeringen inte är tillförlitlig. Redigera-menyn visas nu enhetligt när du navigerar via vägbeskrivningar, vilket förbättrar arbetsflödet för elementval i den uppdaterade processen att skapa aktivitet. (TGT-52873)
* **Det gick inte att visa snabbmenyn i VEC.** Snabbmenyn i det uppdaterade VEC-gränssnittet visades inte konsekvent när du klickade på element, vilket gör det svårt att komma åt redigeringsalternativen. Snabbmenyn visas nu på ett tillförlitligt sätt när du väljer element, vilket förbättrar redigeringsarbetsflödet och den övergripande användbarheten i den uppdaterade processen att skapa aktiviteter. (TGT-53015)
* **Det gick inte att visa snabbmenyn för vissa element i VEC.** Snabbmenyn visades inte när specifika element valdes i den uppdaterade VEC:n, vilket gör det svårt att använda ändringarna. Snabbmenyn visas nu enhetligt för alla element som stöds, vilket förbättrar tillförlitligheten och användbarheten för redigeringen i det uppdaterade arbetsflödet som skapar aktiviteter. (TGT-53248)
* **Snabbmenyn försvann första gången du klickar när du använder vägbeskrivningar i VEC.** Om du valde ett överordnat element via vägbeskrivningarna i VEC visades snabbmenyn snabbt och försvinner, vilket gör det svårt att komma åt redigeringsalternativen. Snabbmenyn är nu fortfarande synlig och funktionell när du navigerar bland element via vägbeskrivningar, vilket förbättrar tillförlitligheten i arbetsflödet för att välja element i den uppdaterade processen för att skapa aktivitet. (TGT-53424)
* **Snabbmenyn visades inte för element på den översta nivån i VEC.** Om du valde element på den översta nivån, till exempel `<div>` eller `<main>` taggar, via vägbeskrivningarna i VEC, utlöstes inte snabbmenyn, vilket förhindrar ytterligare redigeringsåtgärder. Snabbmenyn visas nu konsekvent för alla element som stöds, inklusive behållare på den översta nivån, vilket förbättrar flexibiliteten och användbarheten i arbetsflödet som skapar aktiviteter. (TGT-53770)
* **Element på en viss sida kunde inte redigeras i VEC.** Vissa element på sidan kunde inte markeras eller redigeras i den uppdaterade VEC:n. Problemet isolerades till den sidan och påverkade inte andra sidor på samma konto. Alla element på sidan kan nu markeras och redigeras som förväntat, vilket återställer alla funktioner i det aktivitetsskapande arbetsflödet. (TGT-53353)
* **Förbättrat arbetsflöde när underordnade element visas när element väljs i VEC.** VEC visar nu underordnade element när du hovrar över eller väljer ett överordnat HTML-element för att förbättra användbarheten och precisionen när aktiviteter skapas. Tack vare den här förbättringen kan kunderna bättre förstå sidans struktur och göra exaktare ändringar, vilket effektiviserar redigeringsarbetsflödet i det uppdaterade användargränssnittet. (TGT-53416)
* **Element i befintliga aktiviteter kunde inte redigeras med ändringsfältet.** När tidigare skapade aktiviteter redigerades gick det inte att aktivera ändringsfältet för vissa element på sidan, vilket förhindrar uppdateringar. Detta problem observerades främst i modifierade aktiviteter och var svårt att reproducera i nyskapade. Ändringsfältet visar nu konsekvent och tillåter redigering av alla element som stöds, vilket förbättrar tillförlitligheten och användbarheten i det uppdaterade arbetsflödet för att skapa aktiviteter. (TGT-53013)

+++

+++[!UICONTROL Workspaces]

* **Om en aktivitet klonas till en annan arbetsyta utlöstes felet&quot;Ogiltig användarinmatning&quot;.** Ett försök att klona en aktivitet från en arbetsyta till en annan resulterade i felet&quot;InvalidProperty.Json - det okända egenskapsnamnet&quot;content&quot;.&quot; Problemet orsakades av felaktig hantering av aktivitetsmetadata under kloningsprocessen. Aktiviteter kan nu klonas över arbetsytorna utan att utlösa valideringsfel, vilket ger smidigare arbetsflöden för aktivitetsdistribution. (TGT-53731 &amp; TGT-53736)

+++

## [!DNL Target Standard/Premium] 25.9.2 (22 september 2025)

Den här versionen innehåller följande korrigeringar och förbättringar:

**[!UICONTROL Audiences]**

+++Se detaljer
* **Ett problem där aktiviteter inte kunde kopieras på grund av ogiltiga målgrupps-ID har korrigerats.** Kunder som försöker kopiera aktiviteter i den uppdaterade processen för att skapa aktiviteter påträffade ett fel som orsakas av ogiltiga målgrupps-ID:n (till exempel -175272244307). Det här problemet med backend-validering förhindrade dubblering av aktiviteter inom samma arbetsyta. Problemet har lösts och aktiviteter kan nu kopieras utan målgruppsrelaterade fel. (TGT-53717)
* **Ett problem har korrigerats där ogiltiga användarindatafel påträffades för målgrupper som bara är aktivitetsaktiva i [!UICONTROL Automated Personalization]-aktiviteterna för [!UICONTROL Manage Content] modal.**-kunder påträffade ogiltiga användarindatafel när de konfigurerade målgrupper som bara är aktivitetsspecifika i [!UICONTROL &#x200B; Manage Content] modal för AP-aktiviteter. Problemet uppstod trots att målgrupperna tidigare användes korrekt. Kombinerade målgruppskonfigurationer sparas nu korrekt utan att utlösa valideringsfel. (TGT-53749)

+++

**Dokumentation**

+++Se detaljer
* **Målspecifika SDK-dokumentationssidor har flyttats till Adobe Target-databasen.** Som en del av dokumentationsomstruktureringen för Web SDK har [!DNL Target]-specifikt innehåll migrerats från de allmänna SDK-dokumenten till [!DNL Adobe Target] [Utvecklarhandboken](https://experienceleague.adobe.com/sv/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}. Ändringen förbättrar innehållsidentifieringen och säkerställer att lösningsspecifik vägledning upprätthålls av rätt produktgrupp. (TGT-53374)

+++

**[!UICONTROL Offer Decisions]**

+++Se detaljer
* **Alternativet för beslut om erbjudande visas nu konsekvent när inledande aktivitet skapas.** Löste ett problem i det uppdaterade användargränssnittet där alternativet [!UICONTROL Offer Decision] inte kunde visas när A/B-aktiviteter skapades för första gången, särskilt när det används i inkognito-läge på klientorganisationer med aktiverade erbjudandebeslut. Alternativet visades endast efter navigering till [!UICONTROL Targeting]-steget och tillbaka till [!UICONTROL Experiences]. Med den här korrigeringen är alternativet [!UICONTROL Offer Decision] omedelbart tillgängligt under den första konfigurationen, vilket förbättrar användbarheten och minskar förvirringen. (TGT-51888)

+++

**[!UICONTROL Offers]**

+++Se detaljer
* **Korrigerade ett problem där omdirigeringserbjudandena inte inkluderade `redirectOptions` i nyttolasten när `includeContent=true`.** Kunder som hämtar omdirigeringserbjudanden med `includeContent=true ` saknade fältet `redirectOptions` i svarsnyttolasten. Inkonsekvensen påverkade arbetsflöden, t.ex. kopiering av erbjudanden och skapande av aktiviteter. Omdirigeringserbjudanden inkluderar nu `redirectOptions` korrekt när innehåll begärs. (TGT-53737)

+++

**[!DNL Recommendations]**

+++Se detaljer
* **Klickspårning har återställts för [!UICONTROL Recommendations] aktiviteter som har skapats i det uppdaterade användargränssnittet.** Löste ett problem där [!UICONTROL Recommendations] aktiviteter skapade i det uppdaterade användargränssnittet inte kunde registrera klickspårning, vilket resulterade i noll rapporterade konverteringar. Aktiviteter som byggts i det äldre användargränssnittet spårade klickningar korrekt och rapporterade konverteringar som förväntat. Med den här korrigeringen ser du till att rekommendationsaktiviteter som skapas i det uppdaterade användargränssnittet nu innehåller rätt spårningsattribut, återställer konverteringsrapportering och anpassning till A4T-värden. (TGT-53287)
* **Klickspårning återställd för rekommendationsaktiviteter.** Löste ett problem där [!UICONTROL Recommendations] aktiviteter skapade i det uppdaterade användargränssnittet inte kunde registrera klickspårning, vilket resulterade i noll rapporterade konverteringar. Det gamla användargränssnittet tillämpade ett spårnings-ID (`at-track-click`) på [!UICONTROL Recommendations]-innehåll korrekt, medan det uppdaterade användargränssnittet felaktigt infogade en platshållare (`__recsClickTrackIdPlaceholder__`), vilket förhindrar serverdelsspårning. Den här korrigeringen ser till att [!DNL Recommendations]-innehåll nu innehåller rätt spårnings-ID, återställer konverteringsrapportering och justering med A4T-mått. (TGT-53496)
* **Kraschen för samlingsredigeraren löstes i det uppdaterade användargränssnittet.** Korrigerade ett fel i det uppdaterade [!UICONTROL Visual Experience Composer] (VEC)-gränssnittet där sidan kraschade när en samling öppnades från redigeringspanelen med ett TypeError: Det går inte att läsa egenskaper för undefined (läsa customLocale). Det här felet inträffade i flera aktivitetstyper, inklusive [!UICONTROL Recommendations] och A/B-tester. (TGT-53703)
* **Alternativ för att ta bort den valda samlingen som har återställts i VEC.** Korrigerade ett fel i VEC där användare bara kunde ersätta en markerad samling i en [!UICONTROL Recommendations]-aktivitet, men inte kunde ta bort den helt. Den här begränsningen blockerade användningsfall som kräver en ren borttagning av samlingen utan ersättning. Med den här korrigeringen introduceras ett tydligt alternativ för att ta bort den valda samlingen, vilket ger större flexibilitet i aktivitetsinställningarna och anpassning till det gamla gränssnittets beteende. (TGT-53652)
* **Anpassade villkorssamlingar visas nu korrekt i [!UICONTROL Recommendations]-gränssnittet.** Korrigerade ett fel i gränssnittet Recommendations där samlingar som skapats med anpassade villkor inte kunde visa produktresultat. Standardattributbaserade samlingar fungerade som förväntat, men de som använder anpassade filter returnerade&quot;Inga resultat hittades&quot; trots giltiga katalogmatchningar. Den här korrigeringen ser till att samlingar som använder anpassade attribut nu fylls i korrekt på fliken [!UICONTROL Product] och återställer alla funktioner för anpassade rekommendationer. (TGT-53653)
* **Ett problem där samlingar inte visade produkter när sidan [!UICONTROL Products] öppnades har korrigerats.** Kunder som använder samlingar i avsnittet [!UICONTROL Recommendations] fick tomma produktresultat första gången sidan [!UICONTROL Products] öppnades. Problemet uppstod på grund av ett serverdelsfel i GraphQL-frågan, som inte kunde läsa in produktdata för samlingar med anpassade villkor. Problemet har lösts och produkterna visas nu korrekt utan att du behöver byta miljö. (TGT-53694)
* **Ett problem där samlingar inte kunde tas bort i formulärbaserade [!UICONTROL Recommendations]-aktiviteter har korrigerats.** Kunder som skapar [!UICONTROL Recommendations] aktiviteter med [!UICONTROL Form-Based Experience Composer] kunde inte avmarkera en tidigare vald samling. Användargränssnittet krävde att en samling skulle väljas innan den sparades, vilket hindrade användarna från att återgå till&quot;Alla samlingar&quot;. Detta beteende har uppdaterats för att matcha VEC-funktionen, vilket gör att kunderna kan spara utan en vald samling och som standard använda Alla samlingar som förväntat. (TGT-53708)
* **Korrigerade ett problem där kampanjer inte kunde anges av attribut på grund av att samlings- eller filtreringsregelvärden saknas.** Kunder som konfigurerar kampanjer efter attribut i processen för att skapa aktivitet påträffade ett fel som anger att en befordran saknade antingen ett samlings-ID eller filtreringsregelvärden. Det här verifieringsproblemet blockerade progression även när installationen verkade vara klar. Kampanjer kan nu sparas korrekt när de konfigureras med attribut. (TGT-53750)
* **Korrigerade ett problem där aktiviteter inte kunde sparas på grund av dubblerade upplevelsenamn.**-kunder påträffade ett ogiltigt användarindatafel när aktiviteter som innehöll specifika kombinationer av villkor och design sparades. Felet utlöstes av duplicerade upplevelsenamn, även när konfigurationen verkade vara giltig. Aktiviteter med distinkta konfigurationer kan nu sparas utan namnkonflikter. (TGT-53805)
* **Ett problem har korrigerats där valideringen var ogiltig för kampanjer som konfigurerats av attribut.**-kunder stötte på beständiga valideringsfel när de konfigurerade kampanjer efter attribut i processen för att skapa aktivitet, även när alla obligatoriska fält fylldes i korrekt. Problemet orsakades av felaktig verifieringslogik i arbetsflödet [!UICONTROL Recommendations]. Attributbaserade erbjudanden validerar nu och sparar som förväntat. (TGT-53811)
* **Ett problem har korrigerats där en befordran för en aktiv [!UICONTROL Recommendations]-aktivitet utlöste ett fel.** Kunder påträffade felet&quot;En befordran saknar antingen ett samlings-ID eller filtreringsregelvärden&quot; när de försökte tillämpa en frontbefordran på en aktiv [!UICONTROL Recommendations]-aktivitet, även efter att ha angett giltig konfigurationsinformation. Kampanjer kan nu tillämpas på aktiva aktiviteter utan att utlösa valideringsfel, vilket ger en smidigare upplevelse i det uppdaterade användargränssnittet för att skapa aktiviteter. (TGT-53738)
* **Ett problem där produkter inte var synliga i samlingar i användargränssnittet för [!UICONTROL Recommendations] har korrigerats.** Kunder från en enskild klientorganisation rapporterade att produktlistor inte kunde läsas in när de visade vissa samlingar i avsnittet [!UICONTROL Recommendations] i det nya användargränssnittet. Problemet löstes tillfälligt genom att olika miljöer ändrades, men den här lösningen ledde till en sämre användarupplevelse. Produktentiteter läses nu in konsekvent utan att miljön behöver växlas. (TGT-53783)
* **Ett problem har korrigerats där villkor och designer inte visades på en rad i gränssnittet för att skapa aktiviteter.** Tidigare visades kriterier och designer i processen för att skapa aktivitet i ett komprimerat format, vilket gjorde det svårt för kunder att visa och hantera enskilda objekt. Varje kriterium och design visas nu på sin egen rad, vilket förbättrar läsbarheten och användbarheten i det uppdaterade användargränssnittet. (TGT-53818)

+++

**Rapporter**

+++Se detaljer
* Mått **[!UICONTROL Total Revenue]ingår nu i CSV-exporter från aktivitetsrapporter.** Löste ett problem i det uppdaterade [!UICONTROL Overview]-gränssnittet där de totala intäkterna visades korrekt i aktivitetsrapportvyn men saknades i CSV-exporten, vilket visades som $0. Denna diskrepans förhindrade användare från att förlita sig på exporterade data för offlineanalys och rapportering. (TGT-53325)
* Mått **[!UICONTROL Total Sales]ingår nu i CSV-exporter från aktivitetsrapporter.** Löste ett problem i det uppdaterade användargränssnittet där [!UICONTROL Total Sales]-måttet visades korrekt i aktivitetsrapportvyn men saknades i CSV-exporten. Denna diskrepans förhindrade användare från att få tillgång till fullständiga prestandadata i hämtade rapporter. Den här korrigeringen ser till att [!UICONTROL Total Sales]-värden nu inkluderas korrekt i CSV-exporter, vilket återställer konsekvensen mellan apprapportering och offlineanalys. (TGT-53330)
* **Förbättrade felmeddelanden för [!UICONTROL Graph View] när mätvärden inte är aktiverade.** Korrigerade ett fel i VEC där [!UICONTROL Graph View] visade ett allmänt meddelande om att något gick fel när ett begärt mätvärde inte aktiverades i det associerade [!DNL Analytics]-rapportpaketet. Det här problemet utlöstes av ett `not_enabled_metric`-fel i GraphQL-svaret i serverdelen. Den här korrigeringen ersätter det otydliga felet med ett mer informativt meddelande som hjälper användare att identifiera konfigurationsproblem i [!DNL Analytics], vilket minskar förvirring och onödiga supporteskaleringar. (TGT-53577)
* **Ett problem har korrigerats där rapportens varaktighet överskred den tillåtna gränsen på 90 dagar.** kunder som använder filtret [!UICONTROL Last X Days] i avsnittet [!UICONTROL Reports] kunde välja längre tidsperioder än 90 dagar, vilket kan leda till prestandaproblem och ofullständiga data. Filtret har uppdaterats för att framtvinga ett maximalt intervall på 90 dagar, vilket ger en konsekvent och tillförlitlig rapportering. (TGT-53795)
* **Ett problem där CSV-rapporter för prestanda genererades med standardmiljön i stället för den valda har korrigerats.** Tidigare, när kunderna ändrade miljön i rapportinställningarna och genererade en prestandarapport, innehöll den resulterande CSV-filen data från standardmiljön i stället för den valda.  Gränssnittet skickar nu parametern `environmentId` korrekt och ser till att rapporten speglar den valda miljön. Dessutom har felhanteringen förbättrats. Om GraphQL-fel inträffar under CSV-genereringen visas nu ett tydligt felmeddelande i användargränssnittet i stället för att en tom CSV-fil skapas. (TGT-53064)
* **Ett problem har korrigerats där A4T-rapportering (Analytics for Target) inte kunde visa data i [!UICONTROL Graph View].** Kunder som använder [!DNL Target] med A4T-integrering påträffade ett felmeddelande om att något gick fel vid växling till diagramvyn på fliken Rapportering för A/B-testaktiviteter. Även om [!UICONTROL Table View] lästes in korrekt kunde [!UICONTROL Graph View] inte återge måtttrender över det valda tidsintervallet. [!UICONTROL Graph View] visar nu prestandadata som förväntat för alla mätvärden som stöds, vilket förbättrar synligheten och rapporteringsnoggrannheten i det uppdaterade användargränssnittet. (TGT-53573)

+++

**Visual Experience Composer (VEC)**

+++Se detaljer
* **Elementmetadata visas nu när du hovrar på den synliga menyn.** Förbättrade den synliga menyn i VEC så att ytterligare elementdetaljer som ID, klass och namn visas när du hovrar över ett objekt. Den här förbättringen gör det enklare att identifiera och skilja ut element under aktivitetsinställningarna. (TGT-53409)
* **Bakgrundshovring markerar nu motsvarande element i VEC.** Förbättrade [!UICONTROL Visual Experience Composer] så att motsvarande element markeras i redigeraren när du hovrar över objekt på den synliga menyn. Elementtypen visas också, till exempel behållare, fet text eller knapp. Det här beteendet gäller för element på samma nivå och utesluter typer som inte stöds, som SVG, baserat på valideringslistan. (TGT-53411)
* **Varning om osparade ändringar har återställts i arbetsflöden för VEC-ändringar.** Korrigerade ett fel i VEC där användare inte längre informerades om osparade ändringar i anpassade kodändringar. Till skillnad från det gamla användargränssnittet saknade den nya upplevelsen uppmaningar när personaliseringsredigeraren navigerades bort eller stängdes, vilket ledde till oavsiktlig förlust av framsteg. Med den här korrigeringen återställs varningar för alla ändringstyper, inklusive anpassad kod, och användarna varnas innan de avslutar utan att spara. (TGT-53435).
* **Anpassade kodändringar bevaras nu under siduppdatering i VEC.** Korrigerade ett fel i VEC där anpassade kodändringar förlorades under webbplatsuppdateringar. Detta problem uppstod på sidor med flera omladdningar, vilket gjorde att redigeraren återställde och återställer ändringar som inte sparats. Korrigeringen ser till att anpassade kodredigeringar förblir intakta även om sidan läses in igen under redigeringen, vilket förhindrar oavsiktlig förlust av förloppet. (TTGT-53501)
* **Inloggningsproblemet har lösts för webbplatsåtkomst inom VEC.** Korrigerade ett fel där användare inte kunde logga in på sin plats när de använde den via VEC. Inloggningsflödet dirigerade om användare till inloggningssidan upprepade gånger, vilket förhindrar att aktivitet konfigureras och förhandsgranskas. Med den här korrigeringen kan du vara säker på att VEC inte längre stör inloggningsbeteendet och återställa förväntad åtkomst för autentiserade användare. (TGT-53524)
* **Problem med cookie-dubbletter löstes i VEC Helper-tillägget.** Korrigerade ett fel där tillägget [!UICONTROL Adobe Experience Cloud Visual Editing Helper] duplicerade cookien `at_qa_mode` under QA via förhandsgranskningslänkar. När du växlade förhandsvisningsindex manuellt skapades flera cookies med motstridiga värden mellan domäner, vilket förhindrar att testare på ett tillförlitligt sätt byter varianter. Detta beteende observerades även utanför målgränssnittet och påverkade både interna konton och klientkonton. Med den här korrigeringen säkerställs en konsekvent hantering av cookies genom att dubblettposter förhindras och domänomfånget justeras, vilket möjliggör sömlös växling av varianter utan att manuell rensning av cookies krävs. (TGT-53579)
* **Ett problem har korrigerats där minnesläckor orsakades när du klickade på element på en viss hemsida.** Kunder som skapar aktiviteter på den här hemsidan fick minnesläckor när de interagerade med sidelement. Felet var kopplat till för många konsolvarningar och ökad minnesanvändning i delbildrutor, särskilt relaterade till felformaterade resursattribut. Minnesanvändningen är nu stabil under interaktionen. (TGT-53761)
* **Korrigerade ett fel där VEC kraschade och visade en tom skärm när vissa aktiviteter lästes in.** Kunder från en viss klientorganisation rapporterade att redigeraren inte kunde läsa in specifika aktiviteter. VEC fastnade fortfarande på&quot;Tillämpa initiala ändringar&quot; innan det kraschade och en tom skärm visades. VEC läser nu in påverkade aktiviteter utan fel i den uppdaterade processen för att skapa aktiviteter. (TGT-52932)
* **Ett problem har korrigerats där [!UICONTROL Manage Content] rail i [!UICONTROL Automated Personalization]-aktiviteter visade inkonsekventa platsetiketter.** kunder rapporterade att [!UICONTROL Manage Content]-fliken visade olika platsnummer på flikarna [!UICONTROL Experiences] och [!UICONTROL Offers]. (till exempel plats 2 och plats 4 i upplevelser och plats 1 och plats 2 i erbjudandet) även när bara två platser har konfigurerats. Platsetiketter är nu konsekventa och exakt mappade till ändringar, vilket gör att det blir lättare att använda och förtydliga när du skapar aktiviteter. (TGT-52934)
* **Korrigerade ett fel där ändringar i VEC förlorades efter sparande.**-kunder rapporterade att när en ändring har sparats i VEC uppdateras sidan och återställs till den tidigare versionen. Det här problemet gjorde att de senaste uppdateringarna gick förlorade om inte hela aktiviteten sparades omedelbart. Ändringarna bevaras nu korrekt när du har sparat och redigeraren återställer inte längre ändringarna oväntat, vilket ger en tillförlitlig upplevelse av arbetsflödet som skapats med aktivitet. (TGT-53500)
* **Utökad markering av element i VEC genom att visa elementtypen vid hovring och markering.** VEC dekorerar nu HTML-element med deras typ när de hovras över eller markeras för att förbättra användbarheten när aktiviteter skapas. Den här förbättringen gör det enklare för kunderna att identifiera och välja rätt element. Markerade element markeras med en tydlig färg och hovrade element markeras med blå kontur. Elementtypen visas också, vilket ger ett tydligare sammanhang vid redigering. (TGT-53502)

+++

## Datastream-uppdateringar (19 september 2025)

Kombinationen av dataström-ID och sandlåda måste vara unik för målanslutningarna [!DNL Adobe Target].

Verifieringslogik för målanslutningar för [!DNL Target] har uppdaterats för att tvinga fram att kombinationen av datastream-ID och sandlådenamn måste vara unik inom en IMS-organisation. Detta innebär:

* Det går inte att återanvända samma ID för datastream + sandlådenamn över flera [!DNL Target]-målanslutningar.
* Samma dataström-ID kan bara användas för olika anslutningar om de är konfigurerade i olika sandlådor.
* Den här regeln gäller för alla datastream-markeringar, även när&quot;Ingen&quot; har valts.

Denna uppdatering ger en konsekvent konfiguration och förhindrar konflikter mellan miljöer med flera sandlådor. Mer information finns i [Adobe Target-anslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} i guiden *Experience Platform Destinations*.

## [!DNL Target Standard/Premium] 25.9.1 (5 september 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**[!UICONTROL Experience Fragments]**

+++Se detaljer
* **Förbättrad användarattribuering för [!UICONTROL AEM Experience Fragment] erbjudanden.** Löste ett fel i VEC där fältet [!UICONTROL Last updated] för [!UICONTROL AEM Experience Fragment] (XF) felaktigt visade ett kod-ID i stället för användarnamnet. Denna diskrepans inträffade när erbjudanden valdes i det uppdaterade användargränssnittet, vilket skapade inkonsekvens med det gamla användargränssnittet och HTML-erbjudandet, som korrekt visade namnet på den senaste redigeraren. Med den här programfixen får du konsekvent användarattribuering över olika erbjudandetyper, vilket förbättrar genomskinligheten och justerar det med förväntat beteende. (TGT-52880 &amp; TGT-52898)

+++

**Offer Decisioning**

+++Se detaljer
* **Fel vid beslut om erbjudande åtgärdat för ODE-erbjudanden.** Löste ett problem där ODE-erbjudanden (Offer Decision Engine) som injicerades via [!DNL Target] returnerade ett 400-fel på grund av saknade formatmetadata. Felmeddelandet visade att MIME-typen var null, vilket förhindrar att erbjudandebeslut kan bearbetas. Med den här programfixen får du en korrekt hantering av metadata för erbjudanden, återställer funktioner för personlig innehållsleverans och möjliggör oavbrutet genomförande av marknadsföringskampanjer. (TGT-53635)
* **Återgivningsproblemet för ODS-erbjudanden har åtgärdats.** Löste ett problem där [!DNL Offer Decision Service] (ODS) erbjudanden som skapats via [!DNL Adobe Journey Optimizer] (AJO) inte återgavs när aktiviteter skapades med VEC i det uppdaterade användargränssnittet. Samma konfiguration fungerade korrekt i det gamla användargränssnittet, vilket ledde till förvirring och blockerade kampanjkörningar. Med den här programfixen säkerställs att erbjudandet levereras enhetligt i båda användargränssnittsversionerna, vilket återställer förväntat beteende för AJO-driven personalisering.

+++

**Rapporter**

+++Se detaljer
* **Hämtningsalternativet har återställts i rapportavsnittet i det uppdaterade rapportöversiktsgränssnittet.** Löste ett problem i det nya översiktsgränssnittet där knappen [!UICONTROL Download] saknades i avsnittet Rapporter, vilket hindrade användare från att exportera prioritetspoäng för attribut. Den här uppdateringen återställer alla exportfunktioner, vilket ger smidig åtkomst till hämtningsbara data för analys och rapportering. (TGT-53222)
* **[!UICONTROL Download full CSV report]-knappen har återställts i vyn [!UICONTROL Important attributes].** Löste ett problem i det uppdaterade användargränssnittet för att skapa aktiviteter där knappen [!UICONTROL Download full CSV report] saknades i avsnittet [!UICONTROL Important Attributes] i rapportvyn. Med den här korrigeringen återställs åtkomsten till hämtningsbara insikter, vilket ger enhetliga funktioner i både det uppdaterade och det gamla användargränssnittet. (TGT-53238)
* **Löste gränssnittsproblem som påverkar [!UICONTROL Auto Target]-rapportering i det uppdaterade översiktsgränssnittet.** har åtgärdat flera gränssnittsproblem i det uppdaterade översiktsgränssnittet som påverkar [!UICONTROL Auto Target] aktivitetsrapportering. Bland dessa korrigeringar finns:

   * Saknade hissar- och förtroendevärden i sammanfattningsrapporter
   * Felaktig färgindikator för kryssrutan &quot;Modeller byggda&quot;
   * Icke-fungerande diagramrapport trots datavarians i [!DNL Analytics]
   * Hämtningslänk saknas för [!UICONTROL Automated Segments]- och [!UICONTROL Important Attributes]-rapporter
   * [!UICONTROL Automated Segments]-rapportvisning har brutits

  Dessa korrigeringar återställer förväntat rapporteringsbeteende och förbättrar synligheten för [!UICONTROL Auto Target]-prestanda i det uppdaterade användargränssnittet. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Se detaljer
* **Formulärvalideringen har korrigerats för parameternärvarovillkor i uppdaterat användargränssnitt.** Löste ett problem i det uppdaterade användargränssnittet där användaren felaktigt måste ange ett värde genom att välja [!UICONTROL Custom mbox parameter value is present] eller [!UICONTROL Parameter is present]. Det här beteendet står i konflikt med den avsedda logiken, som helt enkelt kontrollerar om det finns en parameter oavsett dess värde. Korrigeringen anpassar formulärvalidering till förväntat beteende, vilket ger smidigare aktivitetsinställningar och stöd för ett fullständigt införande av det uppdaterade användargränssnittet. (TGT-53638)
* **Formulärlogiken har korrigerats för regler för parameternärvaro vid sidleverans.&quot;** Löste ett problem i det uppdaterade användargränssnittet där användaren felaktigt måste ange ett ytterligare parametervärde när sidleveransregler som [!UICONTROL Parameter is present], [!UICONTROL Parameter is not present], [!UICONTROL Parameter value is present] eller [!UICONTROL Parameter value is not present] väljs. Detta beteende var inkonsekvent med det gamla användargränssnittet och motstod den avsedda logiken för att identifiera parameterförekomst utan att ange ett värde. Den här korrigeringen återställer förväntat regelkonfigurationsbeteende, effektiviserar aktivitetsinställningarna och förbättrar användbarheten. (TGT-53640)
* **Verifieringslogiken har förbättrats för regelbyggaren för flera sidor i det uppdaterade användargränssnittet.** Löste flera verifieringsproblem i regelbyggaren för flera sidor i det uppdaterade användargränssnittet. Bland dessa korrigeringar finns:

   * Förhindrar att regler skapas när parametern mbox är tom
   * Visa lämpliga felmeddelanden för ogiltiga regellägen
   * Korrigera valideringslogik för unära och parameterbaserade operatorer som inte kräver operandvärden
   * Aktivera hash-fragmentregler med unära operatorer genom att återställa sparfunktioner

  Uppdateringarna säkerställer korrekt regelkonfiguration och förbättrar användbarheten i komplexa sidleveransscenarier. (TGT-53722)
* **Platsens namnbytesproblem har lösts i A/B- och MVT-aktiviteter.** Korrigerade ett fel i det uppdaterade användargränssnittet där namnbytet av en plats i en [!UICONTROL A/B Test] - eller [!UICONTROL Multivariate Test] -aktivitet inte kvarstod efter navigering mellan platslistan, målplatsen och bakåt. Den här uppdateringen ser till att platsnamnändringar sparas och visas på ett konsekvent sätt i hela aktivitetsarbetsflödet. (TGT-52367)
* **Platsnamnbeständighet har åtgärdats för MVT- och AP-aktiviteter i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där platsnamn som redigerades i [!UICONTROL Multivariate Test]- (MVT) och [!UICONTROL Automated Personalization] (AP) aktiviteter inte sparades korrekt. När namnet på en plats har ändrats återställs namnen till det tidigare läget när du navigerade mellan flikar, till exempel [!UICONTROL Targeting] och [!UICONTROL Experiences]. Med den här korrigeringen får du konsekvent platsnamn på olika flikar och blir tillförlitligare under aktivitetsinställningarna. (TGT-52927)
* **Platsetiketten har korrigerats på panelen Hantera upplevelser för MVT-aktiviteter.** Löste ett problem i det uppdaterade användargränssnittet där [!UICONTROL Manage Experiences]-panelaktiviteter i [!UICONTROL Multivariate Test] (MVT) visade inkonsekvent platsnumrering. Med den här korrigeringen säkerställs att platsetiketterna är sekventiella och korrekt anpassade till användardefinierade ändringar, vilket förbättrar klarheten och användbarheten vid inställning av upplevelser. (TGT-52929)

+++

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
