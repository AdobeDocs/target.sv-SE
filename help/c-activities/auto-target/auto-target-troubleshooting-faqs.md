---
keywords: auto-target;targeting;traffic allocation;frequently asked questions;faq;troubleshooting;trouble shooting
description: Felsökning och vanliga frågor om Automatiskt mål i Adobe Target.
title: Automatisk målsökning och vanliga frågor
feature: auto-target
topic: Standard
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '1722'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Auto-Target-felsökning och vanliga frågor och svar

Felsökning och vanliga frågor om [!UICONTROL Auto-Target] i [!DNL Adobe Target].

## Automatisk målanpassning av vanliga frågor {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Se följande frågor och svar när du arbetar med [!UICONTROL Auto-Target] aktiviteter:

### Vilka är de bästa sätten att konfigurera en [!UICONTROL Auto-Target] aktivitet?

* Bestäm om affärsvärdet för ett framgångsmått för Intäkter per besök är värt de extra trafikkraven. RPV behöver vanligtvis minst 1 000 konverteringar per upplevelse för att en aktivitet ska fungera jämfört med konvertering.
* Bestäm allokeringen mellan kontroll och personaliserade upplevelser innan du påbörjar aktiviteten utifrån era mål.
* Kontrollera om du har tillräckligt med trafik till den sida där din [!UICONTROL Auto-Target] aktivitet ska köras för att personaliseringsmodeller ska kunna byggas inom rimlig tid.
   * Om du testar personaliseringsalgoritmen bör du inte ändra upplevelser eller lägga till/ta bort profilattribut när aktiviteten är aktiv.

* Överväg att slutföra en A/B-aktivitet mellan de erbjudanden och platser som du planerar att använda i din [!UICONTROL Auto-Target] aktivitet för att se till att platserna och erbjudandena påverkar optimeringsmålet. Om en A/B-aktivitet inte uppvisar någon signifikant skillnad kommer den troligtvis inte heller att kunna generera någon lyft [!UICONTROL Auto-Target] .

   * Om ett A/B-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är det troligt att de erbjudanden du överväger inte skiljer sig tillräckligt mycket från varandra, att de platser du valde inte påverkar framgångsmåttet eller att optimeringsmålet är för långt i konverteringsprocessen för att påverkas av dina valda erbjudanden.

* Försök att inte göra några större ändringar av upplevelserna under aktivitetens gång.

### Är kryssmarkeringarna som anger att en modell har skapats för den upplevelseuppdateringen om rapportens datumintervall ändras?

Nej, bockmarkeringar för modellgenerering visar endast de modeller som är byggda hittills. Det finns inget sätt att gå tillbaka och se när en modell är klar.

### Om en besökare INTE ser aktiviteten och konverterar, räknas konverteringen i min aktivitet? [!UICONTROL Auto-Target]

Nej, endast besökare som är kvalificerade för och visar [!UICONTROL Auto-Target] aktiviteten räknas i rapporteringen.

### Min [!UICONTROL Auto-Target] aktivitet verkar inte generera något lyft. Vad är det som pågår?

Det krävs fyra faktorer för att en aktivitet ska kunna generera en lyft: [!UICONTROL Auto-Target]

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar.

Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

### När ska jag stoppa min [!UICONTROL Auto-Target] aktivitet?

[!UICONTROL Auto-Target] kan användas som&quot;alltid on&quot;-personalisering som hela tiden optimeras. Särskilt för omogna innehåll finns inget behov av att stoppa din [!UICONTROL Auto-Target] aktivitet.

Om du vill göra väsentliga ändringar i innehållet i din [!UICONTROL Auto-Target] aktivitet är det bästa sättet att starta en ny aktivitet så att andra användare inte förväxlar eller relaterar tidigare resultat med annat innehåll.

### Hur länge ska jag vänta på att modeller ska byggas? {#how-long}

Hur lång tid det tar för modeller att bygga in din [!UICONTROL Auto-Target] aktivitet beror vanligtvis på trafiken till de valda aktivitetsplatserna och den konverteringsgrad som är kopplad till din aktivitets framgångsmått.

[!UICONTROL Auto-Target] kommer inte att försöka skapa en personaliserad modell för en viss upplevelse förrän det finns minst 50 konverteringar för den upplevelsen. Om den modell som byggs inte har tillräcklig kvalitet (enligt offlineutvärdering av spärrade&quot;testdata&quot;, med [ett mått som kallas AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), kommer modellen inte att användas för att betjäna trafiken på ett personaliserat sätt.

Några andra punkter att tänka på när det gäller [!UICONTROL Auto-Target]modellbyggandet:

* När en aktivitet är aktiv tar hänsyn [!UICONTROL Auto-Target] till de 45 sista dagarna i slumpmässigt betjänade data när man försöker skapa modeller (t.ex. kontrolltrafik, plus några extra data som tillhandahålls av vår algoritm).
* När [!UICONTROL Revenue per Visit] är dina framgångsmått kräver dessa aktiviteter vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksinkomsterna jämfört med konverteringsgraden.
* Eftersom modellerna byggs per upplevelse måste tillräcklig trafik (dvs. minst 50 konverteringar) samlas in för den nya upplevelsen innan personaliserade modeller kan byggas om.

### En modell är inbyggd i min aktivitet. Är besöken till den upplevelsen personaliserade?

Nej, det måste finnas minst två modeller i din aktivitet för att personaliseringen ska kunna börja.

### När kan jag börja titta på resultaten av min [!UICONTROL Auto-Target] aktivitet?

Du kan börja titta på resultatet av ditt [!UICONTROL Auto-Target] test när du har minst två upplevelser med modeller byggda (grön bock) för upplevelsen som har modeller skapade.

### Kan jag ange en specifik upplevelse som ska användas som kontroll?

Du kan välja en upplevelse som ska användas som kontroll när du skapar en aktivitet för [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) eller [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använda en viss upplevelse som kontroll](/help/c-activities/t-automated-personalization/experience-as-control.md).

### Kan jag ändra målmåttet genom en Auto-Target-aktivitet? {#change-metric}

Vi rekommenderar inte att du ändrar målmåttet halvvägs genom en aktivitet. Även om det går att ändra målmåttet under en aktivitet med [!DNL Target] användargränssnittet bör du alltid starta en ny aktivitet. Vi garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Denna rekommendation gäller för [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag använda alternativet Återställ rapportdata när jag kör en Automatisk målaktivitet?

Du bör inte använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Auto-Target] aktiviteter. Även om det tar bort synliga rapportdata tas inte alla utbildningsposter bort från [!UICONTROL Auto-Target] modellen. I stället för att använda [!UICONTROL Reset Report Data] alternativet för [!UICONTROL Auto-Target] aktiviteter skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. (Obs! Denna vägledning gäller även [!UICONTROL Auto-Allocate] verksamhet och [!UICONTROL Automated Personalization] verksamhet.)

## Felsökning [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar du kan ställas inför när du använder [!UICONTROL Auto-Target]och några förslag på lösningar.

### Min [!UICONTROL Auto-Target] aktivitet tar för lång tid att skapa modeller.

Det finns flera ändringar av aktivitetsinställningarna som kan minska den förväntade tiden att skapa modeller, bland annat antalet upplevelser i din [!UICONTROL Auto-Target] aktivitet, trafiken till din webbplats och det valda framgångsmåttet.

**Lösning:** Granska din aktivitetskonfiguration och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller. Du kommer inte att förlora aktivitetsdata om du ändrar resultatmåttet från RPV till konvertering.
* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsgrad kommer att öka de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Finns det några upplevelser du kan släppa från din aktivitet? Om du minskar antalet upplevelser i en aktivitet minskar tiden för att skapa modeller.
* Finns det någon sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

### Min [!UICONTROL Auto-Target] aktivitet genererar ingen hiss.

Det krävs fyra faktorer för att en AP-aktivitet ska kunna generera lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

**Lösning:** Kontrollera först att din aktivitet personaliserar trafik. Om du inte har skapat modeller för alla upplevelser är din [!UICONTROL Auto-Target] aktivitet fortfarande slumpvis tillgänglig för en stor del av besöken för att försöka skapa alla modeller så snabbt som möjligt. Om modeller inte byggs personaliserar [!UICONTROL Auto-Target] inte trafiken.

Se sedan till att erbjudandena och aktivitetsplatserna verkligen gör skillnad för den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

### Alla mätvärden som är beroende av konverteringsmått konverteras aldrig.

Detta förväntas.

När ett konverteringsmått (vare sig optimeringsmål eller postmål) har konverterats i en [!UICONTROL Auto-Target] aktivitet frisläpps användaren från upplevelsen och aktiviteten startas om.

Det finns till exempel en aktivitet med ett konverteringsmått (C1) och ett ytterligare mått (A1). A1 är beroende av C1. När en besökare går in i aktiviteten för första gången och villkoren för konvertering av A1 och C1 inte konverteras, konverteras inte mätvärdena A1 på grund av beroendet av framgångsmått. Om besökaren konverterar C1 och sedan konverterar A1 konverteras A1 fortfarande inte eftersom besökaren släpps när C1 konverteras.
