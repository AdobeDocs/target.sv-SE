---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6ecc59588b51da505b8f567a7e87ccef0f375477
workflow-type: tm+mt
source-wordcount: '1959'
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
* **Enhetlig aktivitetsinformation**: De senaste ändringarna, oavsett vilket användargränssnitt du använder, visas på din aktiva webbplats. Det gamla användargränssnittet visar dock bara de senaste ändringarna som gjorts i den versionen. Den här situationen kan orsaka förvirring om aktiviteter som redigeras i det uppdaterade användargränssnittet ser annorlunda ut än i det äldre användargränssnittet.

#### Fler resurser att lära sig om det uppdaterade användargränssnittet

* [[!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md): Här behandlas vanliga frågor om det nya [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC), inklusive navigeringsändringar, funktionsplatser och borttagning av den tillfälliga användargränssnittsversionen. Vare sig du är marknadsförare, utvecklare eller administratör kan du med de här vanliga frågorna få en smidig övergång och få ut det mesta av det uppdaterade användargränssnittet.
* Versionsinformation för [[!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Activities], [!UICONTROL Recommendations] och [!UICONTROL Visual Experience Composer] (VEC).
* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].
* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.
* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.
* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

+++

## [!DNL Target Standard/Premium] 25.8.1 (7 augusti 2025)

Den här versionen innehåller följande förbättringar och korrigeringar:

**Aktiviteter**

+++Se information
* Korrigerade flera problem med det uppdaterade användargränssnittet, bland annat fel vid borttagning av sidtyper på grund av mellanrum i indatavärden, otillförlitlig aktivitetskopiering mellan arbetsytor och felfungerande regler för sidleverans i QA-miljöer. (TGT-52703)
* Ett problem har korrigerats i det uppdaterade användargränssnittet för [!DNL Target] där användare med rollen [!UICONTROL Editor] kunde komma åt och försöka redigera aktiva aktiviteter, vilket borde begränsas. Aktivitetslistan och översiktsskärmarna visade felaktigt redigeringsalternativ för aktiva aktiviteter, vilket kan leda till oavsiktliga ändringar. (TGT-53055)
* Ett problem har korrigerats i användargränssnittet för [!UICONTROL Advanced Search] där användaren uppmanades att ange en operand genom att välja &quot;värdet finns&quot; eller &quot;värdet finns inte&quot;, vilket inte bör vara nödvändigt för dessa villkor. (TGT-51961)
* Korrigerade ett problem i det uppdaterade användargränssnittet där försök att kopiera aktiviteter från mellanlagringen till produktionsytan genomgående misslyckades, även i sandlådemiljöer. Kunderna fick olika felmeddelanden, bland annat&quot;Anonym publik som redan används av aktiviteten&quot; och&quot;Ogiltigt målar-ID&quot;, trots att giltiga konfigurationer och lämpliga behörigheter för arbetsytan används. (TGT-52394)

+++

**Upplevelsefragment (XF)**

+++Se information
* Ett problem har korrigerats där Experience Fragment-innehåll (XF) inte kan återges i förhandsvisningen av [!UICONTROL Visual Experience Composer] (VEC) trots att det fungerar korrekt vid innehållsleverans. (TGT-53318)

+++

**Lokalisering**

+++Se information
* Ett lokaliseringsfel har korrigerats där knappen&quot;Lägg till erbjudande&quot; i avsnittet&quot;Kampanjer&quot; inte fanns översatt i flera språkmiljöer i QA-klienten. (TGT-53263)

+++

**Erbjudanden**

+++Se information
* Ett problem har korrigerats där redigering av ett befintligt HTML-erbjudande via Visual Experience Composer (VEC) gjorde att alla ändringar togs bort från innehållsleveransen. Ändringarna visas som nedtonade på ändringsfliken och återspeglas inte i QA-förhandsvisningar, trots att de tillämpas korrekt i det äldre användargränssnittet. (TGT-52863)
* Korrigerade ett fel i det uppdaterade användargränssnittet för [!DNL Target] där HTML inte längre erbjuder ändringar gjorda i [!UICONTROL Visual Experience Composer] (VEC) efter att du navigerat från fliken [!UICONTROL Targeting] till [!UICONTROL Experiences]. (TGT-52874)
* Korrigerade ett fel i det uppdaterade användargränssnittet för [!DNL Target] där infogning av ett HTML-erbjudande före och ett annat efter samma väljare orsakade felaktig platsgenerering. När kunder returnerades från fliken [!UICONTROL Targeting] till fliken [!UICONTROL Experience] kvarstod bara en väljare, vilket resulterade i förlorade ändringar och bruten innehållsleverans. Det här beteendet skiljer sig från det gamla användargränssnittet, som bevarar båda ändringarna korrekt med distinkta platsidentifierare. (TGT-52891)
* Korrigerade ett problem i det uppdaterade användargränssnittet för [!DNL Target] där ett klickat på ett tillagt erbjudande i [!UICONTROL Modifications] -rälen fick den högra panelen [!UICONTROL Configuration] att visas och försvinna då och då, vilket gjorde det svårt att interagera med erbjudandeinställningarna. (TGT-53288)
* Ett problem har korrigerats där HTML erbjudanden som lagts till i målgruppsspecifika variationer i en aktivitet inte sparades konsekvent eller visades i ändringsavsnittet. Efter att ha växlat mellan olika målgrupper under redigeringen försvinner eller misslyckas tidigare erbjudanden, vilket stör valideringen och försenar beredskapen för aktiviteter. (TGT-53440)
* Ett problem har korrigerats där kopiering av en aktivitet som innehöll erbjudanden resulterade i att dubblerade erbjudanden skapades i den nya aktiviteten. Det här beteendet orsakade onödig störning och förvirring, särskilt när du flyttade aktiviteter mellan arbetsytor. Korrigeringen säkerställer att [!DNL Target] erbjudanden nu kopieras korrekt till målarbetsytan utan dubbletter, vilket effektiviserar aktivitetshanteringen och förbättrar arbetsflödets effektivitet. (TGT-53454)

+++

**Single Page Applications (SPA)**

+++Se information
* Korrigerade ett fel i den uppdaterade VEC som förhindrade kunder från att tillämpa ändringar i [!UICONTROL Single Page Application]-vyer (SPA). Aktiviteter som skapats i det gamla användargränssnittet har stöd för vyspecifik målanpassning, men det nya användargränssnittet kunde inte identifiera eller tillåta redigering av dessa vyer. Kontrollerna för visningsväxling är inaktiverade. (TGT-52556)

+++

**Visual Experience Composer (VEC)**

+++Se information
* Ett problem har korrigerats där ändringar som gjorts i upplevelser i [!UICONTROL Visual Experience Composer] antingen inte var synliga eller visades inkonsekvent i användargränssnittet. (TGT-TGT-53381)
* Korrigerade ett fel i den uppdaterade VEC där avsnittet [!UICONTROL Manage Content] inte kunde visa alternativ text för upplevelseminiatyrer. Det här problemet gjorde det svårt för användare att identifiera dokument, särskilt när filnamnen var långa eller trunkerade. (TGT-52291)
* Ett fel har korrigerats där kunder påträffade felaktiga valideringsfel när [!UICONTROL page delivery]-regler konfigurerades i VEC-aktiviteter. Operatorer som &quot;equals any of&quot; och &quot;does not equal any of&quot; utlöste &quot;Invalid input for the operator type&quot; vid inmatning av textvärden, trots att text bör stödjas. (TGT-52629)
* Korrigerade flera problem som orsakade inkonsekvent beteende på panelen [!UICONTROL Modifications] i det uppdaterade användargränssnittet när erbjudanden valdes med knappen Välj ett erbjudande. I stället för att ersätta det befintliga erbjudandet lade användargränssnittet till en dubblett, och försöket att interagera med båda erbjudandena resulterade i konsolfel som `selectorNotFound`. Dessutom visas inte knappen Välj ett erbjudande i vissa erbjudanden, där endast redigerbara egenskaper visas. (TGT-53321)
* Korrigerade ett fel i det uppdaterade användargränssnittet för [!DNL Target] där HTML-kodändringar som gjorts under aktivitetsinställningarna inte fanns kvar på variantsidorna trots att de sparades korrekt för kontrollgrupper. Trots flera försök och återskapande av tester utan sidgrupperingar misslyckades variationssidorna genomgående att behålla ändringarna, vilket påverkade innehållsleveransen och QA-valideringen. (TGT-53436)
* Korrigerade ett fel i den uppdaterade VEC där &quot;equals any of&quot;-operatorn i regler för sidleverans inte accepterar indatavärden. När kundparametrar konfigurerades för alla kryssrutor resulterade valet av den här operatorn i felet&quot;Ogiltig inmatning&quot;, vilket förhindrar att regler skapas. (TGT-52623)

+++

**Arbetsytor**

+++Se information
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
