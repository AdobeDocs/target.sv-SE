---
keywords: visual experience composer options;experience composer options;experience options;edit text;edit html;edit text/html;edit background color;background color;insert element;edit link;link;visual experience composer link;edit css class;css class;swap offer;offer swap;swap image;image swap;remove item;item remove;hide item;item hide;rearrange;move element;element move;resize element;element resize;element;expand selection;navigate to this link;navigate link;link navigate;navigate;link;undo;redo;undo/redo
description: När du klickar på ett sidelement i Adobe Target Visual Experience Composer (VEC) visas de alternativ som är tillgängliga för den elementtypen på en meny.
title: Alternativ för Adobe Target Visual Experience Composer (VEC)
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '2355'
ht-degree: 0%

---


# Alternativ för Visual Experience Composer

När du klickar på ett sidelement i [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) visas de alternativ som är tillgängliga för den elementtypen på en meny. Dessutom visas en DOM-sökväg längst ned på sidan, så att du enkelt kan navigera i sidstrukturen.

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

Flera formateringsalternativ för formaterad text finns tillgängliga när du redigerar text och HTML för [!UICONTROL A/B]- och [!UICONTROL Experience Targeting]-aktiviteter. Du kan välja ett teckensnitt, välja ett teckensnittsformat, ändra textjustering och andra standardalternativ för textformatering. När du ändrar HTML kan du växla mellan kodvyn och den avancerade redigeringsvyn för HTML.

Följande HTML5-taggar kan kapslas:

| Tagg | Tillåtna kapslade taggar |
| --- | --- |
| `<a>` | `<h1-h6>`,  `<p>`,  `<ul>`,  `<ol>`,  `<menu>`,  `<div>`,  `<figure>`,  `<figcaption>` |
| `<ins>` | `<h1-h6>`,  `<p>`,  `<ul>`,  `<ol>`,  `<menu>` |
| `<del>` | `<ul>`,  `<ol>`,  `<menu>`,  `<h1-h6>`,  `<p>` |
| `<label>` | `<p>` |

#### Bakgrundsfärg

Använd färgväljaren för att välja eller konfigurera en bakgrundsfärg. Du kan välja en färgruta och justera den med RGB-värden eller färghexkoder. Det röda krysset i färgväljaren gör bakgrunden genomskinlig.

**Obs!** Det här alternativet är inte tillgängligt för ett element där en bakgrundsbild är inställd.

#### Stilar {#styles}

Använd panelen [!UICONTROL Styles] om du vill visa eller redigera värdet för befintliga format för det markerade elementet. Du kan också lägga till ytterligare format.

Du öppnar panelen [!UICONTROL Styles] genom att klicka på ett sidelement i VEC och sedan på **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

Panelen [!UICONTROL Styles] visas till höger om VEC. Panelen innehåller en lista med format som du kan använda för att redigera eller lägga till i det markerade elementet. Med en CSS-redigerare i realtid kan du visa ändringar och lägga till format om du känner dig bekväm med att använda CSS (Cascading Style Sheets) eller om du tar emot kod från utvecklaren.

![Panelen Format](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

När du använder olika format kan du alltid återställa ändringarna genom att klicka på ikonen [!UICONTROL Revert] som visas i det övre högra hörnet av panelen [!UICONTROL Styles] när du har ändrat något avsnitt. Observera att när du klickar på ikonen [!UICONTROL Revert] återställs alla ändringar på panelen för det aktuella avsnittet.

Expandera varje avsnitt om du vill redigera eller lägga till format, vilket förklaras nedan. Om du vill spara ändringarna klickar du på bakåtikonen längst upp på panelen för att gå tillbaka till panelens huvudvisning och klickar sedan på **[!UICONTROL Save]**.

Observera att blå punkter på huvudpanelen och bredvid varje alternativ på de olika avsnittspanelerna anger att du har ändrat motsvarande format. Det gör det enkelt för dig att granska ändringarna innan du klickar på [!UICONTROL Save].

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

   Target har också stöd för andra storleksenheter, som rem, pc, em, etc. Mer information om de här enheterna finns i [CSS-tips och -tricks för webbformatmallar](https://www.w3.org/Style/Examples/007/units.en.html).

* **Utfyllnad**

   Ändra utfyllnaden för det markerade elementet. Du kan ändra utfyllnaden för vänster, höger, nederkant och överkant.

   Ange utfyllnaden genom att dra i skjutreglaget eller ange antalet pixlar för utfyllnaden.

   Utfyllnaden stöder breddskalor från 0 och framåt.

   Målet stöder också [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), t.ex. rem, pc, em osv.

* **Kant**

   Klicka på kantikonerna högst upp på panelen om du vill ändra det markerade elementets kantlinje.

   Du kan redigera följande format för varje kantlinje (överkant, höger, nederkant och vänster):

   * Kantlinjeformat (ingen, dold, prickad, streckad, heldragen eller dubbel)
   * Kantfärg (ange färgkoden eller använd färgväljaren)
   * Kantbredd (dra reglaget för att välja en kantbredd eller ange bredden i pixlar)

   Kantlinje har stöd för breddskalor från 0 och framåt.

   Målet stöder också [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), t.ex. rem, pc, em osv.

* **Position**

   Flytta det markerade elementet från dess aktuella position. Du kan ändra elementets position överst, nederst, vänster, höger och [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp).

   Klicka på listrutan [!UICONTROL Static] och välj bland följande placeringsalternativ:

   * Statisk
   * Relativ
   * Absolut
   * Fäst
   * Fast

   Klicka på listruteikonen för varje position för att välja bland följande alternativ:

   * Auto
   * Värde (dra skjutreglaget för att placera elementet eller ange antalet pixlar som du vill flytta elementet)

   Position stöder positiva och negativa värden.

   Målet stöder också [andra storleksenheter](https://www.w3.org/Style/Examples/007/units.en.html), t.ex. rem, pc, em osv.

* **Storlek**

   Ändra det markerade elementets bredd och höjd.

   Klicka på listruteikonen bredvid [!UICONTROL Width] och [!UICONTROL Height] och välj bland följande alternativ:

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

   Lägg märke till de blå punkterna bredvid alternativen [!UICONTROL Typography], [!UICONTROL Border] och [!UICONTROL Size] i föregående bild. Dessa punkter indikerar att du har gjort ändringar i de här avsnitten. Om du öppnar de här avsnittspanelerna visas blå punkter bredvid de specifika alternativ som du har ändrat.

   Du kan skriva egen kod om det önskade formatet inte är tillgängligt som standard i [!UICONTROL Styles].

   Tänk på att CSS Editor endast visar information för den aktuella sessionen. Om du sparar ändringarna och sedan öppnar redigeraren igen visas inte information om den tidigare ändringen i redigeraren, även om du väljer samma element igen.

   >[!IMPORTANT]
   >
   >Du kan använda en bakgrundsbild med CSS Editor, men det kan orsaka flimmer. Testa ändringarna före driftsättningen.

#### CSS-klass

Ange den fördefinierade CSS-klass som används för elementet. Om du har markerat flera element avgränsar du flera CSS-klasser med ett mellanslag.

Tillgängligt för [!UICONTROL A/B]-, [!UICONTROL Automated Personalization]- och [!UICONTROL Multivariate Test]-aktiviteter.

#### Länk

Ändra URL-adressen i länken.

Använd Redigera länk för att uppdatera väljaren så att den pekar på samma bildelement. Det går dock inte att länka till ett annat bildelement. Om du vill länka till ett annat bildelement tar du bort den ursprungliga åtgärden från kodredigeraren och använder [!UICONTROL Visual Experience Composer] för att tillämpa åtgärden på det andra bildelementet.

### Infoga före

Följande alternativ är tillgängliga:

#### Bild, HTML och text

Lägg till vilket element som helst på sidan förutom att ändra befintligt innehåll. Lägg till text, kod, listor med mera för att skapa helt olika upplevelser att testa.

Markera ett element på sidan, klicka sedan på [!UICONTROL Insert Before] och välj om du vill infoga en bild, HTML eller text. Det infogade elementet visas före det markerade elementet.

Det infogade elementets beteende beror på sidans struktur, CSS och andra sidkonfigurationsalternativ. Giltig HTML krävs för att sidan ska visas korrekt. Testa alltid sidan när du har infogat ett objekt för att se till att den visas som förväntat.

[!UICONTROL Recommendations] stöder innehållet  [!UICONTROL Insert Before] i DIV-, SECTION- och Article-taggarna.

**Obs!** Om du infogar en bild måste det  [!DNL Adobe Scene7 Publishing System] vara aktiverat så att du har tillgång till bildbiblioteket.

#### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Recommendations som erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Infoga upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target]-aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Infoga efter

Följande alternativ är tillgängliga:

#### Bild, HTML och text

Lägg till vilket element som helst på sidan förutom att ändra befintligt innehåll. Lägg till text, kod, listor med mera för att skapa helt olika upplevelser att testa.

Markera ett element på sidan, klicka sedan på [!UICONTROL Insert After] och välj om du vill infoga en bild, HTML eller text. Det infogade elementet visas efter det markerade elementet.

Det infogade elementets beteende beror på sidans struktur, CSS och andra sidkonfigurationsalternativ. Giltig HTML krävs för att sidan ska visas korrekt. Testa alltid sidan när du har infogat ett objekt för att se till att den visas som förväntat.

[!UICONTROL Recommendations] stöder innehållet  [!UICONTROL Insert After] i DIV-, SECTION- och Article-taggarna.

**Obs!** Om du infogar en bild måste det  [!DNL Adobe Scene7 Publishing System] vara aktiverat så att du har tillgång till bildbiblioteket.

#### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Recommendations som erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Infoga upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target]-aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Ersätt med

Följande alternativ är tillgängliga:

#### Bild

Välj en annan bild i innehållsbiblioteket. De bilder som är tillgängliga för växling omfattar de bilder som har överförts till resursmappen Experience Cloud eller som har överförts till innehållsbiblioteket i Target.

När den inledande aktiviteten skapas är den URL som visas inte den URL som används för leverans. Vid aktivitetssynkronisering uppdateras den URL:en till en Scene7-produktionswebbadress.

Den inledande URL:en kan till exempel se ut som i följande exempel:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Efter aktivitetssynkronisering kan leverans-URL:en se ut som i följande exempel:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations stöder Ersätt med i DIV-, SECTION- och Article-taggar.

**Obs!För** att byta bild krävs ett Adobe Scene7 Publishing System-konto.

#### HTML-erbjudande

Välj ett annat erbjudande från [!UICONTROL Content Library].

**Obs!** HTML-erbjudanden lagras på  [!DNL Target] servrar.

Ett HTML-erbjudande kan vara upp till 256 kB stort.

#### Rekommendation

Inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Recommendations som erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Infoga upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target]-aktiviteter för att underlätta optimering eller personalisering. Mer information finns i [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Layout

Följande alternativ är tillgängliga:

#### Ordna om

Dra elementet till en annan plats inuti samma överordnade element eller DIV. Andra element flyttas för att skapa utrymme för det omordnade elementet.

**Obs!** Klickspårning fungerar inte för omsorterade objekt.

#### Ändra storlek

Ändra storlek på ett element på sidan. När du väljer [!UICONTROL Resize] visas ett handtag i elementets nedre högra hörn som du kan använda för att ändra storlek på genom att dra i hörnet. Håll ned Skift om du vill behålla samma proportioner.

**Obs!Det går inte att ändra storlek på** infogade element.

#### Flytta {#move}

Flytta element på sidan. Till skillnad från alternativet [!UICONTROL Rearrange] flyttar [!UICONTROL Move] inte andra element för att ge plats åt det element som flyttas. Använd piltangenterna för att finjustera flyttningen. (Planerad förbättring: stöd för att se till att flyttade element inte döljs bakom andra element.)

I vissa fall, t.ex. när en CSS-begränsning kräver att ett element ska finnas i det överordnade elementet, kan du inte flytta elementet utanför det överordnade elementet. Ett element kan inte flyttas utanför en behållare som har följande CSS-egenskap: `overflow: hidden`.

#### Dölj

Dölj elementet. Det tomma utrymmet återstår, men innehållet tas bort.

#### Ta bort

Ta bort elementet. Det tomma utrymmet bakom bilden tas bort och det utrymme där elementet var komprimerat.

**Obs!Det går inte att ta bort** objekt i en &quot;klassisk&quot; mbox (en mbox som skapats i en Target Classic-kampanj) med det här alternativet.

### Expandera avsnitt

Markera det överordnade elementet förutom det ursprungligen markerade elementet. När du markerar ett överordnat element markeras alla underordnade element automatiskt. Du kan expandera markeringen flera gånger.

### Navigera till länk

Öppna länkens mål.

### Ångra/Gör om

Ångra ändringar du gör i dina aktiviteter under en redigeringssession. Du kan också göra om ändringar som tidigare har ångrats.

## Överväganden {#considerations}

* Om ett erbjudande innehåller HTML-innehåll kan du läsa &quot;How at.js renders offers with HTML content&quot; i [How at.js works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render) för mer information.

## Navigera mellan element med DOM-sökvägen {#dom-path}

När du klickar på ett element på sidan visas VEC-alternativmenyn. När du klickar på ett element visas dessutom motsvarande DOM-sökväg längst ned på sidan.

![DOM-sökväg](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Du kan använda DOM-sökvägen för att snabbt visa information om det markerade elementet (typ, ID och klass) och flytta upp eller ned DOM-sökvägen för att markera det önskade elementet.

När du hovrar över DOM-banan markeras motsvarande element i VEC med en blå ruta. När du klickar på elementet markeras elementet med en orange ruta och VEC-alternativmenyn visas, vilket förklaras ovan.

Du kan enkelt navigera till alla överordnade, jämställda eller underordnade element inom VEC med DOM-sökvägen.

DOM-sökvägsfunktionen är också tillgänglig när du konfigurerar [klickspårning](/help/c-activities/r-success-metrics/click-tracking.md).