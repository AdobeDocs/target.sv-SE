---
keywords: troubleshooting;frequently asked questions;FAQ;FAQs;automated personalization
description: Lista med vanliga frågor och svar om Automated Personalization (AP).
title: Automated Personalization FAQ
feature: ap
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1944'
ht-degree: 0%

---


# ![Vanliga frågor om ](/help/assets/premium.png) automatisk personaliseringPREMIUMA{#automated-personalization-faq}

Lista med vanliga frågor och svar om Automated Personalization (AP).

## Kan jag ange en specifik upplevelse som ska användas som kontroll?

Du kan välja en upplevelse som ska användas som kontroll när du skapar en [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) eller [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT)-aktivitet.

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använd en specifik upplevelse som kontroll](/help/c-activities/t-automated-personalization/experience-as-control.md).

## Hur kan jag jämföra Automated Personalization med en standardupplevelse? {#section_46C1A620A2384C2C8392D6716DD18495}

Det finns inget körklart alternativ för att jämföra AP med en standardupplevelse. Om det finns ett standarderbjudande eller en standardupplevelse som en del av den övergripande aktiviteten kan du som en tillfällig lösning klicka på&quot;Kontroll&quot;-segmentet i rapporterna och leta reda på just det erbjudandet i den rapport på erbjudandenivå som skapas. Den konverteringsgrad som registreras för det här erbjudandet kan användas för att jämföra konverteringsgraden för hela segmentet &quot;Slumpskog&quot;. Detta hjälper till att jämföra hur datorn fungerar jämfört med standarderbjudandet.

## Vilka är de bästa sätten att skapa en Automated Personalization-aktivitet? {#section_E155B26282BE49B58EA2683413D11DE6}

* Om du vill anpassa en sida med låg trafik eller vill göra strukturella ändringar av den upplevelse du personaliserar bör du överväga att använda Automatiskt mål i stället för Automated Personalization. Se [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md).
* Överväg att slutföra en A/B-aktivitet mellan de erbjudanden och platser som du planerar att använda i din Automated Personalization-aktivitet för att säkerställa att de platser och erbjudanden påverkar optimeringsmålet. Om en A/B-aktivitet inte uppvisar någon större skillnad kommer Automated Personalization sannolikt inte heller att generera någon lyft.

   * Om ett A/B...N-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är det troligt att de erbjudanden du överväger inte skiljer sig tillräckligt mycket från varandra, påverkar de valda platserna inte framgångsmätningen eller så är optimeringsmålet för långt i konverteringstratten för att påverkas av dina valda erbjudanden.

* Använd [Traffic Estimator](/help/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) så att du får en uppfattning om hur lång tid det tar för personaliseringsmodeller att bygga in din Automated Personalization-aktivitet.
* Bestäm fördelningen mellan kontroll och mål innan du påbörjar aktiviteten utifrån dina mål.

   Det finns tre scenarier att tänka på baserat på målet för din aktivitet och vilken typ av kontroll du har valt:

   * **Random Experiences as your control and your activity target is to test the effect of the personalization algorithm**: Om målet är att utvärdera personaliseringsalgoritmen vill ni ha en mer exakt bild av lyften. Du skulle också troligtvis vilja jämföra med konverteringsgraden för dina upplevelser/erbjudanden om du bara gjorde ett A/B-test (en slumpmässigt kontrollerad kontroll). I sådana fall rekommenderas att man använder en tilldelning på 50 % för att kontrollera slumpmässigt hanterade upplevelser.
   * **&quot;Slumpmässiga upplevelser&quot; när kontrollen och ditt verksamhetsmål är att maximera personaliserad trafik**: Om du känner dig trygg med algoritmen och vill ha maximalt antal personaliserade trafikdata, rekommenderar vi att du använder 10 till 30 % för att kontrollera. Höjdpunkten här är den noggrannhet som du kommer att se i din lyftinformation (eftersom tillförlitlighetsintervallen för din kontrolltrafik kommer att bli större eftersom det finns mindre trafik till dem).
   * **En specifik upplevelse som er kontroll, med båda måltyperna**: Om du vill jämföra en specifik marknadsföringsdriven upplevelse med personaliseringsmodellerna rekommenderar vi att du anger 10 till 30 % för att få kontroll. När du bara väljer en upplevelse som kontroll sprids inte trafiken över alla erbjudanden/upplevelser i aktiviteten.

* Målreglerna bör användas så sparsamt som möjligt eftersom de kan påverka modellens förmåga att optimera.
* Rapporteringsgrupper kan begränsa hur framgångsrik din Automated Personalization-aktivitet är. De bör endast användas under särskilda förhållanden.

   * Använd bara rapportgrupper om följande villkor uppfylls: (1) du planerar att ersätta/lägga till nya erbjudanden medan aktiviteten pågår, (2) erbjudandena i rapporteringsgruppen tilltalar samma besökare och (3) erbjudandena i den rapporteringsgruppen har ungefär samma totala svarsfrekvens.
   * Det finns ingen personalisering mellan erbjudanden i en rapporteringsgrupp: erbjudandena behandlas på samma sätt av personaliseringsmodellen.
   * Lägg aldrig alla erbjudanden i en aktivitet i en enda rapporteringsgrupp. Detta beslut kommer att få alla erbjudanden att slumpmässigt skickas till alla besökare i aktiviteten.

## Vanliga frågor

Se följande frågor och svar när du arbetar med Automatisk fördelning av aktiviteter:

### Vilka begränsningar finns det i Automated Personalization? {#section_08BA09ED51B547299963C94FE6417CFA}

Target har en hård gräns på 30 000 upplevelser, men fungerar som bäst när färre än 10 000 upplevelser skapas.

### Hur implementeras målinriktning på erbjudandenivå? {#section_9D7A86EA93D74E9B8C81072A681263A4}

När varje besökare anländer bestäms de möjliga erbjudandena som besökaren kan se av reglerna för målinriktning på erbjudandenivå. Algoritmen väljer sedan det erbjudande som modellen förutser ska ha den bästa förväntade intäkten eller möjligheten till konvertering bland dessa erbjudanden. Observera att målgruppsanpassning påverkar effekten av Target maskininlärningsalgoritmer och därför bör användas så sparsamt som möjligt.

### Min aktivitet lyfter inte. Vad är det som pågår? {#section_BFA07C8C258F45318F73A461B8F32737}

Det krävs fyra faktorer för att en AP-aktivitet ska kunna generera lyft:

* Erbjudandena på varje plats måste vara tillräckligt olika för att påverka besökarna.
* Platserna måste vara någonstans som gör skillnad för optimeringsmålet.
* Det måste finnas tillräckligt med trafik och statistisk styrka i verksamheten för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

Mer information finns i [Felsökning av Automated Personalization](/help/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

### Hur tilldelar Automated Personalization trafiken? {#section_4369364F77804E0D9B78BEE551DA5659}

Automated Personalization dirigerar besökarna till den upplevelse som har det högsta prognostiserade framgångsmåttet baserat på de senaste [Slumpmässig skog](/help/c-activities/t-automated-personalization/algo-random-forest.md)-modellerna som skapats för varje modell. Denna prognos baseras på besökarens specifika information och besökskontext.

Anta till exempel att en AP-aktivitet har två platser med två erbjudanden vardera. På den första platsen har erbjudande A en prognostiserad konverteringsgrad på 3 % för en viss besökare, och erbjudande B har en prognostiserad konverteringsgrad på 1 %. På den andra platsen har Offer C en prognostiserad konverteringsgrad på 2 % för samma besökare och Offer D har en prognostiserad konverteringsgrad på 5 %. Därför skulle Automated Personalization ge besökaren en upplevelse av Erbjudande A och Erbjudande D.

### När ska jag stoppa min Automated Personalization-aktivitet? {#section_C51F3DAB8887463BB147373F6FE06B93}

Automated Personalization kan användas som&quot;alltid on&quot;-personalisering som hela tiden optimeras. I synnerhet för grönt innehåll behöver du inte stoppa din Automated Personalization-aktivitet. Om du vill göra omfattande ändringar av innehåll som inte liknar de erbjudanden som för närvarande finns i din Automated Personalization-aktivitet, är det bästa sättet att starta en ny aktivitet så att andra användare som granskar rapporter inte förväxlar eller relaterar tidigare resultat med annat innehåll.

### Hur länge ska jag vänta på att modeller ska byggas? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

Hur lång tid det tar för modeller att bygga in din aktivitet beror vanligtvis på trafiken till de valda aktivitetsplatserna och hur framgångsrik aktiviteten är. Använd [Traffic Estimator](/help/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) för att fastställa hur lång tid det förväntas ta för modeller att bygga in din aktivitet.

### En modell är inbyggd i min aktivitet. Är besöken till den upplevelsen personaliserade? {#section_51EA953C6D1D4A3185FC9DD290D66621}

Nej, det måste finnas minst två modeller i din aktivitet för att personaliseringen ska kunna börja.

### När kan jag se resultaten av min Automated Personalization-verksamhet? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

Du kan börja titta på resultaten av din Automated Personalization-aktivitet när du har minst två upplevelser med färdiga modeller (grön bockmarkering) för den upplevelse som har färdiga modeller.

### Hur kan jag minska tiden som behövs för att modeller ska kunna bygga in min aktivitet? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

Granska din aktivitetskonfiguration och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsgrad kommer att öka de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller.
* Finns det några upplevelser du kan släppa från din aktivitet? Genom att minska antalet upplevelser i en aktivitet kan du snabbare skapa modeller.
* Finns det en sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

### Varför ser besökarna upplevelser för en AP-aktivitet som de inte ska se? {#section_41CECEAE0881446A8D9F3B016857914B}

Automated Personalization-aktiviteter utvärderas en gång per session. Om det finns aktiva sessioner som har kvalificerat sig för en viss upplevelse och nu har nya erbjudanden lagts till, kommer användarna att se det nya innehållet tillsammans med tidigare erbjudanden. Eftersom de tidigare har kvalificerat sig för de här upplevelserna skulle de fortfarande se dem under hela sessionen. Om du vill utvärdera detta vid varje sidbesök bör du byta till aktivitetstypen Experience Targeting (XT).

### Kan jag ändra målmåttet genom en Automated Personalization-aktivitet? {#change-metric}

Vi rekommenderar inte att du ändrar målmåttet halvvägs genom en aktivitet. Även om det går att ändra målmåttet under en aktivitet med hjälp av användargränssnittet i [!DNL Target] bör du alltid starta en ny aktivitet. Vi garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Den här rekommendationen gäller för [!UICONTROL Auto-Allocate]-, [!UICONTROL Auto-Target]- och [!UICONTROL Automated Personalization]-aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag använda alternativet Återställ rapportdata när jag kör en Automated Personalization-aktivitet?

Du bör inte använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Automated Personalization]-aktiviteter. Även om det tar bort synliga rapportdata tas inte alla utbildningsposter bort från [!UICONTROL Automated Personalization]-modellen. I stället för att använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Automated Personalization]-aktiviteter skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. (Obs! Den här vägledningen gäller även för [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter.)

### Hur bygger Automated Personalization modeller för olika miljöer?

En modell är byggd för att identifiera den personaliserade strategins prestanda jämfört med slumpvis betjänad trafik jämfört med att skicka all trafik till den övergripande vinnande upplevelsen. Den här modellen hanterar endast träffar och konverteringar i standardmiljön.

Trafik från en andra uppsättning modeller byggs för varje modellgrupp (AP) eller upplevelse (AT). För var och en av dessa modeller beaktas träffar och konverteringar i alla miljöer.

Förfrågningar kommer därför att hanteras enligt samma modell, oavsett miljö, men den stora trafikmångfalden bör komma från standardmiljön för att säkerställa att den identifierade övergripande vinnande upplevelsen överensstämmer med det verkliga beteendet.
