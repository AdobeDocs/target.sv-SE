---
keywords: automatiskt mål;mål;trafikallokering;vanliga frågor;frågor;felsökning;felsökning;trafik
description: Utforska felsökningsämnen och Frågor och svar om [!UICONTROL Auto-Target] verksamhet.
title: Hur felsöker jag [!UICONTROL Auto-Target] Verksamheter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1859'
ht-degree: 0%

---

# [!UICONTROL Auto-Target] Vanliga frågor och felsökning

Felsökning och vanliga frågor (FAQ) om [!UICONTROL Auto-Target] verksamhet i [!DNL Adobe Target].

## [!UICONTROL Auto-Target] Vanliga frågor {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Se följande frågor och svar när du arbetar med [!UICONTROL Auto-Target] verksamhet:

### Vad är de bästa sätten att skapa en [!UICONTROL Auto-Target] aktivitet?

+++Svar
* Bestäm om affärsvärdet för en [!UICONTROL Revenue per Visit] (RPV) framgångsmått är värt de extra trafikkraven. RPV behöver vanligtvis minst 1 000 konverteringar per upplevelse för att en aktivitet ska fungera jämfört med konvertering.
* Bestäm allokeringen mellan kontroll och personaliserade upplevelser innan du påbörjar aktiviteten utifrån era mål.
* Kontrollera om du har tillräckligt med trafik till sidan där [!UICONTROL Auto-Target] för att personaliseringsmodeller ska kunna byggas på rimlig tid.
* Om du testar personaliseringsalgoritmen bör du inte ändra upplevelser eller lägga till eller ta bort profilattribut när aktiviteten är aktiv.
* Överväg att slutföra en A/B-aktivitet mellan erbjudandena och platserna som du tänker använda i [!UICONTROL Auto-Target] aktivitet för att säkerställa att platserna och erbjudandena påverkar optimeringsmålet. Om en A/B-aktivitet inte uppvisar någon signifikant skillnad, [!UICONTROL Auto-Target] sannolikt inte heller genererar lyft.

  Om ett A/B-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är det troligt att de erbjudanden du överväger inte skiljer sig tillräckligt mycket från varandra, att de platser du valde inte påverkar framgångsmåttet eller att optimeringsmålet är för långt i konverteringsprocessen för att påverkas av dina valda erbjudanden.

* Försök att inte göra några större ändringar av upplevelserna under aktiviteten.

+++

### Gör [!UICONTROL Adobe] som du rekommenderar med [!UICONTROL Auto Target] med 90 (Kontroll)/10 (Riktat) delat tills modellerna har byggts?

+++Svara på Din optimala trafikallokering beror på vad du vill uppnå.

Om målet är att personalisera så mycket trafik som möjligt kan ni behålla 90 % riktad tilldelning och 10 % kontroll över aktivitetens livstid. Om målet är att köra ett experiment där personaliserade algoritmer jämförs med kontrollen, är en delning på 50/50 bäst under aktivitetens livstid.

Det bästa sättet är att behålla uppdelningen av trafikallokeringen under aktivitetens livstid så att besökarna inte växlar mellan målinriktade upplevelser och kontrollupplevelser.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Om en besökare gör det **not** se [!UICONTROL Auto-Target] räknar konverteringen i min aktivitet?

+++Svarsnr Endast besökare som är berättigade att visa [!UICONTROL Auto-Target] aktivitet räknas i rapporteringen.

+++

### Varför är inte min [!UICONTROL Auto-Target] aktiviteten verkar generera något lyft.

+++Svar Det krävs fyra faktorer för en [!UICONTROL Auto-Target] Aktivitet för att skapa lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar.

Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på erbjudanden och platser som inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

+++

### När borde jag stoppa min [!UICONTROL Auto-Target] aktivitet?

+++Svar
[!UICONTROL Auto-Target] kan användas som&quot;alltid on&quot;-personalisering som ständigt optimeras. I synnerhet när det gäller innehåll som alltid är grönt behöver du inte stoppa [!UICONTROL Auto-Target] aktivitet.

Om du vill göra väsentliga ändringar av innehållet i [!UICONTROL Auto-Target] är det bästa sättet att starta en ny aktivitet så att andra användare som granskar rapporter inte förväxlar eller relaterar tidigare resultat med annat innehåll.

+++

### Hur länge ska jag vänta på att modeller ska byggas? {#how-long}

+++Svar Den tid det tar för modeller att bygga in [!UICONTROL Auto-Target] aktiviteten beror vanligtvis på trafiken till de valda aktivitetsplatserna och konverteringsgraden som är kopplad till din aktivitets framgångsmått.

[!UICONTROL Auto-Target] försöker inte skapa en personaliserad modell för en viss upplevelse förrän det finns minst 50 konverteringar för den upplevelsen. Om den modell som byggs dessutom har otillräcklig kvalitet (enligt offlineutvärdering av spärrdata), använder man [ett mått som kallas AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)) används modellen inte för att betjäna trafiken på ett personaliserat sätt.

Några andra saker att tänka på [!UICONTROL Auto-Target]Modelluppbyggnad:

* När en aktivitet är aktiv, [!UICONTROL Auto-Target] tar hänsyn till de senaste 45 dagarna med slumpmässigt använda data när man försöker skapa modeller. Styr till exempel trafiken, plus vissa extra data som spelas upp slumpmässigt av algoritmen.
* När [!UICONTROL Revenue per Visit] är dina framgångsmått, kräver dessa aktiviteter vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksinkomster jämfört med konverteringsgraden.
* Eftersom modellerna byggs per upplevelse innebär en ersättning av en upplevelse med en annan att tillräcklig trafik (minst 50 konverteringar) måste samlas in för den nya upplevelsen innan personaliserade modeller kan återskapas.

+++

### En modell är inbyggd i min aktivitet. Är besöken till den upplevelsen personaliserade?

+++Svarsnr. Det måste finnas minst två modeller byggda i din aktivitet för att personaliseringen ska kunna börja.

+++

### När kan jag börja titta på resultaten från [!UICONTROL Auto-Target] aktivitet?

+++Svar Du kan börja titta på resultaten av [!UICONTROL Auto-Target] testa efter att du har minst två upplevelser med modeller byggda (grön bock) för upplevelsen som har modeller skapade.

+++

### Kan jag ange en specifik upplevelse som ska användas som kontroll?

+++Svar Du kan välja en upplevelse som ska användas som kontroll när du skapar en [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) aktivitet.

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokering som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använd en specifik upplevelse som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### Kan jag ändra målmåttet genom en [!UICONTROL Auto-Target] aktivitet? {#change-metric}

+++Besvara Adobe rekommenderar inte att du ändrar målmåttet genom en aktivitet. Även om det är möjligt att ändra målmåttet under en aktivitet med [!DNL Target] Gränssnittet, du bör alltid starta en ny aktivitet. Adobe garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Denna rekommendation gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

+++

### Kan jag använda [!UICONTROL Reset Report Data] alternativ när en [!UICONTROL Auto-Target] aktivitet?

+++Svara med [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Auto-Target] aktiviteter föreslås inte. Även om det tar bort synliga rapportdata, tas inte alla utbildningsposter bort från [!UICONTROL Auto-Target] modell. I stället för att använda [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Auto-Target] skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten.

Denna vägledning gäller även för [!UICONTROL Auto-Allocate] och [!UICONTROL Automated Personalization] verksamhet.

+++

### Vad händer om jag tar bort en upplevelse från en [!UICONTROL Auto-Target] aktivitet?

+++Svar
[!DNL Target] bygger en modell per upplevelse, vilket innebär att en upplevelse tas bort [!DNL Target] skapar en modell med mindre storlek och påverkar inte modeller för de andra upplevelserna.

Anta att du har en [!UICONTROL Auto-Target] med åtta upplevelser och du tycker inte om en upplevelse. Ni kan ta bort den upplevelsen och den påverkar inte modellerna för de sju återstående upplevelserna.

+++

## Felsökning [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar som du kan stöta på när du använder [!UICONTROL Auto-Target] och några förslag på lösningar.

### Min [!UICONTROL Auto-Target] aktiviteten tar för lång tid att skapa modeller.

+++Felsökningsförslag Det finns flera ändringar av aktivitetsinställningarna som kan minska den förväntade tiden att skapa modeller, inklusive antalet upplevelser i din [!UICONTROL Auto-Target] -aktivitet, trafiken till er webbplats och de resultat ni valt.

**Lösning:** Granska din aktivitetskonfiguration och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Om mätvärdet för framgång är inställt på [!UICONTROL RPV]kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller. Du kommer inte att förlora aktivitetsdata om du ändrar resultatmåttet från RPV till konvertering.
* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsfrekvens ökar de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Finns det några upplevelser du kan släppa från din aktivitet? Om du minskar antalet upplevelser i en aktivitet tar det kortare tid att skapa modeller.
* Finns det någon sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

+++

### Min [!UICONTROL Auto-Target] aktiviteten inte genererar något lyft.

+++Felsökningsförslag Det finns fyra faktorer som krävs för en [!UICONTROL Auto-Target] Aktivitet för att skapa lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

**Lösning:** Kontrollera först att din aktivitet personaliserar trafik. Om modellerna inte har byggts för alla upplevelser, [!UICONTROL Auto-Target] aktiviteten ger fortfarande en slumpvis stor del av besöken för att försöka skapa alla modeller så snabbt som möjligt. Om modeller inte byggs [!UICONTROL Auto-Target] personaliserar inte trafik.

Se sedan till att erbjudandena och aktivitetsplatserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet fungerar. Personalisering kan fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på erbjudanden och platser som inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

+++

### Alla mätvärden som är beroende av ett konverteringsmått konverteras aldrig.

+++Felsökningsförslag Detta förväntas.

I en [!UICONTROL Auto-Target] när ett konverteringsmått (vare sig optimeringsmål eller postmål) konverteras, släpps användaren från upplevelsen och aktiviteten startas om.

Det finns till exempel en aktivitet med ett konverteringsmått (C1) och ett ytterligare mått (A1). A1 är beroende av C1. När en besökare går in i aktiviteten för första gången och villkoren för konvertering av A1 och C1 inte konverteras, konverteras inte mätvärdena A1 på grund av beroendet av framgångsmått. Om besökaren konverterar C1 och sedan konverterar A1, konverteras A1 fortfarande inte eftersom besökaren frigörs när C1 konverteras.

+++
