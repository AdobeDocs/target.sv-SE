---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar,aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d87f1fbe78512363d4fe30935cbb4f2556b4a06b
workflow-type: tm+mt
source-wordcount: '1935'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Uppdaterat: [!DNL Target] Inaktuell version av användargränssnittet (17 juni 2025) {#revised}

Från och med den 17 juni 2025 bör alla IMS-organisationer ha aktiverats för det uppdaterade användargränssnittet för [!DNL Target], antingen för specifika användare eller för hela organisationen, för att börja testa den nya upplevelsen.

På grund av nyligen identifierade problem, som främst gäller komplexa kundanpassningar, har [!DNL Target]-teamet justerat tidslinjen för borttagning:

* **30 juni 2025**: [Uppdaterat [!DNL Target] gränssnitt](/help/main/c-intro/understand-the-target-ui.md) blir standardupplevelsen för alla IMS-organisationer som har aktiverat alternativet för gränssnittsversion.

   * Kunder som för närvarande ser det gamla användargränssnittet kommer som standard att se det uppdaterade användargränssnittet vid inloggning.
   * Användargränssnittets versionsknapp är fortfarande tillgänglig till och med slutet av juli så att användare kan växla tillbaka vid behov.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] rekommenderar starkt att det uppdaterade [!DNL Target]-gränssnittet används. Växla bara tillbaka till det gamla användargränssnittet om ett problem med blockering inträffar. Se [[!DNL Target] Borttagning av versionsinformation för användargränssnitt (23 maj 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#toggle) i versionsinformationen för tidigare versioner för viktig information om växlingsknappen.

* **15 juli till 30 juli 2025**: Användargränssnittets versionsväxel inaktiveras permanent i faser. Påverkade IMS-organisationer kan inte längre återgå till det gamla användargränssnittet.

   * Undantag kommer att ses över från fall till fall.
   * Förseningar av avaktiveringen ges endast kortvarigt (några dagar) medan blockerarproblem åtgärdas.

Kontakta [Adobe kundtjänst](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) om du har några frågor eller om du förväntar dig problem under den här övergången.

## [!DNL Target Standard/Premium] 25.6.2 (12 juni 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* En [ny artikel med vanliga frågor och svar](/help/main/c-intro/updated-ui-faq.md) har lagts till som åtgärdar vanliga frågor om det uppdaterade [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC).
* Ett problem har korrigerats där regeln [!UICONTROL URL - does not contain] i [!UICONTROL Page Delivery] inte fungerade, vilket gör att innehåll kan visas även när det borde ha blockerats. (TGT-52754)
* Ett problem har korrigerats där [!UICONTROL Page Delivery] felaktigt visade felmeddelandet: &quot;Duplicerade sidadresser tillåts inte. (TGT-52765)
* Korrigerade ett problem där målgrupper för [!UICONTROL Page Delivery] URL:er som innehåller upplevelsefragment skapades med # felaktigt tillagt. (TGT-52786)
* Ett problem har korrigerats där [!DNL Target]-gränssnittet inte svarade när en aktivitet kopierades och inställningarna för redigering på sidan [!UICONTROL Goals and Settings] ändrades. (TGT-52797)
* Korrigerade ett fel i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) som felaktigt tillät omdirigering av ytterligare en sida i en [!UICONTROL A/B Test]-aktivitet till samma URL. (TGT-51838)
* Ett problem har korrigerats där ändringar av mätvärden på sidan [!UICONTROL Goals and Settings] inte sparades när en aktivitet redigerades. (TGT-52799)
* Ett problem har korrigerats där tillägg av en ny upplevelse medan webbredigeraren fortfarande lästes in orsakade att den nya upplevelsen duplicerade innehåll från den tidigare upplevelsen. (TGT-51397)
* Möjligheten att använda anpassad kod utanför `<head>`-taggen återställdes, vilket är en funktion som tidigare fanns i det äldre målgränssnittet. (TGT-52304 &amp; TGT-52300)
* Onödig validering togs bort när standardarbetsytan valdes när aktiviteten skapades. Obligatorisk egenskapsvalidering gäller inte längre för standardarbetsytan, men finns kvar för icke-standardarbetsytor. (TGT-52449)
* Korrigerade ett problem i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) där `triggerView()` anrop inte kunde identifieras. (TGT-52575)
* Korrigerade ett fel i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) som gjorde att användare inte kunde lägga till ändringar i SPA-vyer ([!UICONTROL Single Page Application]). (TGT-52556)
* Ett problem i det uppdaterade användargränssnittet för [!DNL Target] som gjorde att kunderna inte kunde visa erbjudandeinformationen har åtgärdats. (TGT-52607)
* Ett problem har korrigerats där uppdateringar av erbjudanden i [!UICONTROL Offers Library] inte återspeglades i den uppdaterade versionen av [!UICONTROL Visual Experience Composer] (VEC). (TGT-52637)
* Ett problem som gjorde att offertavsnittet inte kunde visas korrekt när en aktivitet skapades har åtgärdats. (TGT-52773)
* Valideringen har lagts till för att säkerställa att alla `optionLocalIds` som refereras i `optionGroups` finns i alternativarrayen. Ogiltiga referenser tas automatiskt bort när aktiviteten skapas. (TGT-52687)
* Ett problem har korrigerats där rapporteringsgrupper och undantag inte behölls efter att ett nytt erbjudande lagts till. (TGT-52728)
* Ett problem har korrigerats där aktiviteter utan knappen [!UICONTROL Activity QA] visade en tom alternativväljare. (TGT-52733)
* Korrigerade ett problem där QA-länkar inte kunde återge innehåll korrekt. (TGT-52718)
* Ett problem har korrigerats där det inte gick att ersätta ett element med ett upplevelsefragment på rätt sätt i QA-miljön. (TGT-52762)
* Korrigerade ett fel i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) som orsakade felet &quot;Ogiltig inmatning&quot; när användare försökte lägga till upplevelsefragment. (TGT-52701)
* Korrigerade ett problem där spärrmetoden Redigera publik verkade tom vid redigering av målgruppsanpassning i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC). (TGT-52749)
* Ett meddelande har lagts till som informerar användare när en entitet inte är tillgänglig på den valda arbetsytan. (TGT-52767)
* Ett problem har korrigerats där användargränssnittet inte kunde tillåta manuell tilldelning av ett miljö-ID till ett villkor. I stället används ID:t för värdgruppen [!UICONTROL Product Catalog Search] som standard. Med den här korrigeringen säkerställs att villkorsändringar nu tillämpas i alla miljöer, inte bara som standard. (TGT-52817)
* Ett problem har korrigerats där alternativet [!UICONTROL Download Recommendations data] saknades för [!UICONTROL Experience Targeting] (XT)-aktiviteter med rekommendationer. (TGT-52730 &amp; TGT-52756)

## [!DNL Target Standard/Premium] 25.6.1 (6 juni 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem har korrigerats där QA-länkar inte gav rätt upplevelse för den associerade aktiviteten. (TGT-52163 &amp; TGT-52790)
* Ett problem har korrigerats där QA-länkar saknade det associerade målar-ID:t. (TGT-52722)
* Ett problem har korrigerats för att säkerställa att upplevelserna levereras endast när de konfigurerade villkoren för sidleverans-URL uppfylls korrekt. (TGT-52696)
* Ett problem som gjorde att kunder inte kunde skapa en [!DNL Recommendations]-designmall har korrigerats. Om du försöker skapa en mall utlöstes felet:&quot;Det ska finnas minst en entitetsvariabel i skriptet.&quot; (TGT-52395)
* Ett problem som gjorde att [!DNL Recommendations] designer inte kunde sparas med hjälp av hastighetsmatriser har åtgärdats. Felmeddelandet&quot;Det måste finnas minst en entitetsvariabel i skriptet&quot; utlöstes felaktigt. (TGT-52734)
* Korrigerade ett problem där ändringar inte var tillgängliga i [!UICONTROL Visual Experience Composer] (VEC) när sidan inte kunde läsas in för interna webbsidor. (TGT-52488 &amp;TGT-52470)
* Ett problem har korrigerats där panelen [!UICONTROL Modifications] inte var synlig på mindre skärmstorlekar i VEC. (TGT-52470)
* Korrigerade ett problem i den uppdaterade VEC där växling från läget [!UICONTROL Browse] till läget [!UICONTROL Design] orsakade ett konsolfel och förhindrade ytterligare interaktion. (TGT-52532)
* Korrigerade ett fel i VEC där storleken på vissa element oavsiktligt utökades när du klickade på dem. (TGT-52497)
* Korrigerade ett problem där vissa sidelement inte kunde läsas in eller identifieras i VEC, vilket förhindrade interaktioner som att välja knappar eller banners och störa korrekt händelsespårning i aktiviteter. (TGT-52663)
* Ett problem som gjorde att kunder inte kunde ta bort eller ta bort erbjudanden i [!UICONTROL Automated Personalization] (AP)-aktiviteter har åtgärdats. (TGT-52690)
* Korrigerade ett problem som orsakade inkonsekvent aktivitetskvalificeringsbeteende i flersidiga aktiviteter. (TGT-52694)
* Ett problem som orsakade att aktivitetens [!UICONTROL Overview]-sida visade en ogiltig URL för [!UICONTROL Activity Location] har korrigerats. (TGT-52695)
* Korrigerade ett problem i det uppdaterade användargränssnittet för [!DNL Target] som gjorde att dubblettposter visades för aktivitetsplatser. (TGT-52693)
* Korrigerade ett problem som utlöste ett `getAudiencesV3`-fel, vilket förhindrade kunder från att redigera eller kopiera aktiviteter. (TGT-52709)
* Korrigerade ett problem som orsakade ett ogiltigt nyttolastfel när [!UICONTROL Experience Fragments] eller HTML-erbjudanden lades till i en aktivitet. (TGT-52779 &amp; TGT-52773)
* Korrigerade ett fel i det uppdaterade [!DNL Target]-användargränssnittet där E[!UICONTROL xperience Fragments] inte kunde visas korrekt på grund av ett ogiltigt indatafel. (TGT-52701)
* Ett problem som gjorde att kunder inte kunde redigera aktiviteter i [!UICONTROL Form-based Experience Composer] på grund av ett ogiltigt användarfel har korrigerats. (TGT-52470)
* Korrigerade ett lokaliseringsfel på koreanskt språk där tidigare översättningar använde tecken utanför det grundläggande flerspråkiga planet. Den uppdaterade översättningen använder lämpliga tecken som förmedlar den avsedda innebörden korrekt. (TGT-52508 &amp; TGT-52509)
* Korrigerade ett lokaliseringsfel på koreanskt språk där översättningen för &quot;date&quot; var inkonsekvent när start- och slutdatum för en aktivitet valdes. (TGT-52510)

## [!DNL Target]-användargränssnittsversion växlar bort (23 maj 2025) {#toggle}

>[!IMPORTANT]
>
>Teamet [!DNL Target] har justerat tidslinjen för att växla borttagning av gränssnittsversion. Mer information finns i [Uppdaterad: [!DNL Target] Borttagning av gränssnittsversion (17 juni 2025)](#revised).

Det nya [!DNL Target]-användargränssnittet kommer att vara klart den 27 maj 2025 **.** Då har alla kunder tillgång till den senaste gränssnittsversionen.

Från och med **22 juni 2025** tas gränssnittsversionen bort. Alla användare kommer att övergå permanent till det nya gränssnittet, utan möjlighet att återgå till den tidigare versionen.

>[!NOTE]
>
>Kunder med specialfall som behöver ha kvar denna länk efter den 22 juni kan kontakta Adobe kundtjänst för att få hjälp.

### Viktig information om användargränssnittets versionsväxling

Vi erbjuder en tillfällig funktion som gör att du kan växla mellan det uppdaterade [!DNL Target]-gränssnittet och den äldre versionen med en växlingsknapp. Det här alternativet är endast tillgängligt under den sista fasen av UI-utrullningen.

![Växla mellan målgränssnittsversion](/help/main/r-release-notes/assets/toggle.png)

När utrullningen är klar tas växlingsknappen bort och alla användare övergår permanent till det uppdaterade användargränssnittet den **22 juni 2025**. Adobe rekommenderar att du planerar i förväg eftersom den här funktionen kommer att fasas ut snart.

### Begränsningar för användargränssnittets växlingsbeteende

* **Synlighet för nya aktiviteter**: Aktiviteter som har skapats i det uppdaterade användargränssnittet visas inte om du växlar tillbaka till det gamla användargränssnittet.
* **Redigera befintliga aktiviteter**: Ändringar som gjorts i befintliga aktiviteter (som ursprungligen skapades i det äldre användargränssnittet) när det uppdaterade användargränssnittet används kommer att publiceras på webbplatsen. De här uppdateringarna visas dock inte i det gamla användargränssnittet om du byter tillbaka. Endast de senaste uppdateringarna från det gamla användargränssnittet visas där.
* **Enhetlig aktivitetsinformation**: De senaste ändringarna, oavsett vilket användargränssnitt du använder, visas på din aktiva webbplats. Det gamla användargränssnittet visar dock endast de senaste ändringarna som gjorts i den versionen. Detta kan orsaka förvirring om aktiviteter som redigeras i det uppdaterade användargränssnittet ser annorlunda ut än i det äldre användargränssnittet.

### Mer information om det uppdaterade användargränssnittet

* Versionsinformation för [[!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Activities], [!UICONTROL Recommendations] och [!UICONTROL Visual Experience Composer] (VEC).

* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].

* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.

* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.

* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

* [[!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md): Här behandlas vanliga frågor om det nya [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC), inklusive navigeringsändringar, funktionsplatser och borttagning av den tillfälliga användargränssnittsversionen. Vare sig du är marknadsförare, utvecklare eller administratör kan du med de här vanliga frågorna få en smidig övergång och få ut det mesta av det uppdaterade användargränssnittet.

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
