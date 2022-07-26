---
keywords: automatiskt mål;mål;trafikallokering;vanliga frågor;frågor;felsökning;felsökning;trafik
description: Utforska felsökningsämnen och vanliga frågor och svar om Automatisk Target-aktiviteter i Adobe Target.
title: Hur felsöker jag Automatiskt inriktade aktiviteter?
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1869'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Automatisk målsökning och vanliga frågor

Felsökning och vanliga frågor (FAQ) om [!UICONTROL Auto-Target] in [!DNL Adobe Target].

## Automatisk målanpassning av vanliga frågor {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Se följande frågor och svar när du arbetar med [!UICONTROL Auto-Target] verksamhet:

### Vad är de bästa sätten att skapa en [!UICONTROL Auto-Target] aktivitet?

* Bestäm om affärsvärdet för ett framgångsmått för Intäkter per besök är värt de extra trafikkraven. RPV behöver vanligtvis minst 1 000 konverteringar per upplevelse för att en aktivitet ska fungera jämfört med konvertering.
* Bestäm allokeringen mellan kontroll och personaliserade upplevelser innan du påbörjar aktiviteten utifrån era mål.
* Kontrollera om du har tillräckligt med trafik till sidan där [!UICONTROL Auto-Target] aktiviteten kommer att köras så att personaliseringsmodeller kan byggas upp inom rimlig tid.
   * Om du testar personaliseringsalgoritmen bör du inte ändra upplevelser eller lägga till/ta bort profilattribut när aktiviteten är aktiv.

* Överväg att slutföra en A/B-aktivitet mellan erbjudandena och platserna som du tänker använda i [!UICONTROL Auto-Target] aktivitet för att säkerställa plats(er) och erbjudanden påverkar optimeringsmålet. Om en A/B-aktivitet inte uppvisar någon signifikant skillnad, [!UICONTROL Auto-Target] sannolikt inte heller kommer att generera någon lyft.

   * Om ett A/B-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är det troligt att de erbjudanden du överväger inte skiljer sig tillräckligt mycket från varandra, att de platser du valde inte påverkar framgångsmåttet eller att optimeringsmålet är för långt i konverteringsprocessen för att påverkas av dina valda erbjudanden.

* Försök att inte göra några större ändringar av upplevelserna under aktivitetens gång.

### Rekommenderar du att vi använder [!UICONTROL Auto Target] med 90 (Kontroll)/10 (Riktat) delat tills modellerna har byggts?

Din optimala trafikallokeringsdelning beror på vad du vill uppnå.

Om målet är att personalisera så mycket trafik som möjligt kan ni hålla er till 90 % målinriktning och 10 % kontroll över aktivitetens livstid. Om målet är att köra ett experiment där man jämför hur väl personaliserade algoritmer fungerar jämfört med kontrollen är en delning på 50/50 bäst under aktivitetens livstid.

Det bästa sättet är att behålla uppdelningen av trafikallokeringen under aktivitetens livstid så att besökarna inte växlar mellan målinriktade upplevelser och kontrollupplevelser.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

### Om en besökare INTE ser [!UICONTROL Auto-Target] räknar konverteringen i min aktivitet?

Nej, bara besökare som är berättigade att visa [!UICONTROL Auto-Target] aktivitet räknas i rapporteringen.

### Min [!UICONTROL Auto-Target] aktiviteten verkar inte generera något lyft. Vad är det som pågår?

Det krävs fyra faktorer för [!UICONTROL Auto-Target] verksamhet för att skapa lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar.

Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

### När borde jag stoppa min [!UICONTROL Auto-Target] aktivitet?

[!UICONTROL Auto-Target] kan användas som&quot;alltid on&quot;-personalisering som hela tiden optimeras. I synnerhet när det gäller innehåll som alltid är grönt behöver du inte stoppa [!UICONTROL Auto-Target] aktivitet.

Om du vill göra väsentliga ändringar av innehållet i [!UICONTROL Auto-Target] är det bästa sättet att starta en ny aktivitet så att andra användare som granskar rapporter inte förväxlar eller relaterar tidigare resultat med annat innehåll.

### Hur länge ska jag vänta på att modeller ska byggas? {#how-long}

Den tid det tar för modeller att bygga in [!UICONTROL Auto-Target] aktiviteten är vanligtvis beroende av trafiken till de valda aktivitetsplatserna och konverteringsgraden som är kopplad till din aktivitets framgångsmått.

[!UICONTROL Auto-Target] kommer inte att försöka skapa en personaliserad modell för en viss upplevelse förrän det finns minst 50 konverteringar för den upplevelsen. Om den modell som byggs dessutom har otillräcklig kvalitet (enligt offlineutvärdering av&quot;testdata&quot;, använder man [ett mått som kallas AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)) kommer modellen inte att användas för att betjäna trafiken på ett personaliserat sätt.

Några andra saker att tänka på [!UICONTROL Auto-Target]Modelluppbyggnad:

* När en aktivitet är aktiv, [!UICONTROL Auto-Target] tar hänsyn till upp till de 45 senaste dagarnas slumpmässigt använda data när man försöker skapa modeller (t.ex. trafikstyrning, plus några extra slumpmässigt använda data som lagras av vår algoritm).
* När [!UICONTROL Revenue per Visit] är dina framgångsmått, kräver dessa aktiviteter vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksinkomster jämfört med konverteringsgraden.
* Eftersom modellerna byggs per upplevelse måste en upplevelse (minst 50 konverteringar) samlas in för den nya upplevelsen innan personaliserade modeller kan byggas om.

### En modell är inbyggd i min aktivitet. Är besöken till den upplevelsen personaliserade?

Nej, det måste finnas minst två modeller i din aktivitet för att personaliseringen ska kunna börja.

### När kan jag börja titta på resultaten från [!UICONTROL Auto-Target] aktivitet?

Du kan börja titta på resultaten av [!UICONTROL Auto-Target] testa efter att du har minst två upplevelser med modeller byggda (grön bock) för upplevelsen med modeller skapade.

### Kan jag ange en specifik upplevelse som ska användas som kontroll?

Du kan välja en upplevelse som ska användas som kontroll när du skapar en [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) aktivitet.

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använd en specifik upplevelse som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

### Kan jag ändra målmåttet genom en Auto-Target-aktivitet? {#change-metric}

Vi rekommenderar inte att du ändrar målmåttet halvvägs genom en aktivitet. Även om det är möjligt att ändra målmåttet under en aktivitet med [!DNL Target] Gränssnittet, du bör alltid starta en ny aktivitet. Vi garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Denna rekommendation gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag använda alternativet Återställ rapportdata när jag kör en Automatisk målaktivitet?

Använda [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Auto-Target] aktiviteter föreslås inte. Även om det tar bort synliga rapportdata, tas inte alla utbildningsposter bort från [!UICONTROL Auto-Target] modell. I stället för att använda [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Auto-Target] skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. (Obs! Denna vägledning gäller även för [!UICONTROL Auto-Allocate] och [!UICONTROL Automated Personalization] verksamhet.)

### Vad händer om jag tar bort en upplevelse från en Automatisk målaktivitet?

[!DNL Target] bygger en modell per upplevelse, vilket innebär att en upplevelse tas bort [!DNL Target] bygger bara en enda modell och påverkar inte modellerna för de andra upplevelserna.

Anta till exempel att du har en [!UICONTROL Auto-Target] med åtta upplevelser och du tycker inte om en upplevelse. Ni kan ta bort den upplevelsen och den kommer inte att påverka modellerna för de sju återstående upplevelserna.

## Felsökning [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar du kan ställas inför när du använder [!UICONTROL Auto-Target]och några förslag på lösningar.

### Min [!UICONTROL Auto-Target] aktiviteten tar för lång tid att skapa modeller.

Det finns flera ändringar av aktivitetsinställningarna som kan minska den förväntade tiden att skapa modeller, inklusive antalet upplevelser i [!UICONTROL Auto-Target] -aktivitet, trafiken till er webbplats och de resultat ni valt.

**Lösning:** Granska din aktivitetskonfiguration och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller. Du kommer inte att förlora aktivitetsdata om du ändrar resultatmåttet från RPV till konvertering.
* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsgrad kommer att öka de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Finns det några upplevelser du kan släppa från din aktivitet? Om du minskar antalet upplevelser i en aktivitet minskar tiden för att skapa modeller.
* Finns det någon sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

### Min [!UICONTROL Auto-Target] aktiviteten inte genererar något lyft.

Det krävs fyra faktorer för att en AP-aktivitet ska kunna generera lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

**Lösning:** Kontrollera först att din aktivitet personaliserar trafik. Om modellerna inte har byggts för alla upplevelser, [!UICONTROL Auto-Target] aktiviteten ger fortfarande en slumpvis stor del av besöken för att försöka skapa alla modeller så snabbt som möjligt. Om modeller inte byggs [!UICONTROL Auto-Target] personaliserar inte trafik.

Se sedan till att erbjudandena och aktivitetsplatserna verkligen gör skillnad för den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

### Alla mätvärden som är beroende av konverteringsmått konverteras aldrig.

Detta förväntas.

I en [!UICONTROL Auto-Target] när ett konverteringsmått (vare sig optimeringsmål eller postmål) konverteras, släpps användaren från upplevelsen och aktiviteten startas om.

Det finns till exempel en aktivitet med ett konverteringsmått (C1) och ett ytterligare mått (A1). A1 är beroende av C1. När en besökare går in i aktiviteten för första gången och villkoren för konvertering av A1 och C1 inte konverteras, konverteras inte mätvärdena A1 på grund av beroendet av framgångsmått. Om besökaren konverterar C1 och sedan konverterar A1 konverteras A1 fortfarande inte eftersom besökaren släpps när C1 konverteras.
