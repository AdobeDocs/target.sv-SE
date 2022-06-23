---
keywords: alternativ för visuell upplevelsedisposition;alternativ för upplevelsedisposition;alternativ för upplevelser;redigera text;redigera html;redigera text/html;redigera bakgrundsfärg;bakgrundsfärg;infoga element;redigera länk;länk för disposition;redigera CSS-klass;css-klass;swap offer swap;swap image;remove item remove;item remove;item remove;item hide;move element;move move;element move element;resize element;element resielement expandera markering;navigera till den här länken;navigera länk;navigera;navigera;länk;ångra;gör om;göra om;anpassade händelser;webbkomponenter;erbjudandebeslut;offer decisioning
description: Se vilka alternativ som finns i [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).
title: Hur jag använder [!UICONTROL Visual Experience Composer] (VEC) Alternativ?
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '2740'
ht-degree: 0%

---

# Alternativ för Visual Experience Composer

När du klickar på ett sidelement i [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) visar en meny de alternativ som är tillgängliga för den elementtypen. Dessutom visas en DOM-sökväg längst ned på sidan, så att du enkelt kan navigera i sidstrukturen.

De olika [!UICONTROL Visual Experience Composer] (VEC)-åtgärder grupperas i lämpliga menyalternativ för att göra jobbet snabbare och effektivare:

![VEC-alternativmeny](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>Vilka alternativ som är tillgängliga beror på vilken typ av aktivitet du skapar eller redigerar.

## [!UICONTROL Edit]

Följande alternativ är tillgängliga:

### [!UICONTROL Text/HTML] {#edit-text-html}

Ändra HTML-koden för elementet, till exempel texten för ett textområde, en knapp eller en länk.

Förutom HTML-kod kan du redigera och mata in anpassad JavaScript.

Flera formateringsalternativ för formaterad text är tillgängliga när du redigerar text och HTML för [!UICONTROL A/B] och [!UICONTROL Experience Targeting] verksamhet. Du kan välja ett teckensnitt, välja ett teckensnittsformat, ändra textjustering och andra standardalternativ för textformatering. När du ändrar HTML kan du växla mellan kodvyn och den avancerade redigeringsvyn för HTML.

Följande HTML5-taggar kan kapslas:

| Tagg | Tillåtna kapslade taggar |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

Använd färgväljaren för att välja eller konfigurera en bakgrundsfärg. Du kan välja en färgruta och justera den med hjälp av RGB-värden eller färghexkoder. Det röda krysset i färgväljaren gör bakgrunden genomskinlig.

**Obs!** Det här alternativet är inte tillgängligt för ett element där en bakgrundsbild är inställd.

### [!UICONTROL Styles] {#styles}

Använd [!UICONTROL Styles] om du vill visa eller redigera värdet för det markerade elementets befintliga format. Du kan också lägga till ytterligare format.

Så här öppnar du [!UICONTROL Styles] klickar du på ett sidelement i VEC och sedan på **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] visas till höger om VEC. Panelen innehåller en lista med format som du kan använda för att redigera eller lägga till i det markerade elementet. Med en CSS-redigerare i realtid kan du visa ändringar och lägga till format om du känner dig bekväm med att använda CSS (Cascading Style Sheets) eller om du tar emot kod från utvecklaren.

![Panelen Format](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

När du använder olika format kan du alltid återställa ändringarna genom att klicka på [!UICONTROL Revert] ikon som visas i det övre högra hörnet av [!UICONTROL Styles] när du har ändrat något avsnitt. Klicka på [!UICONTROL Revert] ikonen återställer alla ändringar på panelen för det aktuella avsnittet.

Expandera varje avsnitt om du vill redigera eller lägga till format, vilket förklaras nedan. Spara ändringarna genom att klicka på [!UICONTROL Back] ikonen längst upp på panelen för att gå tillbaka till panelens huvudskärm och klicka sedan på **[!UICONTROL Save]**.

De blå punkterna på huvudpanelen och bredvid varje alternativ på de olika avsnittspanelerna anger att du har ändrat motsvarande format. Den här visuella indikatorn gör det enkelt för dig att granska ändringarna innan du klickar [!UICONTROL Save].

>[!NOTE]
>
>Snabbåtgärder för layoutändringar, bakgrundsfärg, storleksändring och flyttning finns också tillgängliga som separata åtgärder på VEC-menyn. Dessa alternativ kan användas som separata åtgärder eller så kan du använda menyn Format, vilket förklaras här.

* **[!UICONTROL Background]**

   Ändra bakgrundsfärg och bild.

   * Färg (ange färgkoden eller använd färgväljaren)
   * Bild (välj en bild i bildväljaren)
   * Bildkälla (ange en extern URL)
   * Bifogad fil
      * Klicka på den övre listrutan för att välja rullning, fast eller lokal
      * Klicka på den nedre listrutan för att välja upprepning, upprepning, x, upprepning, ingen upprepning, mellanrum eller rund
   * Klipp
      * Klicka på den övre listrutan för att välja kantlinje, utfyllnadslåda, innehållslåda eller text
      * Klicka på den nedre listrutan för att välja automatiskt ljud eller ljud

* **[!UICONTROL Typography]**

   Ändra ett elements typografi. Det går snabbt och enkelt att redigera typografi.

   Även om RTF-redigeraren (Redigera text/HTML) är tillgänglig för finjustering är snabbåtgärder för att ändra hela elementet tillgängliga med det här alternativet. Om du bara vill använda typografiska ändringar på en del av texten (inte på hela texten) använder du [textredigerare](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

   Du kan redigera följande typografiska format:

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] (ange färgkoden eller använd färgväljaren)
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

   Ändra marginalen för det markerade elementet. Du kan ändra marginalerna för vänster, höger, under och över.

   Klicka på listruteikonen för varje marginal för att välja mellan följande alternativ:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (dra reglaget för att ange marginalen eller ange antalet pixlar för varje marginal)

   Marginalen har stöd för positiva och negativa värden.

   Target har också stöd för andra storleksenheter, som rem, pc, em. Mer information om dessa enheter finns i [CSS-tips och -tricks för webbformatmallar](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

   Ändra utfyllnaden för det markerade elementet. Du kan ändra utfyllnaden för vänster, höger, nederkant och överkant.

   Ange utfyllnaden genom att dra i skjutreglaget eller ange antalet pixlar för utfyllnaden.

   Utfyllnaden stöder breddskalor från 0 och framåt.

   Target har även stöd för [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), som rem, pc, em.

* **[!UICONTROL Border]**

   Klicka på kantikonerna högst upp på panelen om du vill ändra det markerade elementets kantlinje.

   Du kan redigera följande format för varje kantlinje (överkant, höger, nederkant och vänster):

   * [!UICONTROL Border style] (ingen, dold, prickad, streckad, heldragen eller dubbel)
   * [!UICONTROL Border color] (ange färgkoden eller använd färgväljaren)
   * [!UICONTROL Border width] (dra reglaget för att välja en kantbredd eller ange bredden i pixlar)

   Kantlinje har stöd för breddskalor från 0 och framåt.

   Target har även stöd för [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), som rem, pc, em.

* **[!UICONTROL Position]**

   Flytta det markerade elementet från dess aktuella position. Du kan ändra elementets övre, nedre, vänstra, högra och [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

   Klicka på [!UICONTROL Static] nedrullningsbar lista där du kan välja bland följande placeringsalternativ:

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

   Klicka på listruteikonen för varje position för att välja bland följande alternativ:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (dra skjutreglaget för att placera elementet eller ange antalet pixlar som du vill flytta elementet)

   Position stöder positiva och negativa värden.

   Target har även stöd för [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), som rem, pc, em.

* **[!UICONTROL Size]**

   Ändra det markerade elementets bredd och höjd.

   Klicka på listruteikonen bredvid [!UICONTROL Width] och [!UICONTROL Height] för att välja bland följande alternativ:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (dra skjutreglaget för att ändra storlek på elementet eller ange antalet pixlar för varje dimension)

* **[!UICONTROL Filter]**

   Dra skjutreglaget för varje filteralternativ eller ange önskad procentsats:

   * [!UICONTROL Sepia]
   * [!UICONTROL Contrast]
   * [!UICONTROL Brightness]
   * [!UICONTROL GrayScale]
   * [!UICONTROL Blur]
   * [!UICONTROL Opacity]
   * [!UICONTROL Invert]
*
[!UICONTROL  Hue-rotate]
   * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

   Med CSS Editor i realtid kan du visa ändringar och lägga till format om du känner dig bekväm med att använda CSS (Cascading Style Sheets) eller om du tar emot kod från utvecklaren.

   CSS Editor visar alla ändringar som du gör på formatpanelen. Som framgår av bilden nedan har teckensnittsstorleken, den övre kanten och bildstorleken ändrats:

   ![CSS-redigerare med ändringar](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   Lägg märke till de blå punkterna bredvid [!UICONTROL Typography], [!UICONTROL Border]och [!UICONTROL Size] i föregående bild. Dessa punkter indikerar att du har ändrat de här avsnitten. Om du öppnar de här avsnittspanelerna visas blå punkter bredvid de specifika alternativ som du har ändrat.

   Du kan skriva egen kod om det önskade formatet inte är tillgängligt som standard i [!UICONTROL Styles].

   CSS Editor visar endast information för den aktuella sessionen. Om du sparar ändringarna och sedan öppnar redigeraren igen visas inte information om den tidigare ändringen i redigeraren, även om du väljer samma element igen.

   >[!IMPORTANT]
   >
   >Du kan använda en bakgrundsbild med CSS Editor, men det kan orsaka flimmer. Testa ändringarna före driftsättningen.

### [!UICONTROL CSS Class]

Ange den fördefinierade CSS-klass som används för elementet. Om du har markerat flera element avgränsar du flera CSS-klasser med ett mellanslag.

Finns för [!UICONTROL A/B], [!UICONTROL Automated Personalization]och [!UICONTROL Multivariate Test] verksamhet.

### [!UICONTROL Link]

Ändra URL-adressen i länken.

Använd Redigera länk för att uppdatera väljaren så att den pekar på samma bildelement. Det går dock inte att länka till ett annat bildelement. Om du vill länka till ett annat bildelement tar du bort den ursprungliga åtgärden från kodredigeraren och använder kommandot [!UICONTROL Visual Experience Composer] om du vill använda åtgärden på det andra bildelementet.

## [!UICONTROL Insert Before]

Följande alternativ är tillgängliga:

### [!UICONTROL Offer Decision]

Lägg till en [erbjudande skapat i [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} för att presentera det bästa erbjudandet och upplevelsen för era kunder med hjälp av offer decisioning.

**Obs!** Det här alternativet är tillgängligt när du redigerar eller skapar [manuell [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) eller [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) endast aktiviteter. Det här alternativet är inte tillgängligt för andra aktivitetstyper.

Mer information finns i [Använd offertbeslut](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML]och [!UICONTROL Text]

Lägg till vilket element som helst på sidan förutom att ändra befintligt innehåll. Lägg till text, kod, listor med mera för att skapa helt olika upplevelser att testa.

Markera ett element på sidan och klicka sedan på [!UICONTROL Insert Before] och välja om du vill infoga en bild, HTML eller text. Det infogade elementet visas före det markerade elementet.

Det infogade elementets beteende beror på sidans struktur, CSS och andra sidkonfigurationsalternativ. Du måste ange HTML för att sidan ska visas korrekt. Testa alltid sidan när du har infogat ett objekt för att se till att den visas som förväntat.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] innehållet i DIV-, SECTION- och Article-taggarna.

**Obs!** Om du infogar en bild måste du [!DNL Adobe Scene7 Publishing System] är aktiverat så att du har tillgång till bildbiblioteket.

### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Infoga upplevelsefragment skapade i [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

Följande alternativ är tillgängliga:

### [!UICONTROL Offer Decision]

Lägg till en [erbjudande skapat i [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} för att presentera det bästa erbjudandet och upplevelsen för era kunder med hjälp av offer decisioning.

**Obs!** Det här alternativet är tillgängligt när du redigerar eller skapar [manuell [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) eller [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) endast aktiviteter. Det här alternativet är inte tillgängligt för andra aktivitetstyper.

Mer information finns i [Använd offertbeslut](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML]och [!UICONTROL Text]

Lägg till vilket element som helst på sidan förutom att ändra befintligt innehåll. Lägg till text, kod, listor med mera för att skapa helt olika upplevelser att testa.

Markera ett element på sidan och klicka sedan på [!UICONTROL Insert After] och välja om du vill infoga en bild, HTML eller text. Det infogade elementet visas efter det markerade elementet.

Det infogade elementets beteende beror på sidans struktur, CSS och andra sidkonfigurationsalternativ. Du måste ange HTML för att sidan ska visas korrekt. Testa alltid sidan när du har infogat ett objekt för att se till att den visas som förväntat.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] innehållet i DIV-, SECTION- och Article-taggarna.

**Obs!** Om du infogar en bild måste du [!DNL Adobe Scene7 Publishing System] är aktiverat så att du har tillgång till bildbiblioteket.

### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Infoga upplevelsefragment skapade i [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

Följande alternativ är tillgängliga:

### [!UICONTROL Offer Decision]

Lägg till en [erbjudande skapat i [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} för att presentera det bästa erbjudandet och upplevelsen för era kunder med hjälp av offer decisioning.

**Obs!** Det här alternativet är tillgängligt när du redigerar eller skapar [manuell [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) eller [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) endast aktiviteter. Det här alternativet är inte tillgängligt för andra aktivitetstyper.

Mer information finns i [Använd offertbeslut](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Välj en annan bild i innehållsbiblioteket. De bilder som är tillgängliga för växling omfattar de bilder som har överförts till resursmappen Experience Cloud eller som har överförts till innehållsbiblioteket i Target.

När den inledande aktiviteten skapas är den URL som visas inte den URL som används för leverans. Vid aktivitetssynkronisering uppdateras den URL:en till en Scene7-produktionswebbadress.

Den inledande URL:en kan till exempel se ut som i följande exempel:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Efter aktivitetssynkronisering kan leverans-URL:en se ut som i följande exempel:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations stöder Ersätt med i DIV-, SECTION- och Article-taggar.

**Obs!** Du måste ha ett Adobe Scene7 Publishing System-konto för att kunna byta bilder.

### [!UICONTROL HTML Offer]

Välj ett annat erbjudande på [!UICONTROL Content Library].

**Obs!** HTML-erbjudanden lagras på [!DNL Target] servrar.

Ett HTML-erbjudande kan vara upp till 256 kB.

### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Infoga upplevelsefragment skapade i [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

Följande alternativ är tillgängliga:

### [!UICONTROL Rearrange]

Dra elementet till en annan plats inuti samma överordnade element eller DIV. Andra element flyttas för att skapa utrymme för det omordnade elementet.

**Anteckning**: Klickspårning fungerar inte för omsorterade objekt.

För närvarande finns det vissa VEC-åtgärder, som [!UICONTROL Rearrange] och [!UICONTROL Move], anta att elementen på samma nivå i det överordnade käll- och målelementet är helt inlästa. Om lat inläsningsbeteende inträffar under det överordnade DOM-elementet (källa eller mål) kan dessa VEC-åtgärder orsaka inkonsekvent beteende. Vi arbetar på en mer tillförlitlig strategi för att få VEC-åtgärder att fungera i lazy-fyllda DOM-element. Som tillfällig lösning kan du använda [!UICONTROL Custom Code] i dessa scenarier för att återge era upplevelser.

### [!UICONTROL Resize]

Ändra storlek på ett element på sidan. När du väljer [!UICONTROL Resize]visas ett handtag längst ned till höger i elementet. Du kan dra i hörnet för att ändra storlek. Håll ned Skift om du vill behålla samma proportioner.

**Obs!** Det går inte att ändra storlek på infogade element.

### [!UICONTROL Move] {#move}

Flytta element på sidan. Till skillnad från [!UICONTROL Rearrange] option, [!UICONTROL Move] flyttar inte andra element för att ge plats åt elementet som flyttas. Använd piltangenterna för att finjustera flyttningen. (Planerad förbättring: för att säkerställa att flyttade element inte döljs bakom andra element.)

I vissa situationer, t.ex. när en CSS-begränsning kräver att ett element ska finnas i det överordnade elementet, kan du inte flytta elementet utanför det överordnade elementet. Ett element kan inte flyttas utanför en behållare som har följande CSS-egenskap: `overflow: hidden`.

Se [!UICONTROL Rearrange] om du vill ha mer information om inkonsekvent beteende med [!UICONTROL Move] och [!UICONTROL Rearrange] åtgärder på grund av lat inläsande av DOM-element.

### [!UICONTROL Hide]

Dölj elementet. Det tomma utrymmet återstår, men innehållet tas bort.

### [!UICONTROL Remove]

Ta bort elementet. Det tomma utrymmet bakom bilden tas bort och det utrymme där elementet var komprimerat.

**Obs!** Det går inte att ta bort objekt i en klassisk mbox (en mbox som skapats i en Target Classic-kampanj) med det här alternativet.

## [!UICONTROL Expand Section]

Markera det överordnade elementet förutom det ursprungligen markerade elementet. När du markerar ett överordnat element markeras alla underordnade element automatiskt. Du kan expandera markeringen flera gånger.

## [!UICONTROL Navigate to Link]

Öppna länkens mål.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Ångra ändringar du gör i dina aktiviteter under en redigeringssession. Du kan också göra om ändringar som tidigare har ångrats.

## Överväganden {#considerations}

* Om ett erbjudande innehåller HTML finns mer information i&quot;How at.js renders offers with HTML content&quot; i [Hur at.js fungerar](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/) för mer information.

## Stöd för anpassade element {#custom}

VEC stöder [Webbkomponenter](https://developer.mozilla.org/en-US/docs/Web/Web_Components) så att ni kan skapa och testa personaliserade upplevelser och erbjudanden för anpassade element och element inuti anpassade element. Den här funktionen är tillgänglig i VEC för alla [!DNL Target] aktivitetstyper.

>[!NOTE]
>
>VEC-stöd för anpassade element stöds i [at.js version](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) 2.7.0 (eller senare). Kontrollera att rätt version är distribuerad på webbplatsen. Om du använder [Hjälptillägg för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)måste den också ha den version av at.js som krävs distribuerad. De VEC-alternativ som beskrivs ovan är inte synliga och tillgängliga för användning med versioner av at.js som inte stöds.
>
>VEC-stöd för anpassade element stöds för närvarande inte med [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/).

De flesta VEC-åtgärder stöds för anpassade händelser och i anpassade händelser, med följande undantag:

Följande åtgärder är inte tillgängliga för anpassade element:

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

Följande åtgärd är inte tillgänglig i anpassade element:

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## Navigera mellan element med DOM-sökvägen {#dom-path}

När du klickar på ett element på sidan visas VEC-alternativmenyn. När du klickar på ett element visas dessutom motsvarande DOM-sökväg längst ned på sidan.

![DOM-sökväg](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Du kan använda DOM-sökvägen för att snabbt visa information om det markerade elementet (typ, ID och klass) och flytta upp eller ned DOM-sökvägen för att markera det önskade elementet.

När du hovrar över DOM-banan markeras motsvarande element i VEC med en blå ruta. När du klickar på elementet markeras elementet med en orange ruta och VEC-alternativmenyn visas, vilket förklaras ovan.

Du kan enkelt navigera till alla överordnade, jämställda eller underordnade element inom VEC med DOM-sökvägen.

DOM-sökvägsfunktionen är också tillgänglig när du konfigurerar [klickspärra/knip](/help/main/c-activities/r-success-metrics/click-tracking.md).
