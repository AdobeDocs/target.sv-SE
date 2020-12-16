---
description: Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar du kan ställas inför när du använder Automated Personalization, och några förslag på lösningar.
title: Felsöka Automated Personalization
feature: ap
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMTroubleshoot Automated Personalization{#troubleshoot-automated-personalization}

Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar du kan ställas inför när du använder Automated Personalization, och några förslag på lösningar.

## Min AP-aktivitet tar för lång tid att skapa modeller. {#section_20028B204DBB4D77A324BA193434AEE2}

Det finns flera ändringar av aktivitetsinställningarna som kan minska den förväntade tiden att skapa modeller, bland annat antalet upplevelser i ditt Automated Personalization-test, trafiken till din webbplats och det framgångsmått du valt.

**Lösning:** Granska aktivitetsinställningarna och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller. Du kommer inte att förlora aktivitetsdata om du ändrar resultatmåttet från RPV till konvertering.
* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsfrekvens ökar de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Finns det erbjudanden eller upplevelser du kan utesluta från din aktivitet? Genom att minska antalet upplevelser i en aktivitet går det snabbare att skapa modeller.
* Finns det en sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

## Min AP-aktivitet genererade ingen hiss. {#section_8900BC8968474438B8092F7A94C0C6CF}

Det finns flera faktorer som krävs för att en AP-aktivitet ska kunna generera lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

**Lösning:** Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad för den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

## Min URL för AP-aktivitet visar erbjudandeinnehåll på felaktiga sidor. {#section_82A224406DBF4107B05204BEFBBE458C}

I AP läggs URL- och malltestreglerna till i [!DNL Target]-begärandepostbegränsningen (till exempel target-global-mbox), där de bara utvärderas en gång. När en användare kvalificerar sig för en aktivitet utvärderas inte målinriktningsreglerna på målförfrågansnivå på nytt. Målgruppen läggs dock till i reglerna för målinriktning mot plats.

**Lösning:** Lägg till nödvändiga mallregler som kampanjens målgrupp. Målgruppsutvärdering sker vid varje begäran/anrop.

Detta kommer att korrigeras i en kommande version.

## Alla mätvärden som är beroende av konverteringsmått konverteras aldrig. {#section_076D1F44298C4E4A849AC52F5A33214D}

Detta förväntas.

I en AP-aktivitet, när ett konverteringsmått (vare sig optimeringsmål eller postmål) konverteras, frigörs användaren från upplevelsen och aktiviteten startas om.

Det finns till exempel en aktivitet med ett konverteringsmått (C1) och ett ytterligare mått (A1). A1 är beroende av C1. När en besökare går in i aktiviteten för första gången och villkoren för konvertering av A1 och C1 inte konverteras, konverteras inte mätvärdena A1 på grund av beroendet av framgångsmått. Om besökaren konverterar C1 och sedan konverterar A1 konverteras A1 fortfarande inte eftersom besökaren släpps när C1 konverteras.

## Mina upplevelse-URL:er fungerar inte som förväntat. {#section_7B08DA1F30AA483E9406336DAF361BA4}

* Om du inte kan se förhandsvisningen på den nya fliken (på grund av webbläsarens cacheminne) kan du försöka uppdatera två eller tre gånger eller kopiera länken och öppna den i en ny webbläsare eller i en ny session.
* Generera om Experience URL-länkar om du har ändrat något innehåll och delar de nya länkarna med dina teamkamrater.

