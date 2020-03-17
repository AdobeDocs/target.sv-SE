---
keywords: visual experience composer options;experience composer options;experience options;edit text;edit html;edit text/html;edit background color;background color;insert element;edit link;link;visual experience composer link;edit css class;css class;swap offer;offer swap;swap image;image swap;remove item;item remove;hide item;item hide;rearrange;move element;element move;resize element;element resize;element;expand selection;navigate to this link;navigate link;link navigate;navigate;link;undo;redo;undo/redo
description: När du klickar på ett sidelement i Adobe Target Visual Experience Composer (VEC) visas de alternativ som är tillgängliga för den elementtypen på en meny.
title: Alternativ för Adobe Target Visual Experience Composer (VEC)
topic: Standard
uuid: efd672ae-c684-455f-8ec1-0efcfe1e9534
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Alternativ för Visual Experience Composer{#visual-experience-composer-options}

När du klickar på ett sidelement i Visual Experience Composer (VEC) visas de alternativ som är tillgängliga för den elementtypen på en meny. Dessutom visas en DOM-sökväg längst ned på sidan, så att du enkelt kan navigera i sidstrukturen.

## VEC-alternativ

De olika VEC-åtgärderna (Visual Experience Composer) grupperas med lämpliga menyalternativ för att göra jobbet snabbare och effektivare:

![VEC-alternativmeny](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>Vilka alternativ som är tillgängliga beror på vilken typ av aktivitet du redigerar.

### Redigera

Följande alternativ är tillgängliga:

#### Text/HTML {#edit-text-html}

Ändra HTML-koden för elementet, till exempel texten för ett textområde, en knapp eller en länk.

Förutom HTML-kod kan du redigera och mata in egen JavaScript.

Det finns flera alternativ för formatering av formaterad text när du redigerar text och HTML för [!UICONTROL A/B] - och [!UICONTROL Experience Targeting] -aktiviteter. Du kan välja ett teckensnitt, välja ett teckensnittsformat, ändra textjustering och andra standardalternativ för textformatering. När du ändrar HTML kan du växla mellan kodvyn och redigeringsvyn för HTML.

Följande HTML5-taggar kan kapslas:

| Tagg | Tillåtna kapslade taggar |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

#### Bakgrundsfärg

Använd färgväljaren för att välja eller konfigurera en bakgrundsfärg. Du kan välja en färgruta och justera den med RGB-värden eller färghexkoder. Det röda krysset i färgväljaren gör bakgrunden genomskinlig.

**Obs!** Det här alternativet är inte tillgängligt för ett element där en bakgrundsbild är inställd.

#### Stilar {#styles}

Använd panelen för att visa eller redigera värdet för befintliga format för det markerade elementet [!UICONTROL Styles] . Du kan också lägga till ytterligare format.

Du öppnar panelen genom att klicka på ett sidelement i VEC-fönstret och sedan klicka på [!UICONTROL Styles] > **[!UICONTROL Edit]** **[!UICONTROL Styles]**.

Panelen visas till höger [!UICONTROL Styles] om VEC. Panelen innehåller en lista med format som du kan använda för att redigera eller lägga till i det markerade elementet. Med en CSS-redigerare i realtid kan du visa ändringar och lägga till format om du känner dig bekväm med att använda CSS (Cascading Style Sheets) eller om du tar emot kod från utvecklaren.

![Panelen Format](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

När du använder olika format kan du alltid återställa ändringarna genom att klicka på den [!UICONTROL Revert] ikon som visas längst upp till höger på [!UICONTROL Styles] panelen när du har ändrat något avsnitt. Observera att när du klickar på [!UICONTROL Revert] ikonen återställs alla ändringar på panelen för det aktuella avsnittet.

Expandera varje avsnitt om du vill redigera eller lägga till format, vilket förklaras nedan. Om du vill spara ändringarna klickar du på bakåtikonen längst upp på panelen för att gå tillbaka till panelens huvudvisning och klickar sedan på **[!UICONTROL Save]**.

Observera att blå punkter på huvudpanelen och bredvid varje alternativ på de olika avsnittspanelerna anger att du har ändrat motsvarande format. Det gör det enkelt för dig att granska ändringarna innan du klickar [!UICONTROL Save].

>[!NOTE]
>
>Snabbåtgärder för layoutändringar, bakgrundsfärg, storleksändring och flyttning finns också tillgängliga som separata åtgärder på VEC-menyn. Dessa alternativ kan användas som separata åtgärder eller så kan du använda menyn Format, vilket förklaras här.

* **Bakgrund**

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

* **Typografi**

   Ändra ett elements typografi. Det går snabbt och enkelt att redigera typografi.

   Även om RTF-redigeraren (Redigera text/HTML) är tillgänglig för finjustering är snabbåtgärder för att göra ändringar i hela elementet tillgängliga med det här alternativet. Om du bara vill använda typografiska ändringar på en del av texten (inte på den fullständiga texten) använder du [RTF-redigeraren](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

   Du kan redigera följande typografiska format:

   * Teckenstorlek
   * Teckenbredd
   * Teckensnittsformat
   * Färg (ange färgkoden eller använd färgväljaren)
   * Ordmellanrum
   * Radhöjd
   * Textjustering

* **Marginal**

   Ändra marginalen för det markerade elementet. Du kan ändra marginalerna för vänster, höger, under och över.

   Klicka på listruteikonen för varje marginal för att välja mellan följande alternativ:

   * Auto
   * Värde (dra i skjutreglaget för att ange marginalen eller ange antalet pixlar för varje marginal)
   Marginalen har stöd för positiva och negativa värden.

   Target har också stöd för andra storleksenheter, som rem, pc, em, etc. Mer information om de här enheterna finns i CSS-tips och -tricks för [webbformatmallar](https://www.w3.org/Style/Examples/007/units.en.html).

* **Utfyllnad**

   Ändra utfyllnaden för det markerade elementet. Du kan ändra utfyllnaden för vänster, höger, nederkant och överkant.

   Ange utfyllnaden genom att dra i skjutreglaget eller ange antalet pixlar för utfyllnaden.

   Utfyllnaden stöder breddskalor från 0 och framåt.

   Target har också stöd för [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), som rem, pc, em, etc.

* **Kant**

   Klicka på kantikonerna högst upp på panelen om du vill ändra det markerade elementets kantlinje.

   Du kan redigera följande format för varje kantlinje (överkant, höger, nederkant och vänster):

   * Kantlinjeformat (ingen, dold, prickad, streckad, heldragen eller dubbel)
   * Kantfärg (ange färgkoden eller använd färgväljaren)
   * Kantbredd (dra reglaget för att välja en kantbredd eller ange bredden i pixlar)
   Kantlinje har stöd för breddskalor från 0 och framåt.

   Target har också stöd för [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), som rem, pc, em, etc.

* **Position**

   Flytta det markerade elementet från dess aktuella position. Du kan ändra elementets placering i över-, under-, vänster-, höger- och [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) .

   Klicka på den [!UICONTROL Static] nedrullningsbara listan och välj bland följande placeringsalternativ:

   * Statisk
   * Relativ
   * Absolut
   * Fäst
   * Fast
   Klicka på listruteikonen för varje position för att välja bland följande alternativ:

   * Auto
   * Värde (dra skjutreglaget för att placera elementet eller ange antalet pixlar som du vill flytta elementet)
   Position stöder positiva och negativa värden.

   Target har också stöd för [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), som rem, pc, em, etc.

* **Storlek**

   Ändra det markerade elementets bredd och höjd.

   Klicka på listruteikonen bredvid [!UICONTROL Width] och [!UICONTROL Height] välj bland följande alternativ:

   * Auto
   * Värde (dra skjutreglaget för att ändra storlek på elementet eller ange antalet pixlar för varje dimension)

* **Filter**

   Dra skjutreglaget för varje filteralternativ eller ange önskad procentsats:

   * Sepia
   * Kontrast
   * Intensitet
   * Gråskala
   * Oskärpa
   * Opacitet
   * Invertera
   * Nyansrotering
   * Mätta

* **CSS Editor**

   Med CSS Editor i realtid kan du visa ändringar och lägga till format om du känner dig trygg med att använda CSS (Cascading Style Sheets) eller om du tar emot kod från utvecklaren.

   CSS Editor visar alla ändringar som du gör på formatpanelen. Som framgår av bilden nedan har teckensnittsstorleken, den övre kanten och bildstorleken ändrats:

   ![CSS-redigerare med ändringar](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   Lägg märke till de blå punkterna bredvid [!UICONTROL Typography], [!UICONTROL Border]och [!UICONTROL Size] alternativen i föregående bild. Dessa punkter indikerar att du har gjort ändringar i de här avsnitten. Om du öppnar de här avsnittspanelerna visas blå punkter bredvid de specifika alternativ som du har ändrat.

   Du kan skriva egen kod om det önskade formatet inte är tillgängligt som standard i [!UICONTROL Styles].

   Tänk på att CSS Editor endast visar information för den aktuella sessionen. Om du sparar ändringarna och sedan öppnar redigeraren igen visas inte information om den tidigare ändringen i redigeraren, även om du väljer samma element igen.

   >[!Iviktig]
   >
   >Du kan använda en bakgrundsbild med CSS Editor, men det kan orsaka flimmer. Testa ändringarna före driftsättningen.

#### CSS-klass

Ange den fördefinierade CSS-klass som används för elementet. Om du har markerat flera element avgränsar du flera CSS-klasser med ett mellanslag.

Tillgängligt för [!UICONTROL A/B], [!UICONTROL Automated Personalization]och [!UICONTROL Multivariate Test] aktiviteter.

#### Länk

Ändra URL-adressen i länken.

Använd Redigera länk för att uppdatera väljaren så att den pekar på samma bildelement. Det går dock inte att länka till ett annat bildelement. Om du vill länka till ett annat bildelement tar du bort den ursprungliga åtgärden från kodredigeraren och använder åtgärden [!UICONTROL Visual Experience Composer] för det andra bildelementet.

### Infoga före

Följande alternativ är tillgängliga:

#### Bild, HTML och text

Lägg till vilket element som helst på sidan förutom att ändra befintligt innehåll. Lägg till text, kod, listor med mera för att skapa helt olika upplevelser att testa.

Markera ett element på sidan, klicka [!UICONTROL Insert Before] och välj om du vill infoga en bild, HTML eller text. Det infogade elementet visas före det markerade elementet.

Det infogade elementets beteende beror på sidans struktur, CSS och andra sidkonfigurationsalternativ. Giltig HTML krävs för att sidan ska visas korrekt. Testa alltid sidan när du har infogat ett objekt för att se till att den visas som förväntat.

[!UICONTROL Recommendations] stöder innehållet [!UICONTROL Insert Before] i DIV-, SECTION- och Article-taggarna.

**Obs!** Om du vill infoga en bild måste det [!DNL Adobe Scene7 Publishing System] vara aktiverat så att du har tillgång till bildbiblioteket.

#### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Infoga upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target] aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Infoga efter

Följande alternativ är tillgängliga:

#### Bild, HTML och text

Lägg till vilket element som helst på sidan förutom att ändra befintligt innehåll. Lägg till text, kod, listor med mera för att skapa helt olika upplevelser att testa.

Markera ett element på sidan, klicka [!UICONTROL Insert After] och välj om du vill infoga en bild, HTML eller text. Det infogade elementet visas efter det markerade elementet.

Det infogade elementets beteende beror på sidans struktur, CSS och andra sidkonfigurationsalternativ. Giltig HTML krävs för att sidan ska visas korrekt. Testa alltid sidan när du har infogat ett objekt för att se till att den visas som förväntat.

[!UICONTROL Recommendations] stöder innehållet [!UICONTROL Insert After] i DIV-, SECTION- och Article-taggarna.

**Obs!** Om du vill infoga en bild måste det [!DNL Adobe Scene7 Publishing System] vara aktiverat så att du har tillgång till bildbiblioteket.

#### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Infoga upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target] aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Ersätt med

Följande alternativ är tillgängliga:

#### Bild

Välj en annan bild i innehållsbiblioteket. De bilder som är tillgängliga för växling omfattar de bilder som har överförts till Experience Cloud-resursmappen eller överförts till innehållsbiblioteket i Target.

När den inledande aktiviteten skapas är den URL som visas inte den URL som används för leverans. När aktiviteten synkroniseras uppdateras URL:en till en produktionsscen7-URL.

Den inledande URL:en kan till exempel se ut som i följande exempel:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Efter aktivitetssynkronisering kan leverans-URL:en se ut som i följande exempel:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Rekommendationer har stöd för Ersätt med i DIV-, SECTION- och Article-taggar.

**Obs!** För att kunna byta ut bilder måste du ha ett Adobe Scene7 Publishing System-konto.

#### HTML-erbjudande

Välj ett annat erbjudande från [!UICONTROL Content Library].

**Obs!** HTML-erbjudanden lagras på [!DNL Target] servrar.

Ett HTML-erbjudande kan vara upp till 256 kB stort.

#### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Infoga upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target] aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Layout

Följande alternativ är tillgängliga:

#### Ordna om

Dra elementet till en annan plats inuti samma överordnade element eller DIV. Andra element flyttas för att skapa utrymme för det omordnade elementet.

**Obs!** Klickspårning fungerar inte för omsorterade objekt.

#### Ändra storlek

Ändra storlek på ett element på sidan. När du väljer [!UICONTROL Resize]det här alternativet visas ett handtag i elementets nedre högra hörn som du kan använda till att ändra storlek på genom att dra i hörnet. Håll ned Skift om du vill behålla samma proportioner.

**Obs!** Det går inte att ändra storlek på infogade element.

#### Flytta {#move}

Flytta element på sidan. Till skillnad från [!UICONTROL Rearrange] alternativet flyttas [!UICONTROL Move] inte andra element för att ge plats åt elementet som flyttas. Använd piltangenterna för att finjustera flyttningen. (Planerad förbättring: stöd för att se till att flyttade element inte döljs bakom andra element.)

I vissa fall, t.ex. när en CSS-begränsning kräver att ett element ska finnas i det överordnade elementet, kan du inte flytta elementet utanför det överordnade elementet. Ett element kan inte flyttas utanför en behållare som har följande CSS-egenskap: `overflow: hidden`.

#### Dölj

Dölj elementet. Det tomma utrymmet återstår, men innehållet tas bort.

#### Ta bort

Ta bort elementet. Det tomma utrymmet bakom bilden tas bort och det utrymme där elementet var komprimerat.

**Obs!** Det går inte att ta bort objekt i en klassisk mbox (en mbox som skapats i en Target Classic-kampanj) med det här alternativet.

### Expandera avsnitt

Markera det överordnade elementet förutom det ursprungligen markerade elementet. När du markerar ett överordnat element markeras alla underordnade element automatiskt. Du kan expandera markeringen flera gånger.

### Navigera till länk

Öppna länkens mål.

### Ångra/Gör om

Ångra ändringar du gör i dina aktiviteter under en redigeringssession. Du kan också göra om ändringar som tidigare har ångrats.

## Överväganden {#considerations}

* Om ett erbjudande innehåller HTML-innehåll kan du läsa&quot;How at.js renders offers with HTML content&quot; i [How at.js works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render) för mer information.

## Navigera mellan element med DOM-sökvägen {#dom-path}

När du klickar på ett element på sidan visas VEC-alternativmenyn. När du klickar på ett element visas dessutom motsvarande DOM-sökväg längst ned på sidan.

![DOM-sökväg](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Du kan använda DOM-sökvägen för att snabbt visa information om det markerade elementet (typ, ID och klass) och flytta upp eller ned DOM-sökvägen för att markera det önskade elementet.

När du hovrar över DOM-banan markeras motsvarande element i VEC med en blå ruta. När du klickar på elementet markeras elementet med en orange ruta och VEC-alternativmenyn visas, vilket förklaras ovan.

Du kan enkelt navigera till alla överordnade, jämställda eller underordnade element inom VEC med DOM-sökvägen.

DOM-sökvägsfunktionen är också tillgänglig när du ställer in [klickspårning](/help/c-activities/r-success-metrics/click-tracking.md).