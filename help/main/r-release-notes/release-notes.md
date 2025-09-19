---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 098415849152065b734cbebbab8dcf1d0805e202
workflow-type: tm+mt
source-wordcount: '1779'
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
