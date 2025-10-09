---
keywords: målanvändargränssnitt;användargränssnitt;ui;vanliga frågor;faq
description: Frågor och svar om det uppdaterade användargränssnittet i [!DNL Target]t.
title: Var kan jag hitta vanliga frågor om det uppdaterade  [!DNL Target] användargränssnittet?
feature: Overview
exl-id: 75db4791-ca51-472d-99dd-583f7a74b222
source-git-commit: 6cba2e93d61d3044d1bf7ce2f5bb6cc1f2d71e4a
workflow-type: tm+mt
source-wordcount: '1875'
ht-degree: 0%

---

# [!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering

Nytt 2025 är det omdesignade användargränssnittet i [!DNL Adobe Target] som ger en renare och mer intuitiv upplevelse för alla användare. Vanliga frågor och svar täcker viktiga uppdateringar av [!DNL Target]-gränssnittet och [!UICONTROL Visual Experience Composer]-gränssnittet (VEC), inklusive navigeringsändringar, funktionsplaceringar och borttagning av den tillfälliga gränssnittsväxlingen. Oavsett om du är marknadsförare, utvecklare eller administratör är det din guide till en smidig övergång och smartare arbetsflöden.

## Har tidslinjen för borttagning av växling för målanvändargränssnittsversion uppdaterats?

+++Se detaljer
[!DNL Target]-teamet erbjuder en tillfällig funktion som gör att du kan växla mellan det uppdaterade [!DNL Target]-användargränssnittet och den äldre versionen med en växlingsknapp. Det här alternativet är endast tillgängligt under den sista fasen av UI-utrullningen.

![Växla mellan målgränssnittsversion](/help/main/r-release-notes/assets/toggle.png)

När utrullningen är klar tas växlingsknappen bort och alla användare övergår permanent till det uppdaterade användargränssnittet. [!DNL Adobe] rekommenderar planering i förväg eftersom den här funktionen kommer att fasas ut snart.

### Tidslinje för borttagning

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

### Begränsningar för användargränssnittets växlingsbeteende {#limitations}

Följande information beskriver de begränsningar som du bör vara medveten om när du väljer att använda versionsväxlingen:

* **Synlighet för nya aktiviteter**: Aktiviteter som har skapats i det uppdaterade användargränssnittet visas inte om du växlar tillbaka till det gamla användargränssnittet.
* **Redigera befintliga aktiviteter**: Ändringar som gjorts i befintliga aktiviteter (som ursprungligen skapades i det äldre användargränssnittet) när det uppdaterade användargränssnittet används publiceras på webbplatsen. Dessa uppdateringar visas dock inte i det gamla användargränssnittet om du byter tillbaka. Där visas bara de senaste uppdateringarna från det gamla användargränssnittet.
* **Enhetlig aktivitetsinformation**: De senaste ändringarna, oavsett vilket användargränssnitt du använder, visas på din aktiva webbplats. Det gamla användargränssnittet visar dock bara de senaste ändringarna som gjorts i den versionen. Den här situationen kan orsaka förvirring om aktiviteter som redigeras i det uppdaterade användargränssnittet ser annorlunda ut än i det äldre användargränssnittet.

### Fler resurser att lära sig om det uppdaterade användargränssnittet

* [[!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md): Här behandlas vanliga frågor om det nya [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC), inklusive navigeringsändringar, funktionsplatser och borttagning av den tillfälliga användargränssnittsversionen. Vare sig du är marknadsförare, utvecklare eller administratör kan du med de här vanliga frågorna få en smidig övergång och få ut det mesta av det uppdaterade användargränssnittet.
* Versionsinformation för [[!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Activities], [!UICONTROL Recommendations] och [!UICONTROL Visual Experience Composer] (VEC).
* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].
* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.
* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.
* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

+++

## Var finns mer information om det uppdaterade användargränssnittet för [!DNL Target]?

+++Information
Följande resurser innehåller information om det uppdaterade användargränssnittet för [!DNL Target]:

* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].

* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.

* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.

* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

+++

## Är det uppdaterade användargränssnittet tillgängligt för alla aktuella [!DNL Target]-kunder, [!UICONTROL Standard] och [!UICONTROL Premium]?

+++Information
Det uppdaterade användargränssnittet är tillgängligt för alla [!DNL Target]-kunder, [!UICONTROL Standard] och [!UICONTROL Premium]. Ingen uppgraderad licens eller SKU krävs.

Mer information om utrullning och borttagning av den tillfälliga gränssnittsversionen finns i [Tidskänsliga uppdateringar som du behöver känna till](/help/main/r-release-notes/release-notes.md#time-sensitive).

+++

## Kommer den aktuella listan med fel att korrigeras innan det gamla användargränssnittet har tagits bort?

+++Information
[!DNL Target]-teamet arbetar aktivt med problem som rör den nya UI-utrullningen. Uppdateringar och pågående förbättringar beskrivs i versionsinformationen.

Mer information om utrullning och borttagning av den tillfälliga gränssnittsversionen finns i [Tidskänsliga uppdateringar som du behöver känna till](/help/main/r-release-notes/release-notes.md#time-sensitive).

+++

## Kan kunder ansöka om att användargränssnittets version ska behållas för sina konton om de föredrar att behålla det gamla användargränssnittet?

+++Information
Användargränssnittsversionen är en tillfällig funktion som gör att du kan växla mellan det uppdaterade [!DNL Target]-användargränssnittet och den äldre versionen med en växlingsknapp. Det här alternativet är endast tillgängligt under den sista fasen av UI-utrullningen. När utrullningen är klar tas växlingsknappen bort och alla användare övergår permanent till det uppdaterade användargränssnittet.

Det finns flera begränsningar för att använda växlingsknappen för användargränssnittsversionen, inklusive synlighet för nya aktiviteter, redigering av befintliga aktiviteter och konsekvens i aktivitetsinformationen.

Mer information finns i [Tidskänsliga uppdateringar som du behöver känna till](/help/main/r-release-notes/release-notes.md#time-sensitive).

++++

## Kan [!DNL Adobe] fördröja migreringen till det uppdaterade användargränssnittet tills den fullständiga utrullningen är klar?

+++Information
[!DNL Target] erbjuder inte möjlighet att fördröja eller anpassa tidpunkten för gränssnittsmigreringarna. Kunderna övergår i faser och utrullningsschemat hanteras av [!DNL Adobe]. Information om de senaste uppdateringarna finns i versionsinformationen.

Det finns flera begränsningar för att använda växlingsknappen för användargränssnittsversionen, inklusive synlighet för nya aktiviteter, redigering av befintliga aktiviteter och konsekvens i aktivitetsinformationen.

Mer information finns i [Tidskänsliga uppdateringar som du behöver känna till](/help/main/r-release-notes/release-notes.md#time-sensitive).

+++

## Hur hanterar den uppdaterade VEC-funktionen alternativen för att ordna om, ändra storlek, flytta, dölja och ta bort och hur skiljer sig dessa alternativ från den gamla VEC-versionen? {#options}

+++Information
**[!UICONTROL Rearrange*]*: I den gamla VEC-funktionen användes en övertäckning för att låta användare flytta ett element inom samma grupp. Rörelsen begränsades till att ändra ordningen mellan element på samma nivå.

I den uppdaterade VEC-funktionen effektiviseras den genom åtgärder som går framåt och bakåt. Med de här kontrollerna justeras ett elements position i layouten, både vågrätt och lodrätt, genom att det flyttas framåt eller bakåt i staplingsordningen.

**Ändra storlek**: Funktionen [!UICONTROL Resize] finns i panelen [!UICONTROL Properties] under avsnittet [!UICONTROL Size]. Användare kan justera ett elements bredd och höjd direkt. Avancerade inställningar:

* Kontroller för min-/maxbredd och höjd
* Beteendeinställningar för spill.
* Alternativ för objektpassning för mediaelement

De här verktygen ger exakt kontroll över elementets dimensioner och layoutbeteende.

**Flytta**: Alternativet [!UICONTROL Move] finns i panelen [!UICONTROL Properties] under avsnittet [!UICONTROL Position]. Med det här alternativet kan användare:

* Ange elementets position (till exempel absolut, relativ, fast)
* Definiera z-index för lager
* Välja en placeringstyp

Den uppdaterade [!UICONTROL Properties]-rälen har även stöd för anpassade infogade format, vilket ger flexibilitet när förinställda alternativ inte uppfyller layoutbehoven.

**[!UICONTROL Hide]**: Funktionen [!UICONTROL Hide] finns på panelen [!UICONTROL Properties]. När du har markerat ett element klickar du på [!UICONTROL Hide Element] för att ta bort det från vyn utan att ta bort det. Detta är användbart när du vill hantera synlighet under design eller förhandsgranskning.

**[!UICONTROL Remove]**: Funktionen [!UICONTROL Remove] är tillgänglig via panelen [!UICONTROL Properties]. När du har markerat ett element klickar du på Ta bort element för att ta bort det från sidan. Den här åtgärden tar bort elementet permanent från layouten.

+++

## Kan jag komprimera [!UICONTROL Components]-, [!UICONTROL Modifications]- och [!UICONTROL Properties]-skenorna så att jag kan förstora [!UICONTROL Design]-panelen? {#collapse}

+++Information

Ja, du kan komprimera de här skenorna så att du kan expandera arbetsytan i [!UICONTROL Design] för att göra redigeringen enklare. Så här:

>[!NOTE]
>
>Ikonen [!UICONTROL Show Components] ( ![Visa komponentikonen](/help/main/assets/icons/Add.svg) ) och ikonen [!UICONTROL Show Modifications] ( ![Visa ändringslinjen](/help/main/assets/icons/History.svg) ) fungerar som växlar för att visa lämpliga alternativ.

**Komprimera [!UICONTROL Components] rälen**

Om du vill komprimera [!UICONTROL Components]-rälen och förstora arbetsytan i [!UICONTROL Design] medan [!UICONTROL Components]-rälen är öppen klickar du på ikonen ( ![Visa komponenter ](/help/main/assets/icons/Add.svg) ).

**Komprimera [!UICONTROL Modifications] rälen**

Klicka på ikonen [!UICONTROL Modifications] ( [!UICONTROL Design]Visa ändringslinjen [!UICONTROL Modifications] ) om du vill komprimera [!UICONTROL Show Modifications]-rälen och förstora arbetsytan i ![ medan ](/help/main/assets/icons/History.svg)-rälen är öppen.

**Komprimera [!UICONTROL Properties] rälen**

Klicka på ikonen [!UICONTROL Properties] ( [!UICONTROL Design]egenskapsikonen [!UICONTROL Show/Hide Properties] ) till höger om listen om du vill komprimera eller visa ![-rälen om du vill komprimera ](/help/main/assets/icons/Propertie.svg)-rälen och förstora arbetsytan i [!UICONTROL Properties].

+++

## Är lägena [!UICONTROL Save as Draft] och [!UICONTROL Syncing] fortfarande tillgängliga?

+++Information
Med de senaste uppdateringarna av användargränssnittet är tillstånden [!UICONTROL Save as Draft] och [!UICONTROL Syncing] inte längre tillgängliga. Mer information finns i Status under [Använda filter i aktivitetslistan](/help/main/c-activities/activities.md#filters) i *[!UICONTROL Activities overview]*.

+++

## Hur vet jag om en aktivitet har skapats eller redigerats i det gamla användargränssnittet eller i det uppdaterade användargränssnittet?

+++Information
Aktiviteter som skapas eller redigeras i det uppdaterade användargränssnittet följer samma guidade trestegsarbetsflöde och kan innehålla gränssnittsspecifika metadata eller formatering som inte finns i äldre aktiviteter. Även om det inte finns någon synlig tagg eller etikett i gränssnittet, kan skillnader i layout, struktur eller tillgängliga alternativ (till exempel förbättrade funktioner för målinriktning eller förhandsvisning) visa vilket gränssnitt som användes. Detaljerad identifiering finns i aktivitetens ändringshistorik eller i implementeringsloggarna.

+++

## Vad är det för skillnad mellan att skapa erbjudanden i det gamla jämfört med det uppdaterade användargränssnittet? Krävs ytterligare attribut?

+++Information
Användargränssnittet [!UICONTROL Offer Library] kräver konsekventa attributdefinitioner för alla erbjudanden. När du skapar ett erbjudande som bara innehåller en aktivitet (ad hoc) måste användaren även ange ett erbjudandenamn. Den här informationen visas i [!UICONTROL Form-based Experience Composer], vilket gör det enklare att identifiera erbjudanden utan att behöva granska koden eller innehållet.

+++

## Vad hände med länkarna för förhandsgranskning av erbjudanden i det uppdaterade användargränssnittet?

+++Information
[!UICONTROL Experience Fragment] förhandsgranskningslänkar är tillgängliga i [!UICONTROL Quick Info]-porten, som visas när du klickar på informationsikonen ( ![informationsikonen ](/help/main/assets/icons/InfoOutline.svg) ) för det valda fragmentet.

+++

## Jag måste inaktivera [!UICONTROL Enhanced Experience Composer] när jag redigerar befintliga aktiviteter med det uppdaterade användargränssnittet. Har [!DNL Adobe] observerat liknande beteende med andra kunder?

+++Information
Ja. När du använder [!DNL Adobe Experience Cloud] [!DNL Visual Editing Helper extension] kan du behöva inaktivera [!UICONTROL Enhanced Experience Composer] (EEC).

Mer information finns i [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

+++

## Kan du hänvisa mig till de nya IP-adresserna för tillåtelselistning?

+++Information
Mer information om IP-adresser som du kan tillåtslista finns i följande artiklar:

* **Förbättrad Experience Composer (EEC)**: Se [EEG läser inte in en intern QA-URL som inte är tillgänglig på offentlig IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) i *Felsökning av problem som rör Förbättrad Experience Composer*
* **[!UICONTROL Recommendations]**: Se [IP-adresser som används av rekommendationsservrar för flödeshantering](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md).

+++

## Återställs miljön som standard till mellanlagring i det nya gränssnittet för rekommendationer?

+++Information
Miljöer är nu standard för den senaste som används av kunden. Använd väljaren [!UICONTROL Environment] i det övre högra hörnet av användargränssnittet i [!UICONTROL Catalog Search] om du vill växla mellan miljöer.

![Miljöväxel](/help/main/c-intro/assets/environmnent.png)

+++

## Hur komplicerad är det att ansluta [!DNL Adobe Analytics] eller [!DNL Customer Journey Analytics] till [!DNL Target]?

+++Information
Integrering av [!DNL Adobe Analytics] (AA) eller [!DNL Customer Journey Analytics] (CJA) med [!DNL Target] kan variera från måttlig till avancerad insats, beroende på den aktuella konfigurationen. Om du använder [!DNL Adobe Experience Platform] och har implementerat [!DNL Platform Web SDK] blir integreringen smidigare. Äldre implementeringar som använder at.js eller AppMeasurement kan dock kräva ytterligare konfiguration, inklusive:

* Aktivera [Analytics för Target-integrering (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)
* Integrera [[!DNL Target] rapportering i [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).
* Mappa rapportsviter och datavyer
* Säkerställ enhetlig identitetsupplösning (ECID)
* Validera inställningar för datainsamling och dataattribuering

+++
