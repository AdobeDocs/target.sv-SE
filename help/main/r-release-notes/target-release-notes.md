---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: dc291b4573e00512edd44b94304be2a25106b234
workflow-type: tm+mt
source-wordcount: '1882'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 7 juli 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.7.1 (8 juli 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem där endast aktivitetsspecifika målgruppsförbättringar försvann från användargränssnittet omedelbart efter att de tagits bort från en plats, även innan aktiviteten sparades. Detta beteende stred mot den förväntade funktionen och riktlinjerna för verktygstips, som anger:&quot;Alla oanvända målgrupper från det här biblioteket tas bort när aktiviteten sparas.&quot; (TGT-52982)
* Ett problem har korrigerats vid försök att tilldela en annan målgrupp än [!UICONTROL All Visitors] till en aktivitet. När du sparar visas följande felmeddelande:&quot;Vi kan inte slutföra din begäran. Kontakta Adobe kundtjänst om problemet kvarstår.&quot; (TGT-53008)
* Korrigerade ett problem som blockerade sparandet av en aktivitet efter att en ny målgrupp har skapats och tilldelats i aktivitetsredigeraren. Felmeddelandet som visades var:&quot;Vi kan inte slutföra din begäran. Kontakta Adobe kundtjänst om problemet kvarstår.&quot; (TGT-52977)
* Ett problem som uppstod när en aktivitet skulle sparas efter att en ny rapportpublik har skapats och tilldelats. Felmeddelandet som returnerades var: &quot;Åtkomst nekad. För att kunna utföra den här åtgärden krävs alla följande behörigheter: [editor].&quot; Problemet uppstod trots att användaren har åtkomst på godkännarnivå. (TGT-53103)
* Ett problem har korrigerats där användare med rollen [!UICONTROL Approver] inte kunde lägga till eller spara målgruppsförbättringar enbart för aktivitet. Ett försök att göra detta resulterade i ett 403-fel som anger att privilegiet [editor] krävdes, även om användaren hade tillräcklig behörighet för att godkänna och hantera aktiviteter. (TGT-52984)
* Ett problem har korrigerats när en aktivitetsspecifik målgrupp tas bort med alternativet [!UICONTROL Remove Audience Refinement]. Publiken visas inte längre i målgruppslistan för omval inom samma aktivitet. Det här beteendet hindrade användare från att lägga till samma målgrupp på nytt om de inte återskapar den från grunden. (TGT-52979)
* Korrigerade ett problem som förhindrade användare från att skapa [!UICONTROL Auto-Target] (AT) aktiviteter om [!UICONTROL Auto-Allocate] (AA) väljs först under konfiguration av trafikallokering. Säkerhetsluckan resulterade i ett serverdelsvalideringsfel som förhindrar att aktiviteten sparas. (TGT-53096)
* Ett problem har korrigerats där användare inte kunde bläddra till en annan URL i [!UICONTROL Browse Mode]. Detta hindrade testare och redigerare från att validera eller förhandsgranska alternativa sidor i samma aktivitetssession. (TGT-53052)
* Ett problem har korrigerats där funktionen [!UICONTROL Manage Content] i [!UICONTROL Automated Personalization] (AP)-aktiviteter gjorde att sidan kraschade och var tom. Det här problemet uppstod efter att du klickat på [!UICONTROL Done] i innehållshanteraren, särskilt i aktiviteter som skapats eller redigerats i det uppdaterade användargränssnittet. (TGT-53047)
* Ett problem har korrigerats där funktionen [!UICONTROL Manage Content] inte validerade läget för en plats korrekt efter att alla innehållsalternativ tagits bort. Detta kan leda till inkonsekvent beteende eller fel när du försöker spara eller fortsätta med aktivitetskonfigurationen. (TGT-52801)
* Ett problem har korrigerats där flera [!UICONTROL Visual Experience Composer] (VEC)-instanser skulle öppnas samtidigt när aktiviteten skapades. Problemet uppstod när användare inaktiverade [!UICONTROL Enhanced Experience Composer] (EEC) och tog bort det avslutande snedstrecket från webbplatsens URL i [!UICONTROL Page Delivery]-steget. (TGT-52782)
* Korrigerade ett problem där användare påträffade ett &quot;Ogiltigt indatafel&quot; när de lade till en ny sida och tog bort specifika element i olika upplevelser. Felet utlöstes av att dubbletten `LocalIds` genererades under elementmanipuleringen, särskilt när du växlar mellan upplevelser och ändrar delade sidstrukturer. (TGT-52720)
* Ett problem har åtgärdats där en ändring av en vy skulle medföra att vyn dupliceras och att aktiviteten returnerade ett &quot;Ogiltigt indatafel från användaren&quot;. Med den här korrigeringen säkerställs att vyändringarna tillämpas på rätt sätt utan att utlösa duplicerings- eller valideringsfel. (TGT-52886)
* Ett problem har korrigerats där anpassade kodändringar felaktigt visades för fel upplevelse. I synnerhet har förändringar avsedda för en upplevelse visat sig i en annan upplevelse, vilket lett till förvirring och potentiell misskonfiguration av aktiva aktiviteter. (TGT-52776)
* Ett problem som gjorde att det inte gick att redigera eller spara anpassade kodändringar i det nya VEC-gränssnittet har korrigerats. Mer specifikt:

   * När du har redigerat ett anpassat kodblock och sparat återspeglas inte ändringarna i användargränssnittet eller i QA-förhandsvisningen.
   * I vissa fall gick det inte att ta bort ändringarna om inte aktiviteten stängdes och öppnades igen.
   * Som en tillfällig lösning måste användarna kopiera koden, ta bort ändringen och återskapa den manuellt med det uppdaterade innehållet. (TGT-53072)

* Ett problem har korrigerats där redigering och sparande av anpassad kod gjorde att panelen [!UICONTROL Modifications] inte svarade. (TGT-53075)
* Ett problem har korrigerats där ändringar av anpassad kod i olika upplevelser av misstag återspeglades i [!UICONTROL Control]-upplevelsen. Detta orsakade oönskade förändringar av leveransbeteendet. [!UICONTROL Control]-upplevelsen är nu fortfarande isolerad från anpassade kodredigeringar som gjorts i andra upplevelser. (TGT-52413)
* Korrigerade ett problem i arbetsflödet där ändringar som gjorts i en upplevelse (till exempel Experience B) oavsiktligt duplicerades till en annan upplevelse (Experience A) om användaren klickade på den andra upplevelsen innan redigeraren var helt inläst. Detta beteende kan också leda till att ändringar går förlorade om den upplevelse som du valde först inte hade några ändringar. (TGT-52597)
* Ett problem har korrigerats där ändringar som gjorts i steget [!UICONTROL Modifications] när aktiviteten skapades inte sparades konsekvent. När du har slutfört alla steg och klickat på [!UICONTROL Save] återspeglas i vissa fall inte det anpassade skript som lagts till i avsnittet [!UICONTROL Modifications] på den aktiva webbplatsen, trots att inga synliga fel uppstod under sparandet. (TGT-52661)
* Korrigerade ett problem där anpassade kodändringar inte sparades korrekt och av misstag speglades över flera upplevelser inom samma aktivitet. Dessutom stötte användare på åtkomstproblem när vissa aktiviteter öppnades eller uppdaterades, vilket resulterade i tomma skärmar. Dessa problem har nu åtgärdats för att säkerställa stabil aktivitetsredigering och korrekt upplevelseisolering. (TGT-52594)
* Ett problem har korrigerats där funktionen [!UICONTROL Generate Adhoc Offer] resulterade i att odefinierade platser visades på panelen [!UICONTROL Manage Content]. (TGT-53076 &amp; TGT-53070)
* Beteendet klarlades för kunden där ändringar som gjorts med ett HTML-erbjudande verkar saknas vid navigering från [!UICONTROL Targeting]-steget tillbaka till [!UICONTROL Experiences]. För den här kunden genererade den berörda webbplatsen dynamiskt flera DOM-väljare som ändrades vid inläsningen av varje sida. Därför går det inte att hitta den väljare som ursprungligen användes för ändringen när redigeraren öppnas igen, vilket gör att ändringen verkar saknas eller vara ogiltig. Detta fungerar som avsett. För att ändringarna ska finnas kvar visuellt i redigeraren rekommenderar vi att kunderna använder stabila, konsekventa väljare som inte ändras vid sidomladdning. (TGT-52874)
* Ett problem har korrigerats där ett försök att ta bort eller inaktivera ett erbjudande som var en del av en utesluten upplevelse utlöste felet&quot;Ogiltig användarinmatning&quot;. Problemet uppstod trots att erbjudandet inte användes aktivt i de inkluderade upplevelserna. (TGT-52917)
* Ett problem har korrigerats där den [!UICONTROL Revenue]-metriska listrutan i [!UICONTROL Goals & Settings]-steget felaktigt skulle ha standardvärdet [!UICONTROL Revenue per Visit] (RPVISIT), även efter att användaren har valt ett annat mått.  ett problem uppstod när panelen för metrisk konfiguration komprimerades och utökades på nytt, vilket gjorde att det tidigare valda värdet återställdes. (TGT-52811 &amp; TGT-52878)
* Ett problem som blockerade har korrigerats
* Flera problem har korrigerats i arbetsflödet för att skapa aktivitet relaterade till namngivning och innehållsöversättning i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Multivariate Testing] (MVT)-aktiviteter:

  Viktiga problem som åtgärdats:

   * Om du skapade flera HTML-erbjudanden med samma namn (till exempel &quot;Upplevelse&quot;) utlöstes felet &quot;Duplicera erbjudandenamn tillåts inte&quot;, men gränssnittet visade inte tydligt vilka erbjudanden som orsakade konflikten.
   * När du ändrade namn på erbjudanden via den högra panelen uppdaterades namnet i användargränssnittet, men ändringen återspeglades inte på fliken [!UICONTROL Manage Content] eller [!UICONTROL Offers], vilket orsakar permanenta valideringsfel.
   * I MVT-aktiviteter, trots att dubblettnamnsfelet inte kvarstod efter namnbytet, kunde användargränssnittet fortfarande inte återge uppdaterade erbjudandenamn på ett konsekvent sätt på alla flikar. (TGT-52933)

* Ett problem har korrigerats där [!UICONTROL Export order details to CSV] från sidan [!UICONTROL Reports] resulterade i att en tom fil hämtades. Problemet uppstod även när giltiga orderdata fanns i aktiviteten. (TGT-52225)
* Ett problem har korrigerats där kopiering av en befintlig aktivitet och ändring av rapportkällan till [!DNL Adobe Analytics] (A4T) skulle resultera i ett felaktigt indatafel. Felet utlöstes när vissa måttåtgärder som är inkompatibla med [!DNL Analytics]-rapportering, som `restart_same_experience`, `restart_random_experience` och `restart_new_experience`, behålls från den ursprungliga aktiviteten. (TGT-52900)
* Korrigerade ett problem som hindrade kunder från att skapa eller spara en aktivitet när de valde [!DNL Adobe Analytics] (A4T) som rapportkälla i [!UICONTROL Goals & Settings] -steget. Problemet uppstod när ett [!UICONTROL Custom Event]-mått valdes (till exempel &quot;Egen händelse 16&quot;), vilket resulterade i följande fel: &quot;Ogiltigt användarinvärde.&quot; (TGT-52910)
* Ett problem har korrigerats där användaren omdirigerades till hemsidan i stället för till den avsedda [!UICONTROL View in Analytics]-instrumentpanelen när användaren klickade på länken [!DNL Analytics]. (TGT-53092 &amp; TGT-53093)
* Ett problem har korrigerats vid kloning av en befintlig aktivitet och ändring av rapportkällan från [!DNL Target] till [!DNL Adobe Analytics]. Användarna påträffade felet 400 - ogiltig användarinmatning, vilket förhindrar att aktiviteten sparas. (TGT-52875)
* Ett problem har korrigerats där URL:er för förhandsgranskning felaktigt inkluderade fler målgrupper än den som användaren uttryckligen angav. Detta beteende har korrigerats för att säkerställa att endast den angivna målgruppen används när en QA- eller förhandsgranskningslänk genereras. (TGT-52912)
* Ett problem har korrigerats där URL:en [!UICONTROL Activity QA] innehöll en onödig frågeparameter: `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Korrigerade ett problem i formulärbaserade aktiviteter där dubblering av en upplevelse och redigering av den anpassade koden i en av de duplicerade upplevelserna oavsiktligt skulle tillämpa dessa ändringar på alla duplicerade upplevelser. Varje upplevelse behåller nu sin egen anpassade kod oberoende av varandra efter duplicering. (TGT-51600)
* Ett problem som påverkade arbetsflödet för aktivitetsskapande när [!DNL Recommendations] lades till med [!UICONTROL promotions] har korrigerats. När användare markerade [!UICONTROL Promote by Attribute] och lade till en filtreringsregel (till exempel [!UICONTROL Parameter Matching]), behålldes inte den valda regeltypen och operandvärdena efter att aktiviteten sparats och redigerats om. När filterregeltypen öppnas igen ändras den oväntat och operandvärden saknas. (TGT-53059)
* Ett problem som uppstod när en [!DNL Recommendations]-aktivitet skulle visas i det uppdaterade [!UICONTROL Overview]-gränssnittet, kunde inte läsas in i [!UICONTROL Goals & Settings]-avsnittet när [!DNL Adobe Analytics] (A4T) har valts som rapportkälla har åtgärdats. Följande felmeddelande visades: &quot;Något gick fel. Vi kan inte slutföra din begäran. Kontakta Adobe Client Care om problemet kvarstår.&quot; (TGT-52999)
* Korrigerade ett fel i användargränssnittet för [!DNL Recommendations] där en befordran som skapats med en enskild regel tolkades felaktigt och visades som en erbjudandetyp för&quot;Lista över artiklar&quot;, oavsett regelns logik. (TGT-53063)
* Ett problem har korrigerats när det uppdaterade [!UICONTROL Overview]användargränssnittet [!UICONTROL Download Recommendations Data]-knappen saknades för [!UICONTROL Experience Targeting] (XT)-aktiviteter som innehåller [!DNL Recommendations]. (TGT-52730 &amp; TGT-52756)
* Tidigare visades bara antalet enheter som importerades från en feed i gränssnittet Rekommendationer. Däremot innehåller backend-meddelandeformatet både antalet importerade enheter och det totala antalet enheter i formatet:

  `# of entities imported / # of total entities`

  På grund av den här diskrepansen kunde användare bara se det första värdet (antal importerade) i användargränssnittet, vilket ledde till förvirring. Nu visas båda talen i användargränssnittet. (TGT-53073)

* Korrigerade ett kontextuellt översättningsfel i koreanska nationella inställningar (ko-KR) för strängen Preview Experience. (TGT-52928)
* Fasta terminologinkonsekvenser som identifierats i översättningen av flera textsträngar för förenklad kinesiska (zh_CN). (TGT-52954 &amp; TGT-52955)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
