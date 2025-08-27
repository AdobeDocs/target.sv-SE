---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: be371f3631d79c65c632a23776ab08de21b031eb
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 27 augusti 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Informationen i den här artikeln uppdateras ofta, särskilt före releaser.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.8.4 (28 augusti 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**[!UICONTROL Activities]**

+++Se detaljer
* **Ett problem har korrigerats där den schemalagda aktiviteten felaktigt visade statusen [!UICONTROL Live] i det uppdaterade användargränssnittet under processen att skapa aktivitet**: Aktiviteter med framtida aktiveringsdatum visar nu korrekt status [!UICONTROL Scheduled]. (TGT-53187)
* **Schemalagda aktiviteter visade felaktigt statusen [!UICONTROL Live] tills sidan uppdaterades**: Kunder rapporterade att när en aktivitet schemaläggs att bli aktiv vid ett framtida datum och en framtida tidpunkt visades statusen ursprungligen som [!UICONTROL Live] i stället för [!UICONTROL Scheduled]. Detta orsakade förvirring trots att bekräftelsemeddelandet anger att schemaläggningen fungerar korrekt. Aktivitetsstatusen speglar nu [!UICONTROL Scheduled] korrekt omedelbart efter att du har sparat, utan att en siduppdatering krävs. (TGT-52937)
* **Ändringar av dubblerade upplevelser som oavsiktligt påverkade den ursprungliga upplevelsen**: Kunderna rapporterade att när de duplicerade en upplevelse i en aktivitet och tilldelar en ny publik, speglades även ändringar som gjorts i den duplicerade upplevelsen, till exempel design eller kriterier, i den ursprungliga upplevelsen. Detta förhindrade att oberoende variationer och produktionsarbetsflöden skapades. Dubblerade upplevelser kan nu redigeras oberoende av varandra utan att den ursprungliga versionen påverkas. (TGT-53361)
* **Ett problem som gjorde att kunderna inte kunde spara en aktivitet på grund av ett `InvalidProperty.Json` error** har korrigerats: Tidigare uppstod ett fel om ogiltig användarindata när en aktivitet skulle sparas utan att några ändringar gjordes. Felet orsakades av ett okänt egenskapsnamn, content, i JSON-nyttolasten. Problemet har lösts och aktiviteter kan nu sparas korrekt i det uppdaterade användargränssnittet, även när inga ändringar har gjorts. (TGT-53513)

+++

**Analyser för mål (A4T)**

+++Se detaljer
* **Det går inte att skriva rapportsvitnamn när A4T-aktiviteter skapas**: Kunderna kunde inte skriva i listrutan [!UICONTROL Report Suite] när de valde [!UICONTROL Analytics] som rapportkälla i det uppdaterade användargränssnittet.  Detta gjorde det svårt att hitta specifika rapportsviter, särskilt för organisationer med stora listor. Listrutan har nu stöd för att skriva och söka efter namn, vilket förbättrar effektiviteten när du skapar aktiviteter. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Se detaljer
* **Målgrupper med tidsram blockerade aktiviteter även efter borttagning**: Tidigare kunde kunderna inte spara en aktivitet om den tidigare hade inkluderat en utgången målgrupp med tidsram - även efter att målgruppen tagits bort. Problemet orsakades av en kvarvarande validering hos den målgrupp som bara har aktiviteten kvar, som fortsatte att utlösa fel. Aktiviteter kan nu sparas som förväntat när utgångna målgrupper har tagits bort. (TGT-53517)
* **Ytterligare sidor och flera målgrupper försvinner när en aktivitet har sparats**: Tidigare gick det för kunder som skapade en [!UICONTROL A/B Test]-aktivitet i aktivitetsskapandeprocessen att förlora konfigurerade ytterligare sidor och flera målgrupper efter att de sparats. Detta beteende var oväntat och orsakade förvirring under installationen. Dessa konfigurationer bevaras nu korrekt när aktiviteten har sparats. (TGT-52357)

+++

**Beslutserbjudanden**

+++Se detaljer
* **Det går inte att redigera beslutserbjudanden eller markera specifika sidelement i det uppdaterade VEC**: Kunderna har stött på flera problem i det uppdaterade användargränssnittet som har blockerat deras möjlighet att uppdatera befintliga aktiviteter eller skapa nya:

   * Beslutserbjudandena visades felaktigt när HTML erbjuder, vilket förhindrar redigeringar.
   * Det gick inte att välja specifika sidelement i VEC.
   * Ändringar som gjordes under redigeringen sparades inte.
   * Vissa regionala URL:er lästes inte in korrekt i VEC, vilket kräver manuella cookie-justeringar.

  Kunderna kan nu redigera beslutserbjudanden, välja sidelement korrekt och spara ändringarna som förväntat. Regionala sidor läses också in korrekt i VEC. (TGT-53425)

* **Det gick inte att ändra och ändra väljare för erbjudandebeslut efter att du sparat**: Kunder rapporterade att väljaren inte kunde ändras från standardvärdet när de tillämpade erbjudandebesluten i det uppdaterade användargränssnittet. Försök att ändra väljaren (till exempel till `#tf-cq-hr or body`) ignorerades, och när aktiviteten har sparats ersattes väljaren med ett generiskt värde som `#cdq_element_0`. På grund av detta försvann erbjudandet från Visual Experience Composer (VEC) och ytterligare redigeringar blockerades. Kunderna kan nu ändra beslutsväljarna och de sparade väljarna bevaras korrekt utan oväntade ändringar. (TGT-53433)
* **Erbjudandebeslut har tagits bort från aktiviteter efter att** sparats: Kunder rapporterade att offertbeslut som tillämpats på sidelement i det uppdaterade användargränssnittet inte längre var synliga efter att aktiviteten sparats. I vissa fall ändrades väljaren oväntat och erbjudandet kunde inte återges i VEC vid omredigering. Erbjudandebesluten kvarstår nu korrekt efter sparandet och väljarna är stabila, vilket säkerställer att erbjudandena är synliga och redigerbara som förväntat. (TGT-53434)

+++

**Upplevelsefragment**

+++Se detaljer
* **Kunderna fick ett fel när de infogade [!UICONTROL Experience Fragments] med [!UICONTROL Insert Before] eller[!UICONTROL Insert After]**: Ett fel uppstod när [!UICONTROL Experience Fragments] skulle infogas i en aktivitet med alternativen [!UICONTROL Insert Before] eller [!UICONTROL Insert After] i det uppdaterade användargränssnittet. Felmeddelandet som visades var:

  &quot;Innehållet i erbjudandet måste innehålla exakt ett HTML-element.&quot;

  Problemet var specifikt för det uppdaterade användargränssnittet och uppstod inte i den tidigare versionen. Det har nu lösts och kunderna kan infoga [!UICONTROL Experience Fragments] utan att detta fel påträffas. (TGT-53432)

* **Felmeddelande när [!UICONTROL Experience Fragment] lades till i en aktivitet**: Tidigare påträffades felet&quot;Erbjudandeinnehåll måste innehålla exakt ett HTML-element&quot; när en [!UICONTROL Experience Fragment] skulle infogas med alternativet [!UICONTROL Insert Before] eller [!UICONTROL Insert After].&quot; Det här felet uppstod trots att fragmentet är giltigt och accepterat i det äldre användargränssnittet, som innehåller en växlingsknapp som stöder den här konfigurationen. Problemet har lösts i den uppdaterade VEC:n. (TGT-53442)

+++

**Lokalisering**

+++Se detaljer
* **Popup-meddelanden i [!UICONTROL Goals & Settings]-steget översattes inte**: Tidigare påträffade kunderna ett olokaliserat popup-meddelande när tecken som inte stöds, t.ex. känslolägesikoner, angavs i fältet [!UICONTROL Objective] när aktiviteten skapades. Popup-meddelanden är nu korrekt lokaliserade för alla språk som stöds, vilket ger en enhetlig och tillgänglig upplevelse för globala kunder. (TGT-52251)
* **En sträng i dialogrutan [!UICONTROL Create Audience] översattes inte**: Tidigare visades meddelandet &quot;Välj minst ett start- eller slutdatum för &quot;inte upprepning&quot;&quot; vara olokaliserat i modala [!UICONTROL Create Audience] när tidsramsattribut konfigurerades. Strängen är nu korrekt lokaliserad för alla språk som stöds, vilket ger en konsekvent upplevelse för globala kunder i arbetsflödet [!UICONTROL Audiences]. (TGT-52253)
* **Verktygstipset i dialogrutan [!UICONTROL Create Audience] var inte lokaliserat**: Tidigare visades verktygstipset vara olokaliserat när kunder hovrade över felverktygstipset efter att ha angett tecken som inte stöds, t.ex. känslolägesikoner, i fältet för målgruppsnamn. Verktygstipset visar nu korrekt lokaliserade meddelanden på alla språk som stöds, vilket ger en konsekvent och tillgänglig upplevelse i arbetsflödet för [!UICONTROL Audiences]. (TGT-52254)

+++

**[!DNL Recommendations]**

+++Se detaljer
* **Det går inte att inaktivera [!UICONTROL Front Promotion] i aktiv aktivitet**: Ett problem har korrigerats där kunder inte kunde inaktivera [!UICONTROL Front Promotion] i aktiva aktiviteter med det uppdaterade användargränssnittet. Ändringarna som gjordes i erbjudandeavsnittet under processen för att skapa aktivitet kvarstår nu som förväntat, vilket garanterar korrekt konfiguration av aktiva aktiviteter i [!UICONTROL Product Catalog Search]. (TGT-53231)
* **Redigering av en dubblerad upplevelse påverkar den ursprungliga upplevelsen**: Kunder rapporterade att när de duplicerade en upplevelse i en aktivitet och ändrade rekommendationsdesignen eller kriterierna i dubbletten tillämpades dessa ändringar oavsiktligt på den ursprungliga upplevelsen.  Detta förhindrar att oberoende variationer skapas och störde förväntat beteende i den uppdaterade processen för att skapa aktivitet. Dubblerade upplevelser kan nu redigeras oberoende av varandra utan att den ursprungliga versionen påverkas. (TGT-53369)
* **Det går inte att visa produktlistan när du redigerar en samling eller ett undantag på fliken [!UICONTROL Recommendations]**. Tidigare var produktlistan som filtrerats av tillämpade regler inte synlig i redigeringsmodalen, vilket gör det svårt för kunderna att bekräfta vilka produkter som inkluderades eller uteslöts. Produktlistan visas nu korrekt och uppdateras i realtid när reglerna ändras, vilket förbättrar synligheten och användbarheten i det uppdaterade användargränssnittet för [!DNL Recommendations]. (TGT-53481)
* **Layouten för dialogrutan [!UICONTROL View Details] har uppdaterats på fliken [!UICONTROL Recommendations]**: Tidigare saknade dialogrutan [!UICONTROL View Details] en tydlig struktur, vilket gjorde det svårt för kunderna att komma åt artikelspecifik och lagerrelaterad information. Layouten har uppdaterats så att den innehåller två flikar: en flik visar information för den valda artikeln och den andra fliken visar lagret filtrerat efter de aktuella reglerna för samlingen eller uteslutningen. Den här förbättringen förbättrar tydligheten och användbarheten i det uppdaterade användargränssnittet för [!DNL Recommendations]. (TGT-53503)
* **Kunder kunde inte söka efter rapportsviter i listrutan [!UICONTROL Goals & Settings]**: Tidigare hade listrutan för rapportsviter i avsnittet [!UICONTROL Goals & Settings] i processen för att skapa aktivitet inte stöd för textinmatning för sökning, vilket gjorde det svårt för kunder med ett stort antal rapportsviter att hitta rätt. Den här funktionen, som finns i det gamla användargränssnittet, har återställts. Kunder kan nu skriva och söka efter och välja rapportsviter effektivare. (TGT-53514)
* **Kunderna kan inte hämta CSV-filen med anpassade villkor i [!DNL Recommendations] användargränssnittet**: Tidigare returnerades ett 404-fel när de klickade på nedladdningslänken för CSV-filer med anpassade villkor på fliken [!UICONTROL Recommendations] och kunde inte öppnas på en ny flik. Hämtningslänken öppnas nu på en ny flik och CSV-filen visas korrekt, vilket förbättrar tillgängligheten och användbarheten för kunder som hanterar anpassade villkor. (TGT-51966)
* **Om du aktiverar en [!UICONTROL Recommendations]-kampanj utan indata utlöstes ett generiskt felmeddelande**: Tidigare aktiverade kunder en främre eller bakre befordran i en Recommendations-aktivitet utan att obligatoriska fält angavs ett vagt &quot;Ogiltigt indatafel&quot; med koden `error.restapi.missingFields`. Systemet innehåller nu ett tydligt och åtgärdbart felmeddelande som anger vilka fält som saknas, vilket förbättrar användbarheten och minskar förvirringen när aktiviteten skapas. (TGT-52616)
* **Miniatyrbilder och bilder för produkter lästes inte in konsekvent i[!UICONTROL Catalog Search]**: Kunderna rapporterade att produktminiatyrer och bilder i full storlek i [!UICONTROL Catalog Search] ibland saknades eller gick sönder, särskilt efter att ha navigerat i eller ändrat kolumnsynlighet. Miniatyrbilder och bilder läses nu in tillförlitligt, oavsett kolumninställningar eller navigeringsbeteende, vilket förbättrar det övergripande arbetsflödet i [!UICONTROL Recommendations]. (TGT-52778)
* **Det gick inte att skapa [!UICONTROL Designs] och [!UICONTROL Criteria] i [!UICONTROL Stage] miljö**: Kunderna påträffade ett &quot;ogiltigt användarinmatningsfel&quot; vid försök att skapa [!UICONTROL Designs] eller [!UICONTROL Criteria] på fliken [!UICONTROL Recommendations] i miljön [!UICONTROL Stage]. Kunder kan nu skapa [!UICONTROL Designs] och [!UICONTROL Criteria] utan fel i [!UICONTROL Stage]-miljön. (TGT-53205)
* **[!UICONTROL Promotions]togs inte bort från [!UICONTROL Recommendations] aktiviteter efter att** sparats: Kunder rapporterade att kampanjer som lagts till i [!DNL Recommendation] aktiviteter fortsatte att visas även efter att de tagits bort och sparats. Detta problem påverkade både testnings- och produktionsmiljöer och bevaras över flera försök att spara. Kampanjer återspeglar nu ändringar som gjorts under aktivitetsredigering i den uppdaterade processen för att skapa aktiviteter korrekt. (TGT-53490)

+++

**[!UICONTROL Reports]**

+++Se detaljer
* **[!UICONTROL Automated Segments]visade en null-målgrupp i aktivitetsrapporter**: Kunderna observerade att målgruppsfältet verkade vara null när de visade [!UICONTROL Automated Segments] i [!UICONTROL Reports]-avsnittet i en aktivitet, trots att giltiga segmentdata förväntades. Det här problemet påverkade insynen i målgruppsanpassning och rapportens exakthet. [!UICONTROL Automated Segments] visar nu korrekt associerad målgruppsinformation i aktivitetsrapporter. (TGT-52793)
* **Det gick inte att hämta aktivitetsrapporter i CSV-format**: Kunder som försöker exportera aktivitetsrapporter från fliken [!UICONTROL Reports] påträffade ett fel när de valde alternativet för hämtning av CSV. Problemet påverkade både standardrapporter och export av orderdetaljer. Rapporterna har nu hämtats korrekt i CSV-format. (TGT-53464)

+++

**Single Page Applications (SPA)**

+++Se detaljer
* **Om du växlar mellan [!UICONTROL Browse] och [!UICONTROL Design] lägen återställs SPA-lägen (single-page application) i webbredigeraren**: Kunder rapporterade att växling mellan [!UICONTROL Browse] och [!UICONTROL Design] lägen i VEC gjorde att webbredigeraren lästes in på nytt och SPA-läget återställdes och att processen för att skapa aktivitet stördes. Redigeraren bevarar nu SPA-navigeringstillståndet när du byter läge, vilket ger en smidigare och mer enhetlig redigeringsupplevelse. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++Se detaljer
* **Att byta namn på en plats i en [!UICONTROL Automated Personalization] (AP) eller [!UICONTROL Multivariate Test] (MVT) aktivitet kvarstår inte efter att användaren har navigerat till steget [!UICONTROL Targeting] och återgått.**-kunder kan nu redigera och spara platsnamn, och ändringarna är fortfarande synliga under hela aktivitetsskapandeprocessen. (TGT-52367)
* **Det äldre VEC-gränssnittet som visas på klientorganisationer i [!UICONTROL Stage] miljön** har åtgärdats och ett fel uppstod när vissa klientorganisationer i [!UICONTROL Stage]-miljön skulle visas felaktigt som det gamla gränssnittet i stället för det uppdaterade VEC-gränssnittet. Det här problemet kunde reproduceras över flera inloggningssökvägar och påverkade avsnittet [!UICONTROL Activities]. Det uppdaterade användargränssnittet visas nu korrekt för båda klienterna i miljön [!UICONTROL Stage]. (TGT-52261)
* **Om du valde en bakgrundsfärg kraschade sidan i den uppdaterade VEC:n**:
Ett problem har korrigerats där sidans krasch och tomma blev resultatet när en bakgrundsfärg valdes från panelen [!UICONTROL Style] i den uppdaterade VEC-inställningen. Konsolfel indikerade ett fel med att läsa egenskaper från ett odefinierat element, specifikt relaterat till `querySelector`. Nu kan man säkert välja bakgrundsfärger utan att behöva krascha. (TGT-53561)
* **Det gick inte att spara aktiviteter på grund av ett ogiltigt användarindatafel**: Ett fel har korrigerats vid försök att spara befintliga aktiviteter i den uppdaterade VEC:n. Felet visades endast under redigeringar, inte när nya aktiviteter med samma egenskap skapades. Felmeddelandet innehåller:

  `Invalid Json. Unrecognized property name 'content'. Location: line - 1, column - 432.`

  Aktiviteter som använder den påverkade egenskapen kan nu sparas korrekt efter redigeringen. (TGT-53507)

* **Genomskinliga bilder innehöll inte längre parametern fmt=png-alpha i den uppdaterade VEC**: Kunder rapporterade att genomskinliga bakgrunder inte längre kunde bevaras när bilderna skulle ersättas i det uppdaterade användargränssnittet. Bild-URL:erna som genereras av den uppdaterade VEC:en utelämnade parametern `fmt=png-alpha`, som tidigare säkerställde genomskinlighet i det gamla användargränssnittet. Det uppdaterade användargränssnittet lägger nu korrekt till parametern `fmt=png-alpha` för genomskinliga bilder och återställer det förväntade återgivningsbeteendet. (TGT-52615)
* **Kunder kunde inte fortsätta till målsektionen i AP-aktiviteter utan att lägga till två platser**: Kunder som skapar [!UICONTROL Automated Personalization]-aktiviteter (AP) i det uppdaterade användargränssnittet kunde inte fortsätta till målsektionen om inte två platser lades till. Det här beteendet skiljer sig från det tidigare användargränssnittet, där en enda plats var tillräcklig. Problemet blockerade skapande och sparande av aktivitet för kunder som föredrar att bara använda en plats. Kunderna kan nu gå vidare till målgruppsanpassning och spara AP-aktiviteter på en enda plats, vilket återställer förväntad funktionalitet. (TGT-53426)
* **HTML-erbjudanden är dubblerade på arbetsytan när du byter upplevelser**: Tidigare var det kunder som infogade HTML-erbjudanden i erfaret duplicerat innehåll på arbetsytan efter växling mellan upplevelser. Det här problemet gjorde också att arbetsytan inte kunde rullas, vilket påverkade användbarheten. HTML-erbjudanden är inte längre dubbletter och arbetsytan är rullningsbar när du byter upplevelser i den uppdaterade VEC:n. (TGT-53487)
* **Manuell uppdatering av en CSS-väljare gjorde att VEC-skärmen blev tom**: Kunder rapporterade att när de redigerade ett erbjudande i VEC utlöstes en tom skärm manuellt när CSS-väljaren uppdaterades manuellt, även när väljaren var giltig och fanns på sidan. VEC-skärmen är nu fortfarande stabil när väljarna uppdateras manuellt under aktivitetsskapandeprocessen. (TGT-53553)
* **Trunkeringsproblem i fältet Startdatum när du valde &#39;angivet datum och tid&#39; i[!UICONTROL Goals & Settings]**: Kunderna fick ett trunkeringsproblem i fältet [!DNL Start date] när de valde det angivna datum- och tidsalternativet i avsnittet duration på sidan [!UICONTROL Goals & Settings] när aktiviteter skapades. Det fullständiga datumet och den fullständiga tiden visas nu korrekt för alla språk som stöds. (TGT-47843)
* **Filterikonen försvann när webbläsaren i [!UICONTROL Manage Content] rälen** minimerades: Kunderna rapporterade att filterikonen i [!UICONTROL Manage Content] ratten i aktivitetsskapande [!UICONTROL Automated Personalization]-flöde försvann när webbläsarfönstret ändrades eller minimerades. Filterikonen är nu fortfarande synlig och tillgänglig oavsett webbläsarstorlek, vilket förbättrar användbarheten mellan skärmupplösningar. (TGT-51449)

+++

**[!UICONTROL Workspaces]**

+++Se detaljer
* **Kunder som är begränsade till en enskild arbetsyta kan visa aktiviteter från andra arbetsytor**: Kunder med begränsad åtkomst till en viss arbetsyta kunde fortfarande välja [!UICONTROL All Workspaces] i det uppdaterade användargränssnittet och visa aktiviteter från andra arbetsytor. Detta beteende innebar en risk för oavsiktliga ändringar av aktiva aktiviteter utanför det tilldelade omfånget. Workspace begränsningar används nu korrekt och kunderna kan bara visa aktiviteter på sin tilldelade arbetsyta. (TGT-53101)
* **Kunder kunde visa aktiviteter från [!UICONTROL Default Workspace] utan åtkomst**: Kunder kunde se aktiviteter från [!UICONTROL Default Workspace] trots att de inte hade tillgång till den. Workspace behörigheter används nu korrekt i det uppdaterade användargränssnittet, vilket säkerställer att kunderna bara ser aktiviteter som är kopplade till deras tilldelade arbetsyta. (TGT-53297)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
