---
keywords: automatiskt mål;mål;trafikallokering;vanliga frågor;frågor;felsökning;felsökning;trafik
description: Utforska felsökningsämnen och Vanliga frågor om [!UICONTROL Auto-Target]-aktiviteter.
title: Hur felsöker jag [!UICONTROL Auto-Target] aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1850'
ht-degree: 0%

---

# [!UICONTROL Auto-Target] vanliga frågor och felsökning

Felsökning och vanliga frågor (FAQ) om [!UICONTROL Auto-Target] aktiviteter i [!DNL Adobe Target].

## [!UICONTROL Auto-Target] Vanliga frågor {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Ta del av följande frågor och svar när du arbetar med [!UICONTROL Auto-Target]-aktiviteter:

### Vilka är de bästa sätten att konfigurera en [!UICONTROL Auto-Target]-aktivitet?

+++Svar
* Bestäm om affärsvärdet för ett [!UICONTROL Revenue per Visit] (RPV)-framgångsmått är värt de extra trafikkraven. RPV behöver vanligtvis minst 1 000 konverteringar per upplevelse för att en aktivitet ska fungera jämfört med konvertering.
* Bestäm allokeringen mellan kontroll och personaliserade upplevelser innan du påbörjar aktiviteten utifrån era mål.
* Kontrollera om du har tillräckligt med trafik till sidan där din [!UICONTROL Auto-Target]-aktivitet körs för att personaliseringsmodeller ska kunna byggas inom en rimlig tid.
* Om du testar personaliseringsalgoritmen bör du inte ändra upplevelser eller lägga till eller ta bort profilattribut när aktiviteten är aktiv.
* Överväg att slutföra en A/B-aktivitet mellan erbjudandena och platserna som du planerar att använda i din [!UICONTROL Auto-Target]-aktivitet för att säkerställa att platserna och erbjudandena påverkar optimeringsmålet. Om en A/B-aktivitet inte kan visa en signifikant skillnad, kommer [!UICONTROL Auto-Target] troligtvis inte att generera någon lyft.

  Om ett A/B-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är det troligt att de erbjudanden du överväger inte skiljer sig tillräckligt mycket från varandra, att de platser du valde inte påverkar framgångsmåttet eller att optimeringsmålet är för långt i konverteringsprocessen för att påverkas av dina valda erbjudanden.

* Försök att inte göra några större ändringar av upplevelserna under aktiviteten.

+++

### Rekommenderar [!UICONTROL Adobe] att du använder [!UICONTROL Auto Target] med en delning av 90(Kontroll)/10(Mål) tills modellerna har byggts?

+++Svar 
Din optimala trafikallokeringsdelning beror på vad du vill uppnå.

Om målet är att personalisera så mycket trafik som möjligt kan ni behålla 90 % riktad tilldelning och 10 % kontroll över aktivitetens livstid. Om målet är att köra ett experiment där personaliserade algoritmer jämförs med kontrollen, är en delning på 50/50 bäst under aktivitetens livstid.

Det bästa sättet är att behålla uppdelningen av trafikallokeringen under aktivitetens livstid så att besökarna inte växlar mellan målinriktade upplevelser och kontrollupplevelser.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Om en besökare **inte** ser aktiviteten [!UICONTROL Auto-Target] och konverterar, räknas konverteringen i min aktivitet?

+++Svar
Nej, endast besökare som är kvalificerade för och visar aktiviteten [!UICONTROL Auto-Target] räknas i rapporteringen.

+++

### Varför verkar inte min [!UICONTROL Auto-Target]-aktivitet generera något lyft.

+++Svar
Det krävs fyra faktorer för att en [!UICONTROL Auto-Target]-aktivitet ska kunna generera lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar.

Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på erbjudanden och platser som inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

+++

### När ska jag stoppa min [!UICONTROL Auto-Target]-aktivitet?

+++Svar
[!UICONTROL Auto-Target] kan användas som&quot;alltid aktiverad&quot;-personalisering som ständigt optimeras. I synnerhet för omogna innehåll finns det ingen anledning att stoppa din [!UICONTROL Auto-Target]-aktivitet.

Om du vill göra omfattande ändringar av innehållet i din [!UICONTROL Auto-Target]-aktivitet är det bästa sättet att starta en ny aktivitet så att andra användare inte blandar ihop eller relaterar tidigare resultat med annat innehåll.

+++

### Hur länge ska jag vänta på att modeller ska byggas? {#how-long}

+++Svar
Den tid det tar för modeller att bygga in din [!UICONTROL Auto-Target]-aktivitet beror vanligtvis på trafiken till de valda aktivitetsplatserna och konverteringsgraden som är kopplad till din aktivitets framgångsmått.

[!UICONTROL Auto-Target] försöker inte skapa en anpassad modell för en viss upplevelse förrän det finns minst 50 konverteringar för den upplevelsen. Om den skapade modellen dessutom har otillräcklig kvalitet (enligt offlineutvärdering av spärrdata, med [ett mätvärde som kallas AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), används modellen inte för att hantera trafik på ett personligt sätt.

Några andra punkter att tänka på när det gäller modellbygget för [!UICONTROL Auto-Target]:

* När en aktivitet har publicerats tar [!UICONTROL Auto-Target] hänsyn till upp till de 45 senaste dagarna med slumpmässigt betjänade data vid försök att skapa modeller. Styr till exempel trafiken, plus vissa extra data som spelas upp slumpmässigt av algoritmen.
* När [!UICONTROL Revenue per Visit] är ditt framgångsmått behöver dessa aktiviteter vanligtvis mer data för att skapa modeller på grund av den högre datavariationen som vanligtvis finns i besöksinkomster jämfört med konverteringsgraden.
* Eftersom modellerna byggs per upplevelse innebär en ersättning av en upplevelse med en annan att tillräcklig trafik (minst 50 konverteringar) måste samlas in för den nya upplevelsen innan personaliserade modeller kan återskapas.

+++

### En modell är inbyggd i min aktivitet. Är besöken till den upplevelsen personaliserade?

+++Svar
Nej, det måste finnas minst två modeller i din aktivitet för att personaliseringen ska kunna börja.

+++

### När kan jag börja titta på resultaten av min [!UICONTROL Auto-Target]-aktivitet?

+++Svar
Du kan börja titta på resultatet av ditt [!UICONTROL Auto-Target]-test efter att du har minst två upplevelser med färdiga modeller (grön bock) för den upplevelse som har skapat modeller.

+++

### Kan jag ange en specifik upplevelse som ska användas som kontroll?

+++Svar
Du kan välja en upplevelse som ska användas som kontroll när du skapar en [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) - (AP) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)-aktivitet.

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokering som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använd en specifik upplevelse som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### Kan jag ändra målmåttet genom en [!UICONTROL Auto-Target]-aktivitet? {#change-metric}

+++Svar
Adobe rekommenderar inte att du ändrar målmåttet genom en aktivitet. Även om det går att ändra målmåttet under en aktivitet med användargränssnittet för [!DNL Target] bör du alltid starta en ny aktivitet. Adobe garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Den här rekommendationen gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

+++

### Kan jag använda alternativet [!UICONTROL Reset Report Data] när jag kör en [!UICONTROL Auto-Target]-aktivitet?

+++Svar
Du bör inte använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Auto-Target]-aktiviteter. Även om synliga rapportdata tas bort, tas inte alla utbildningsposter bort från modellen [!UICONTROL Auto-Target]. I stället för att använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Auto-Target]-aktiviteter skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten.

Den här vägledningen gäller även för [!UICONTROL Auto-Allocate]- och [!UICONTROL Automated Personalization]-aktiviteter.

+++

### Vad händer om jag tar bort en upplevelse från en [!UICONTROL Auto-Target]-aktivitet?

+++Svar
[!DNL Target] bygger en modell per upplevelse, så om du tar bort en upplevelse innebär det att [!DNL Target] skapar en modell med mindre storlek och inte påverkar modeller för de andra upplevelserna.

Anta till exempel att du har en [!UICONTROL Auto-Target]-aktivitet med åtta upplevelser och att du inte gillar en upplevelse. Ni kan ta bort den upplevelsen och den påverkar inte modellerna för de sju återstående upplevelserna.

+++

## Felsökning av [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar som du kan ställas inför när du använder [!UICONTROL Auto-Target] och några förslag på lösningar.

### Min [!UICONTROL Auto-Target]-aktivitet tar för lång tid att skapa modeller.

+++Felsökningsförslag
Det finns flera ändringar av aktivitetsinställningarna som kan minska den förväntade tiden att skapa modeller, inklusive antalet upplevelser i din [!UICONTROL Auto-Target]-aktivitet, trafiken till din webbplats och det valda framgångsmåttet.

**Lösning:** Granska din aktivitetsinställning och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger med.

* Om du har angett ett framgångsmått på [!UICONTROL RPV], kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller. Du kommer inte att förlora aktivitetsdata om du ändrar resultatmåttet från RPV till konvertering.
* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsfrekvens ökar de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Finns det några upplevelser du kan släppa från din aktivitet? Om du minskar antalet upplevelser i en aktivitet tar det kortare tid att skapa modeller.
* Finns det någon sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

+++

### Min [!UICONTROL Auto-Target]-aktivitet genererar ingen lyft.

+++Felsökningsförslag
Det krävs fyra faktorer för att en [!UICONTROL Auto-Target]-aktivitet ska kunna generera lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

**Lösning:** Kontrollera först att din aktivitet personaliserar trafik. Om modeller inte har byggts för alla upplevelser är din [!UICONTROL Auto-Target]-aktivitet fortfarande slumpvis betjänad av en stor del av besöken för att försöka skapa alla modeller så snabbt som möjligt. Om modeller inte har skapats personaliserar [!UICONTROL Auto-Target] inte trafik.

Se sedan till att erbjudandena och aktivitetsplatserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet fungerar. Personalization kan fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på erbjudanden och platser som inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

+++

### Alla mätvärden som är beroende av ett konverteringsmått konverteras aldrig.

+++Felsökningsförslag
Detta förväntas.

I en [!UICONTROL Auto-Target]-aktivitet frisläpps användaren från upplevelsen när ett konverteringsmått (oavsett om optimeringsmål eller postmål) har konverterats och aktiviteten startas om.

Det finns till exempel en aktivitet med ett konverteringsmått (C1) och ett ytterligare mått (A1). A1 är beroende av C1. När en besökare går in i aktiviteten för första gången och villkoren för konvertering av A1 och C1 inte konverteras, konverteras inte mätvärdena A1 på grund av beroendet av framgångsmått. Om besökaren konverterar C1 och sedan konverterar A1, konverteras A1 fortfarande inte eftersom besökaren frigörs när C1 konverteras.

+++
