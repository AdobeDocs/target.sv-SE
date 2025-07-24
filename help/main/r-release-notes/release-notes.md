---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 265108dbb0a459e1b111fda01a35042170f05562
workflow-type: tm+mt
source-wordcount: '4383'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Utforska de senaste funktionerna, förbättringarna och korrigeringarna i [!DNL Adobe Target]. Versionsinformationen omfattar även uppdateringar av [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformskomponenter när det är tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Tidskänsliga uppdateringar som du behöver känna till {#time-sensitive}

[!BADGE Viktigt]{type=Informative}

För tidskänsliga uppdateringar relaterade till [!DNL Adobe Target] och din implementering innehåller [!DNL Adobe] detaljerade versionsinformation och dokumentation via [!UICONTROL Experience League]. Här är några viktiga punkter som är relevanta för implementeringen:

### [!DNL Target]-gränssnittsversion växlar borttagning

+++Se information
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
* **Enhetlig aktivitetsinformation**: De senaste ändringarna, oavsett vilket användargränssnitt du använder, visas på den aktiva webbplatsen. Det gamla användargränssnittet visar dock bara de senaste ändringarna som gjorts i den versionen. Den här situationen kan orsaka förvirring om aktiviteter som redigeras i det uppdaterade användargränssnittet ser annorlunda ut än i det äldre användargränssnittet.

#### Fler resurser att lära sig om det uppdaterade användargränssnittet

* [[!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md): Här behandlas vanliga frågor om det nya [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC), inklusive navigeringsändringar, funktionsplatser och borttagning av den tillfälliga användargränssnittsversionen. Vare sig du är marknadsförare, utvecklare eller administratör kan du med de här vanliga frågorna få en smidig övergång och få ut det mesta av det uppdaterade användargränssnittet.
* Versionsinformation för [[!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Activities], [!UICONTROL Recommendations] och [!UICONTROL Visual Experience Composer] (VEC).
* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].
* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.
* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.
* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

+++

## [!DNL Target Standard/Premium] 25.7.3 (24 juli 2025)

På grund av nyligen identifierade problem, som främst gäller komplexa kundanpassningar, innehåller den här versionen följande korrigeringar och uppdateringar:

**Aktiviteter**

+++Se information
* Ett problem har korrigerats där metoden `buildViews` i Builder-klassen felaktigt angav `viewMaxLocalId` till det totala antalet vyer, i stället för till det högsta `viewLocalId` som tilldelats. (TGT-53207)
* Korrigerade ett problem i det uppdaterade användargränssnittet för [!DNL Target] där raderade erbjudanden i [!UICONTROL Automated Personalization] (AP) aktiviteter visades som `Deleted option with ID: X` i stället för deras ursprungliga namn (till exempel `Offer Name [Deleted]` enligt det gamla användargränssnittet). Med den här korrigeringen återställs meningsfulla etiketter för borttagna erbjudanden, vilket gör rapporteringen tydligare och mer användarvänlig. (TGT-52921)
* Ett problem har korrigerats där vissa aktiviteter som migrerades från [!DNL Target]-fronten till [!DNL Target] Central hade inkonsekventa mätkonfigurationer på grund av ett tidigare korrigerat synkroniseringsfel. Aktiviteter som ursprungligen använde ett konverteringsmått och som senare uppdaterades till ett analysbaserat mått, lagrades inaktuella värden i fälten `primaryMetricType` och `successCriteria`. (TGT-52643)
* Ett problem har korrigerats där hela innehållet på en QA-förhandsgranskningssida blev redigerbart på grund av att attributet `contentEditable` oavsiktligt inkluderades i HTML-ändringar. På så sätt kan användare klicka och redigera text på sidan, vilket kan orsaka layoutproblem och förvirring under kvalitetskontrollen. (TGT-53247)
* Ett problem har korrigerats där en ändring från [!DNL Page Load] till en [!UICONTROL View] orsakade att ändringen duplicerades, vilket fanns kvar i [!UICONTROL Page Load] samtidigt som den visades i [!UICONTROL View]. Om du dessutom tar bort ändringen från [!UICONTROL View] tas den även bort felaktigt från [!UICONTROL Page Load]. (TGT-53270)

+++

**API:er**

+++Se information
* Korrigerade ett problem i det permanenta bakgrundslagret där borttagna alternativ lagrades korrekt men inte var tillgängliga via befintliga API-slutpunkter. Därför kunde klientprogram inte hämta beskrivande namn för borttagna alternativ, vilket påverkade historiska rapportvyer. Den här korrigeringen ser till att bevarade borttagna alternativdata nu kan visas korrekt i användargränssnittet. (TGT-52973)
* Implementerade en ny migreringsslutpunkt som stöder överföring av borttagna aktivitetsalternativ från JCR-baserade aktiviteter till [!DNL Target] Central. Den här funktionen gör det möjligt att följa upp och rapportera konsekvent mellan olika system. Den här funktionen ser till att borttagna alternativ bevaras och synkroniseras över [!DNL Target] frontend och backend, vilket förbättrar den historiska rapporteringen och dataintegriteten. (TGT-53217)
* En ny API-slutpunkt introducerades som gör att användare kan återställa tidigare borttagna aktivitetsalternativ från en sekundär databas. Den här funktionen utnyttjar den befintliga infrastrukturen som tillhandahålls av klasserna `RemovedCampaignElements` och `RemovedOptionInfo`, vilket säkerställer smidig återintegrering av borttagna alternativ i aktiva aktiviteter. (TGT-52903)
* Ett problem har korrigerats där [!DNL Recommendations] aktiviteter som innehåller måttnamn som är längre än 25 tecken inte kunde öppnas eller redigeras på grund av API-begränsningar. Den här korrigeringen säkerställer kompatibilitet med metriska namn som överskrider teckengränsen och återställer fullständig åtkomst till berörda aktiviteter. (TGT-52839)

+++

**Formulärbaserad Experience Composer**

+++Se information
* Korrigerade ett fel i [!UICONTROL Form-Based Experience Composer] som gjorde att redigeraren kraschade efter att du klickade på ikonen **[!UICONTROL Manage Content]** ( ![Hantera innehåll ](/help/main/assets/icons/Experience.svg) ) när du skapade eller redigerade en [!UICONTROL Automated Personalization] -aktivitet. (TGT-53047)

+++

**Rekommendationer**

+++Se information
* Korrigerade ett problem som förhindrade [!UICONTROL Catalog Search] från att läsa in ytterligare resultat vid bläddring längst ned i listan, vilket återställde beteenden som överensstämmer med det tidigare användargränssnittet. (TGT-53088)
* Ett problem som blockerade borttagning av objekt från dialogrutan [!UICONTROL Criteria Details] har korrigerats. (TGT-53245)
* Korrigerade ett problem som förhindrade att produkter som inte hade något namn öppnades eller interagerade. Det här problemet uppstod när miljöer som returnerade namnlösa resultat valdes, vilket förhindrar åtkomst till produktinformation. (TGT-53007)
* Korrigerade ett problem som gjorde att sidan [!UICONTROL Catalog Search] kraschade och att en tom skärm visades när vissa produkter valdes. (TGT-53087)
* Ett problem har korrigerats där användare inte kunde redigera aktiviteten site_cart_z1 [!DNL Recommendation] i användargränssnittet för [!DNL Target]. Ett försök att öppna aktiviteten utlöste ett fel på sidan [!UICONTROL Overview], vilket blockerade åtkomst till redigeraren. (TGT-53221)

+++

**Rapportering**

+++Se information
* Ett problem har korrigerats där sandlådefältet i aktivitetsdatabasen inte rensades när rapportkällan växlades från [!DNL Customer Journey Analytics] eller [!DNL Analytics] till [!DNL Target]. Tidigare skickade användargränssnittet en korrekt sandlåda: null, men backend ignorerade det här värdet och lämnade inaktuella sandlådedata på plats. Backend rensar nu sandlådefältet korrekt när null tas emot. (TGT-52798)
* Återimplementerade det borttagna alternativbeständiga lagret i målserverdelen för att stödja korrekt historikrapportering i [!UICONTROL Automated Personalization] (AP)-aktiviteter. Tidigare, när ett alternativ togs bort, gick dess namn förlorat, vilket gjorde det svårt att tolka tidigare prestandadata.

  **Viktiga förbättringar**:

   * Borttagna alternativ spåras nu med den befintliga `RemovedCampaignElements`- och `RemovedOptionInfo`-infrastrukturen.
   * När ett alternativ tas bort från en AP-aktivitet bevaras dess metadata (till exempel ID och namn).
   * Rapporteringsgränssnittet kan nu visa det ursprungliga alternativnamnet (till exempel `Option Name [Deleted]`) tillsammans med historiska värden, vilket förbättrar klarheten och användbarheten.

  Denna uppdatering ger en konsekvent och meningsfull rapportering, även efter det att alternativen har tagits bort från en aktivitet. (TGT-52986)

+++

**Visual Experience Composer (VEC)**

+++Se information

* Korrigerade ett fel i VEC där en ändring av en vy orsakade duplicering och utlöste ett fel av typen&quot;Ogiltig användarinmatning&quot;. (TGT-52886)
* Ett problem med funktionen [!UICONTROL Undo] för alternativen [!UICONTROL Insert Before] och [!UICONTROL Insert After] har korrigerats vid konfiguration av bilderbjudanden i VEC.

  Om du tidigare ångrar en [!UICONTROL Insert Before]- eller [!UICONTROL Insert After]-åtgärd för bilderbjudanden uppstod ett inkonsekvent beteende eller ett fel uppstod när ändringen skulle återställas korrekt, särskilt i aktiviteter som skapades i det äldre [!DNL Target]-gränssnittet. Det här problemet har lösts för att säkerställa att ångra-åtgärder nu fungerar tillförlitligt för dessa ändringar. (TGT-52809)

* Ett problem har korrigerats där attributet `contentEditable` oavsiktligt hade angetts till true och sparades i sparat HTML-innehåll. Denna uppdatering säkerställer renare, förväntade HTML-utdata utan oönskat redigeringsbeteende. (TGT-52319)
* För att förhindra permanent förlust av borttagna alternativ och för att säkerställa ett konsekvent beteende för alla tjänster har funktionen för mjuk borttagning implementerats för alternativ i användargränssnittet och relaterade mikrotjänster.

  **Viktiga ändringar**:

   * Alternativen tas inte längre bort permanent. I stället markeras de med en ny borttagen: true-flagga i parameterns XML-objekt.
   * Den här flaggan används endast av det uppdaterade användargränssnittet för [!DNL Target] för att utesluta borttagna alternativ från återgivning och för att förhindra att de skickas till kanttjänster.
   * Borttagna alternativ är fortfarande en del av aktivitetens nyttolast under redigeringar, vilket säkerställer spårbarhet samtidigt som man undviker att ge kunderna obefintliga alternativ.

  Uppdateringen förbättrar dataintegriteten och är anpassad efter bästa praxis för hantering av borttagningar i distribuerade system. (TGT-52726)

+++

**Arbetsytor**

+++Se information
* Ett problem har korrigerats vid kopiering av en aktivitet från en icke-standardarbetsyta eller mellan icke-standardarbetsytor. Erbjudandena är nu dubblerade med förbättrad spårning och namngivning för att förhindra konflikter.

  **Viktiga förbättringar**:
   * Erbjudandena återskapas i målarbetsytan med uppdaterade ID:n och metadata.
   * Kopierade erbjudanden får nya namn i formatet:&quot;Erbjudandekopia&quot; plus ett slumpmässigt nummer eller en tidsstämpel för att säkerställa att de är unika.
   * Systemet uppdaterar erbjudanden och aktivitetstillstånd för att återspegla de nya ID:n.
   * Den här funktionen förhindrar fel som orsakas av flera identiska&quot;Erbjudandekopia&quot;-namn vid upprepade kopieringsåtgärder.
   * Erbjudandena kanske inte visas omedelbart i erbjudandelistan för målarbetsytan, utan bearbetas och visas på rätt sätt.

  Den här uppdateringen förbättrar tillförlitligheten och spårbarheten när erbjudanden hanteras på flera arbetsytor. (TGT-53080)

+++

## [!DNL Target Standard/Premium] 25.7.2 (18 juli 2025)

På grund av nyligen identifierade problem, som främst gäller komplexa kundanpassningar, innehåller den här versionen följande korrigeringar och uppdateringar:

**Aktiviteter**

+++Se information
* En ytterligare bekräftelsemeddelande har lagts till när aktivitetsredigeringar avbryts med osparade ändringar:&quot;Vill du spara den här aktiviteten? Om du inte sparar kommer alla ändringar att gå förlorade.&quot; Det här meddelandet hjälper till att förhindra dataförlust av misstag. (TGT-52865)
* Äldre funktioner återställdes till skjutreglaget [!UICONTROL Priority] i [!UICONTROL Goals & Settings], vilket gör att kunderna kan ange ett numeriskt värde direkt, vilket stöds i det äldre användargränssnittet. (TGT-53185 &amp; TGT-53219)

+++

**Publiker**

+++Se information
* Korrigerade ett problem som förhindrade att aktiviteter som innehöll anpassade målgrupper sparades eller redigerades. Kunderna fick felmeddelandet&quot;Vi kan inte slutföra din begäran. Kontakta [!DNL Adobe Client Care] om problemet kvarstår.&quot; när du försöker spara ändringar, eller till och med spara utan ändringar, i vissa aktiviteter. (TGT-53189)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Se information
* Ett problem har korrigerats när kunder visade rapporter för specifika aktiviteter på sidan [!UICONTROL Goals & Settings]. Länken [!UICONTROL View in Analytics] pekar felaktigt på QA-miljön i stället för produktionsmiljön. (TGT-53163)

+++

**[!UICONTROL Experiences]och[!UICONTROL Offers]**

+++Se information
* Ett problem har korrigerats där anrop av `triggerView` via anpassad kod orsakade en oändlig loop. (TGT-52885)
* Ett problem som orsakade avvikelser mellan `LocalIds` som definierats för aktiviteter och de `LocalIds` som används i upplevelsedefinitioner har korrigerats. (TGT-52669)
* Korrigerade ett problem där måttnamn saknades på sidan för aktiviteten [!UICONTROL Overview]. Endast erbjudandet visades i stället för det korrekta måttnamnet. (TGT-53054)

+++

**Formulärbaserad Experience Composer**

+++Se information
* Korrigerade ett fel i [!UICONTROL Form-Based Experience Composer] som hindrade aktivitetssparandet och utlöste felmeddelandet: &quot;Det går inte att läsa egenskaper för undefined (läser &#39;map&#39;)&#39;. (TGT-53145)

+++

**Rekommendationer**

+++Se information
* Ett problem har korrigerats där felet&quot;Det gick inte att hämta produktinformation&quot; visades när du klickade på en produkt från [!UICONTROL Catalog Search] och en modal öppnades utan ett stängningsalternativ. (TGT-53082)
* Ett problem har korrigerats där [rekommendationer som erbjudanden](/help/main/c-recommendations/recommendations-as-an-offer.md) i [!UICONTROL A/B Test] aktiviteter inte uppdaterades korrekt när samlingar eller kampanjer ändrades. (TGT-52884)
* Korrigerade ett problem i produktionsmiljön där ett fel visades när användaren klickade på en enhet i det uppdaterade användargränssnittet: &quot;Det gick inte att hämta produktinformation. Kontakta [!DNL Adobe Client Care] om problemet kvarstår.&quot; (TGT-53071)

+++

**Rapporter**

+++Se information
* Ett problem har korrigerats där information om sparad order till en CSV-fil resulterade i en tom fil. (TGT-52225)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Se information
* Löste ett problem på sidan [!UICONTROL Goals & Settings] där väljare som används i flera upplevelser inte markerades konsekvent som valda. (TGT-53062)
* Korrigerade ett problem som förhindrade aktivitetsredigering och utlöste felmeddelandet:&quot;Det går inte att läsa egenskaper för undefined (läsa &#39;map&#39;)&#39;. (TGT-53161)

+++

**Arbetsytor**

+++Se information
* Förbättrad hantering av ad hoc-erbjudanden vid växling av arbetsytor.
   * När du växlar från standardarbetsytan till en icke-standardarbetsyta (eller mellan icke-standardarbetsytor) kopieras ad hoc-erbjudanden nu korrekt. Under initieringen uppdateras arbetsytans kontext och ett nytt ID tilldelas till erbjudandet för att säkerställa att det är unikt.
   * Det sker inga ändringar när du stannar inom samma arbetsyta. (TGT-53079)
* Ett problem som gjorde att kunder inte kunde [kopiera aktiviteter mellan olika arbetsytor](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6) har korrigerats. (TGT-52753 &amp; TGT-47094)
* Ett problem har korrigerats vid ändring av egenskaper mellan arbetsytor.
   * Om den aktuella egenskapen finns i målarbetsytan bevaras egenskapen när du växlar mellan standardarbetsytan och en icke-standardarbetsyta.
   * Om en varning visas i listan [!UICONTROL Properties] (vilket troligtvis anger att vissa egenskaper inte är kompatibla) och kunden klickar på [!UICONTROL Add] eller [!UICONTROL Remove] och sedan klickar på [!UICONTROL Save] tas alla egenskaper som inte finns i målarbetsytan bort. Om kunden klickar på [!UICONTROL Cancel] finns alla egenskaper kvar, även om de inte finns på målarbetsytan. (TGT-47094)
   * Om du stannar kvar på samma arbetsyta eller växlar från en icke-standardarbetsyta till standardarbetsytan eller en annan arbetsyta, förblir allt som det är. (TGT-53078)
* Verifieringslogiken för entiteten har uppdaterats för att ta hänsyn till aktivitetens ursprungliga arbetsytekontext. Enheter som [!UICONTROL Experience Fragments] (XF) valideras nu baserat på arbetsytan som aktiviteten ursprungligen skapades i. Om det till exempel finns en XF-fil på standardarbetsytan och aktiviteten kopieras från arbetsytan X till arbetsytan Y, går valideringen ändå så länge som XF-filen är giltig på den ursprungliga arbetsytan (standardarbetsytan). (TGT-53196)
* Förbättrat stöd för kopiering av ad hoc-målgrupper vid duplicering av aktiviteter.
   * Ad hoc-målgrupper, inklusive statistik, rapportering, sida och endast aktivitet, kopieras nu automatiskt i följande scenarier:
      * När du kopierar en aktivitet från standardarbetsytan till en icke-standardarbetsyta.
      * När du kopierar en aktivitet inom samma arbetsyta. (TGT-53197)

+++

## [!DNL Target Standard/Premium] 25.7.1 (11 juli 2025)

På grund av nyligen identifierade problem, som främst gäller komplexa kundanpassningar, innehåller den här versionen följande korrigeringar och uppdateringar:

**Aktiviteter**

+++Se information
* Ett problem har korrigerats där URL:en [!UICONTROL Activity QA] innehöll en onödig frågeparameter: `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Ett problem har korrigerats där URL:er för förhandsgranskning felaktigt inkluderade fler målgrupper än den som användaren uttryckligen angav. Detta beteende har korrigerats för att säkerställa att endast den angivna målgruppen används när en QA- eller förhandsgranskningslänk genereras. (TGT-52912)
* Korrigerade ett problem som förhindrade användare från att skapa [!UICONTROL Auto-Target] (AT) aktiviteter om [!UICONTROL Auto-Allocate] (AA) väljs först under konfiguration av trafikallokering. Säkerhetsluckan resulterade i ett serverdelsvalideringsfel som förhindrar att aktiviteten sparas. (TGT-53096)

+++

**Publiker**

+++Se information
* Ett problem har korrigerats där användare med rollen [!UICONTROL Approver] inte kunde lägga till eller spara målgruppsförbättringar enbart för aktivitet. Ett försök att göra detta resulterade i ett 403-fel som anger att privilegiet [editor] krävdes, även om användaren hade tillräcklig behörighet för att godkänna och hantera aktiviteter. (TGT-52984)
* Ett problem har korrigerats när en aktivitetsspecifik målgrupp tas bort med alternativet [!UICONTROL Remove Audience Refinement]. Publiken visas inte längre i målgruppslistan för omval inom samma aktivitet. Det här beteendet hindrade användare från att lägga till samma målgrupp på nytt om de inte återskapar den från grunden. (TGT-52979)
* Korrigerade ett problem där endast aktivitetsspecifika målgruppsförbättringar försvann från användargränssnittet omedelbart efter att de tagits bort från en plats, även innan aktiviteten sparades. Detta beteende stred mot den förväntade funktionen och riktlinjerna för verktygstips, som anger:&quot;Alla oanvända målgrupper från det här biblioteket tas bort när aktiviteten sparas.&quot; (TGT-52982)
* Ett problem har korrigerats vid försök att tilldela en annan målgrupp än [!UICONTROL All Visitors] till en aktivitet. När du sparar visas följande felmeddelande:&quot;Vi kan inte slutföra din begäran. Kontakta [!UICONTROL Adobe Client Care] om problemet kvarstår.&quot; (TGT-53008)
* Korrigerade ett problem som blockerade sparandet av en aktivitet efter att en ny målgrupp har skapats och tilldelats i aktivitetsredigeraren. Felmeddelandet som visades var:&quot;Vi kan inte slutföra din begäran. Kontakta [!UICONTROL Adobe Client Care] om problemet kvarstår.&quot; (TGT-52977)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Se information
* Ett problem har korrigerats där kopiering av en befintlig aktivitet och ändring av rapportkällan till [!DNL Adobe Analytics] (A4T) skulle resultera i ett felaktigt indatafel. Felet utlöstes när vissa måttåtgärder som är inkompatibla med [!DNL Analytics]-rapportering, som `restart_same_experience`, `restart_random_experience` och `restart_new_experience`, behålls från den ursprungliga aktiviteten. (TGT-52900)
* Korrigerade ett problem som hindrade kunder från att skapa eller spara en aktivitet när de valde [!DNL Adobe Analytics] (A4T) som rapportkälla i [!UICONTROL Goals & Settings] -steget. Problemet uppstod när ett [!UICONTROL Custom Event]-mått valdes (till exempel &quot;Egen händelse 16&quot;), vilket resulterade i följande fel: &quot;Ogiltigt användarinvärde.&quot; (TGT-52910)
* Ett problem har korrigerats där användaren omdirigerades till hemsidan i stället för till den avsedda [!UICONTROL View in Analytics]-instrumentpanelen när användaren klickade på länken [!DNL Analytics]. (TGT-53092 &amp; TGT-53093)
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* Ett problem som uppstod när en [!DNL Recommendations]-aktivitet skulle visas i det uppdaterade [!UICONTROL Overview]-gränssnittet, kunde inte läsas in i [!UICONTROL Goals & Settings]-avsnittet när [!DNL Adobe Analytics] (A4T) har valts som rapportkälla har åtgärdats. Följande felmeddelande visades: &quot;Något gick fel. Vi kan inte slutföra din begäran. Kontakta Adobe Client Care om problemet kvarstår.&quot; (TGT-52999)

+++

**[!UICONTROL Experiences]och[!UICONTROL Offers]**

+++Se information
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* Ett problem har korrigerats där funktionen [!UICONTROL Manage Content] inte validerade läget för en plats korrekt efter att alla innehållsalternativ tagits bort. Detta kan leda till inkonsekvent beteende eller fel när du försöker spara eller fortsätta med aktivitetskonfigurationen. (TGT-52801)
* Korrigerade ett problem där användare påträffade ett &quot;Ogiltigt indatafel&quot; när de lade till en ny sida och tog bort specifika element i olika upplevelser. Felet utlöses av att dubbletten `LocalIds` genereras under elementredigering, särskilt när du växlar mellan upplevelser och ändrar delade sidstrukturer. (TGT-52720)
* Ett problem har korrigerats där funktionen [!UICONTROL Generate Adhoc Offer] resulterade i att odefinierade platser visades på panelen [!UICONTROL Manage Content]. (TGT-53076 &amp; TGT-53070)
* Beteendet klarlades för kunden där ändringar som gjorts med ett HTML-erbjudande verkar saknas vid navigering från [!UICONTROL Targeting]-steget tillbaka till [!UICONTROL Experiences]. För den här kunden genererade den berörda webbplatsen dynamiskt flera DOM-väljare som ändrades vid inläsningen av varje sida. Därför går det inte att hitta den väljare som ursprungligen användes för ändringen när redigeraren öppnas igen, vilket gör att ändringen verkar saknas eller vara ogiltig. Scenariot fungerar som det ska. För att ändringarna ska finnas kvar visuellt i redigeraren rekommenderar vi att kunderna använder stabila, konsekventa väljare som inte ändras vid sidomladdning. (TGT-52874)
* Ett problem har korrigerats där ett försök att ta bort eller inaktivera ett erbjudande som var en del av en utesluten upplevelse utlöste felet&quot;Ogiltig användarinmatning&quot;. Problemet uppstod trots att erbjudandet inte användes aktivt i de inkluderade upplevelserna. (TGT-52917)

+++

**Formulärbaserad Experience Composer**

+++Se information
* Korrigerade ett problem i formulärbaserade aktiviteter där dubblering av en upplevelse och redigering av den anpassade koden i en av de duplicerade upplevelserna oavsiktligt skulle tillämpa dessa ändringar på alla duplicerade upplevelser. Varje upplevelse behåller nu sin egen anpassade kod oberoende av varandra efter duplicering. (TGT-51600)

+++

**Lokalisering**

+++Se information
* Uppdaterade lokaliseringssträngar i det nya användargränssnittet för franska (fr_FR), tyska (de_DE), italienska (it_IT), koreanska (ko_KO) och förenklad kinesiska (zh_CN).

+++

**[!DNL Recommendations]**

+++Se information
* En ny [!DNL Recommendations] feed [status](/help/main/c-recommendations/c-products/feeds.md#status) har lagts till: [!UICONTROL Partial Import Failed]. (KB-2215)
* Ett problem som påverkade arbetsflödet för aktivitetsskapande när [!DNL Recommendations] lades till med [!UICONTROL promotions] har korrigerats. När användare markerade [!UICONTROL Promote by Attribute] och lade till en filtreringsregel (till exempel [!UICONTROL Parameter Matching]), behålldes inte den valda regeltypen och operandvärdena efter att aktiviteten sparats och redigerats om. När filterregeltypen öppnas igen ändras den oväntat och operandvärden saknas. (TGT-53059)
* Korrigerade ett fel i användargränssnittet för [!DNL Recommendations] där en befordran som skapats med en enskild regel tolkades felaktigt och visades som en erbjudandetyp för&quot;Lista över artiklar&quot;, oavsett regelns logik. (TGT-53063)
* Ett problem har korrigerats när det uppdaterade [!UICONTROL Overview]användargränssnittet [!UICONTROL Download Recommendations Data]-knappen saknades för [!UICONTROL Experience Targeting] (XT)-aktiviteter som innehåller [!DNL Recommendations]. (TGT-52730 &amp; TGT-52756)
* Tidigare visades bara antalet enheter som importerades från en feed i gränssnittet Rekommendationer. Däremot innehåller backend-meddelandeformatet både antalet importerade entiteter och det totala antalet entiteter i formatet: `# of entities imported / # of total entities`. På grund av den här diskrepansen kunde användare bara se det första värdet (antal importerade) i användargränssnittet, vilket ledde till förvirring. Nu visas båda talen i användargränssnittet. (TGT-53073)
* Ett problem har korrigerats där kunder inte kunde spara en filtreringsregel när en [!UICONTROL Promote by attribute]-kampanj konfigurerades i en formulärbaserad A/B-aktivitet med rekommendationer. När aktiviteten har sparats och öppnats igen saknades filtreringsregeln och det gick inte att spara aktiviteten. (TGT-53057)

+++

**Rapporter**

+++Se information
* Ett problem har korrigerats där [!UICONTROL Export order details to CSV] från sidan [!UICONTROL Reports] resulterade i att en tom fil hämtades. Problemet uppstod även när giltiga orderdata fanns i aktiviteten. (TGT-52225)
* Ett problem som uppstod när en aktivitet skulle sparas efter att en ny rapportpublik har skapats och tilldelats. Felmeddelandet som returnerades var: &quot;Åtkomst nekad. För att kunna utföra den här åtgärden krävs alla följande behörigheter: [editor].&quot; Problemet uppstod trots att användaren har åtkomst på godkännarnivå. (TGT-53103)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Se information
* Ett problem har åtgärdats där en ändring av en vy skulle medföra att vyn dupliceras och att aktiviteten returnerade ett &quot;Ogiltigt indatafel från användaren&quot;. Med den här korrigeringen säkerställs att vyändringarna tillämpas på rätt sätt utan att utlösa duplicerings- eller valideringsfel. (TGT-52886)
* Ett problem har korrigerats där anpassade kodändringar felaktigt visades för fel upplevelse. I synnerhet har förändringar avsedda för en upplevelse visat sig i en annan upplevelse, vilket lett till förvirring och potentiell misskonfiguration av aktiva aktiviteter. (TGT-52776)
* Ett problem som gjorde att det inte gick att redigera eller spara anpassade kodändringar i det nya VEC-gränssnittet har korrigerats. Mer specifikt:

   * När du har redigerat ett anpassat kodblock och sparat återspeglas inte ändringarna i användargränssnittet eller i QA-förhandsvisningen.
   * I vissa fall gick det inte att ta bort ändringarna om inte aktiviteten stängdes och öppnades igen.
   * Som en tillfällig lösning måste användarna kopiera koden, ta bort ändringen och återskapa den manuellt med det uppdaterade innehållet. (TGT-53072)

* Ett problem har korrigerats där redigering och sparande av anpassad kod gjorde att panelen [!UICONTROL Modifications] inte svarade. (TGT-53075)
* Ett problem har korrigerats där ändringar av anpassad kod i olika upplevelser av misstag återspeglades i [!UICONTROL Control]-upplevelsen. Detta orsakade oönskade förändringar av leveransbeteendet. [!UICONTROL Control]-upplevelsen är nu fortfarande isolerad från anpassade kodredigeringar som gjorts i andra upplevelser. (TGT-52413)
* Korrigerade ett problem där ändringar som gjorts i en upplevelse (till exempel Experience B) oavsiktligt duplicerades till en annan upplevelse (Experience A) om användaren klickade på den andra upplevelsen innan redigeraren var helt inläst. Detta beteende kan också leda till att ändringar går förlorade om den upplevelse som du valde först inte hade några ändringar. (TGT-52597)
* Ett problem har korrigerats där ändringar som gjorts i steget [!UICONTROL Modifications] när aktiviteten skapades inte sparades konsekvent. När du har slutfört alla steg och klickat på [!UICONTROL Save] återspeglas i vissa fall inte det anpassade skript som lagts till i avsnittet [!UICONTROL Modifications] på den aktiva webbplatsen, trots att inga synliga fel uppstod under sparandet. (TGT-52661)
* Korrigerade ett problem där anpassade kodändringar inte sparades korrekt och av misstag speglades över flera upplevelser inom samma aktivitet. Dessutom stötte användare på åtkomstproblem när vissa aktiviteter öppnades eller uppdaterades, vilket resulterade i tomma skärmar. Dessa problem har nu åtgärdats för att säkerställa stabil aktivitetsredigering och korrekt upplevelseisolering. (TGT-52594)
* Ett problem har korrigerats där användare inte kunde bläddra till en annan URL i [!UICONTROL Browse Mode]. Detta hindrade testare och redigerare från att validera eller förhandsgranska alternativa sidor i samma aktivitetssession. (TGT-53052)
* Ett problem har korrigerats där flera [!UICONTROL Visual Experience Composer] (VEC)-instanser öppnades samtidigt när aktiviteten skapades. Problemet uppstod när användare inaktiverade [!UICONTROL Enhanced Experience Composer] (EEC) och tog bort det avslutande snedstrecket från webbplatsens URL i [!UICONTROL Page Delivery]-steget. (TGT-52782)
* Ett problem har korrigerats där den [!UICONTROL Revenue]-metriska listrutan i [!UICONTROL Goals & Settings]-steget felaktigt skulle ha standardvärdet [!UICONTROL Revenue per Visit] (RPVISIT), även efter att användaren har valt ett annat mått.  Problemet uppstod när panelen för metrisk konfiguration komprimerades och utökades på nytt, vilket gjorde att det tidigare valda värdet återställdes. (TGT-52811 &amp; TGT-52878)
* Flera problem har korrigerats i arbetsflödet för att skapa aktivitet relaterade till namngivning och innehållsöversättning i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Multivariate Testing] (MVT)-aktiviteter:

  Viktiga problem som åtgärdats:

   * Om du skapade flera HTML-erbjudanden med samma namn (till exempel &quot;Upplevelse&quot;) utlöstes felet &quot;Duplicera erbjudandenamn tillåts inte&quot;, men gränssnittet visade inte tydligt vilka erbjudanden som orsakade konflikten.
   * När du ändrade namn på erbjudanden via den högra panelen uppdaterades namnet i användargränssnittet, men ändringen återspeglades inte på fliken [!UICONTROL Manage Content] eller [!UICONTROL Offers], vilket orsakar permanenta valideringsfel.
   * I MVT-aktiviteter, trots att dubblettnamnsfelet inte kvarstod efter namnbytet, kunde användargränssnittet fortfarande inte återge uppdaterade erbjudandenamn på ett konsekvent sätt på alla flikar. (TGT-52933)

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
