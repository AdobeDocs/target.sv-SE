---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e612ec5814c931349699b6b4d2c9fa71b493413c
workflow-type: tm+mt
source-wordcount: '2594'
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
* **Redigera befintliga aktiviteter**: Ändringar som gjorts i befintliga aktiviteter (som ursprungligen skapades i det äldre användargränssnittet) när det uppdaterade användargränssnittet används kommer att publiceras på webbplatsen. De här uppdateringarna visas dock inte i det gamla användargränssnittet om du byter tillbaka. Endast de senaste uppdateringarna från det gamla användargränssnittet visas där.
* **Enhetlig aktivitetsinformation**: De senaste ändringarna, oavsett vilket användargränssnitt du använder, visas på din aktiva webbplats. Det gamla användargränssnittet visar dock endast de senaste ändringarna som gjorts i den versionen. Detta kan orsaka förvirring om aktiviteter som redigeras i det uppdaterade användargränssnittet ser annorlunda ut än i det äldre användargränssnittet.

#### Fler resurser att lära sig om det uppdaterade användargränssnittet

* [[!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md): Här behandlas vanliga frågor om det nya [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC), inklusive navigeringsändringar, funktionsplatser och borttagning av den tillfälliga användargränssnittsversionen. Vare sig du är marknadsförare, utvecklare eller administratör kan du med de här vanliga frågorna få en smidig övergång och få ut det mesta av det uppdaterade användargränssnittet.
* Versionsinformation för [[!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Activities], [!UICONTROL Recommendations] och [!UICONTROL Visual Experience Composer] (VEC).
* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].
* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.
* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.
* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

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
* Korrigerade ett problem där användare påträffade ett &quot;Ogiltigt indatafel&quot; när de lade till en ny sida och tog bort specifika element i olika upplevelser. Felet utlöstes av att dubbletten `LocalIds` genererades under elementmanipuleringen, särskilt när du växlar mellan upplevelser och ändrar delade sidstrukturer. (TGT-52720)
* Ett problem har korrigerats där funktionen [!UICONTROL Generate Adhoc Offer] resulterade i att odefinierade platser visades på panelen [!UICONTROL Manage Content]. (TGT-53076 &amp; TGT-53070)
* Beteendet klarlades för kunden där ändringar som gjorts med ett HTML-erbjudande verkar saknas vid navigering från [!UICONTROL Targeting]-steget tillbaka till [!UICONTROL Experiences]. För den här kunden genererade den berörda webbplatsen dynamiskt flera DOM-väljare som ändrades vid inläsningen av varje sida. Därför går det inte att hitta den väljare som ursprungligen användes för ändringen när redigeraren öppnas igen, vilket gör att ändringen verkar saknas eller vara ogiltig. Detta fungerar som avsett. För att ändringarna ska finnas kvar visuellt i redigeraren rekommenderar vi att kunderna använder stabila, konsekventa väljare som inte ändras vid sidomladdning. (TGT-52874)
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
* Ett problem har korrigerats där den [!UICONTROL Revenue]-metriska listrutan i [!UICONTROL Goals & Settings]-steget felaktigt skulle ha standardvärdet [!UICONTROL Revenue per Visit] (RPVISIT), även efter att användaren har valt ett annat mått.  ett problem uppstod när panelen för metrisk konfiguration komprimerades och utökades på nytt, vilket gjorde att det tidigare valda värdet återställdes. (TGT-52811 &amp; TGT-52878)
* Flera problem har korrigerats i arbetsflödet för att skapa aktivitet relaterade till namngivning och innehållsöversättning i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Multivariate Testing] (MVT)-aktiviteter:

  Viktiga problem som åtgärdats:

   * Om du skapade flera HTML-erbjudanden med samma namn (till exempel &quot;Upplevelse&quot;) utlöstes felet &quot;Duplicera erbjudandenamn tillåts inte&quot;, men gränssnittet visade inte tydligt vilka erbjudanden som orsakade konflikten.
   * När du ändrade namn på erbjudanden via den högra panelen uppdaterades namnet i användargränssnittet, men ändringen återspeglades inte på fliken [!UICONTROL Manage Content] eller [!UICONTROL Offers], vilket orsakar permanenta valideringsfel.
   * I MVT-aktiviteter, trots att dubblettnamnsfelet inte kvarstod efter namnbytet, kunde användargränssnittet fortfarande inte återge uppdaterade erbjudandenamn på ett konsekvent sätt på alla flikar. (TGT-52933)

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
