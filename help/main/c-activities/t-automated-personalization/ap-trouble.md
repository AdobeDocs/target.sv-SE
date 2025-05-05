---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Utforska potentiella utmaningar som du kan ställas inför när du använder [!UICONTROL Automated Personalization] (AP)-aktiviteter i Adobe Target, tillsammans med förslag på lösningar.
title: Hur felsöker jag [!UICONTROL Automated Personalization] aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
source-git-commit: 2cb2c2b68f6487d1af41ecc7e73750afa1ad85f9
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---

# Felsök [!UICONTROL Automated Personalization]

Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar som du kan ställas inför när du använder [!UICONTROL Automated Personalization] (AP), och några förslag på lösningar.

## Min [!UICONTROL Automated Personalization]-aktivitet tar för lång tid att skapa modeller. {#section_20028B204DBB4D77A324BA193434AEE2}

+++Se information

Det finns flera ändringar av aktivitetsinställningarna som kan minska den förväntade tiden att skapa modeller, inklusive antalet upplevelser i din [!UICONTROL Automated Personalization]-aktivitet, trafiken till din webbplats och det valda framgångsmåttet.

**Lösning:** Granska din aktivitetsinställning och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger med.

* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller. Du förlorar inte aktivitetsdata om du ändrar resultatmåttet från RPV till konvertering.
* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsfrekvens ökar de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Finns det erbjudanden eller upplevelser du kan utesluta från din aktivitet? Genom att minska antalet upplevelser i en aktivitet går det snabbare att skapa modeller.
* Finns det en sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

+++

## Min [!UICONTROL Automated Personalization]-aktivitet genererade ingen lyft. {#section_8900BC8968474438B8092F7A94C0C6CF}

+++Se information

Det finns flera faktorer som krävs för att en [!UICONTROL Automated Personalization]-aktivitet ska kunna generera lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

**Lösning:** Det bästa sättet att göra detta är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad för de totala svarsfrekvenserna med ett enkelt, icke-personaliserat A/B-test. Var noga med att beräkna exempelstorlekarna i förväg. Genom att beräkna provstorlekar i förväg kan du säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft. Du kan sedan köra A/B-testet med en fast varaktighet utan att stoppa det eller göra några ändringar. Om ett A/B-testresultat visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet blir framgångsrik. Personalization kan fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på erbjudanden eller platser som inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

+++

## Aktivitets-URL:en för [!UICONTROL Automated Personalization] visar erbjudandeinnehåll på felaktiga sidor. {#section_82A224406DBF4107B05204BEFBBE458C}

+++Se information

I [!UICONTROL Automated Personalization] läggs URL- och malltestreglerna till i [!DNL Target]-begärandebegränsningen (till exempel target-global-mbox), där de bara utvärderas en gång. När en användare kvalificerar sig för en aktivitet utvärderas inte målinriktningsreglerna på målförfrågansnivå. Målgruppen läggs dock till i reglerna för målinriktning mot plats.

**Lösning:** Lägg till nödvändiga mallregler som aktivitetens målgrupp. Målgruppsutvärdering sker vid varje begäran/anrop.

+++

## Alla mätvärden som är beroende av ett konverteringsmått konverteras aldrig. {#section_076D1F44298C4E4A849AC52F5A33214D}

+++Se information

Detta förväntas.

I en [!UICONTROL Automated Personalization]-aktivitet, när ett konverteringsmått (oavsett om optimeringsmål eller postmål) konverteras, släpps besökaren från upplevelsen och aktiviteten startas om.

Det finns till exempel en aktivitet med ett konverteringsmått (C1) och ett ytterligare mått (A1). A1 är beroende av C1. När en besökare går in i aktiviteten för första gången och villkoren för konvertering av A1 och C1 inte konverteras, konverteras inte mätvärdena A1 på grund av beroendet av framgångsmått. Om besökaren konverterar C1 och sedan konverterar A1, konverteras A1 fortfarande inte eftersom besökaren frigörs när C1 konverteras.

+++

## Mina upplevelse-URL:er fungerar inte som förväntat. {#section_7B08DA1F30AA483E9406336DAF361BA4}

+++Se information

* Om du inte kan se förhandsvisningen på den nya fliken (på grund av webbläsarens cacheminne) kan du försöka uppdatera två eller tre gånger. Du kan också kopiera länken och öppna den i en ny webbläsare eller i en ny session.
* Generera om Experience URL-länkar om du har ändrat något innehåll och delar de nya länkarna med dina teamkamrater.

+++
