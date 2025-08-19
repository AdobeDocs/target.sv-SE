---
keywords: felsökning;vanliga frågor;Vanliga frågor;Vanliga frågor;Vanliga frågor;Automatisk personalisering;kontroll;standardupplevelse;bästa praxis
description: Utforska en lista med vanliga frågor och svar om [!UICONTROL Automated Personalization]-aktiviteter (AP) i [!UICONTROL Adobe Target].
title: Hur hittar jag vanliga frågor om [!UICONTROL Automated Personalization] aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 0%

---

# Vanliga frågor om Automated Personalization

Läs följande frågor och svar när du arbetar med [!UICONTROL Automated Personalization] aktiviteter i [!DNL Adobe Target].

## Kan jag ange en specifik upplevelse som ska användas som kontroll i en [!UICONTROL Automated Personalization]-aktivitet?

+++Se detaljer

Du kan välja en upplevelse som ska användas som en kontroll när du skapar en [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) - (AP) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)-aktivitet.

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använd en specifik upplevelse som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

## Hur kan jag jämföra [!UICONTROL Automated Personalization] med en standardupplevelse? {#section_46C1A620A2384C2C8392D6716DD18495}

+++Se detaljer

Det finns inget környckelsalternativ för att jämföra [!UICONTROL Automated Personalization] med en standardupplevelse. Om det finns ett standarderbjudande eller en standardupplevelse som en del av den övergripande aktiviteten kan du lösa problemet genom att klicka på [!UICONTROL Control]-segmentet i rapporter och leta reda på det erbjudandet i den rapport som skapas. Den konverteringsgrad som registreras för det här erbjudandet kan användas för att jämföra konverteringsgraden för hela segmentet &quot;Slumpskog&quot;. Detta hjälper till att jämföra hur datorn fungerar jämfört med standarderbjudandet.

+++

## Vilka är de bästa sätten att konfigurera en [!UICONTROL Automated Personalization]-aktivitet? {#section_E155B26282BE49B58EA2683413D11DE6}

+++Se detaljer

* Om du vill anpassa en sida med lägre trafik eller vill göra strukturella ändringar av den upplevelse du personaliserar bör du överväga att använda en [!UICONTROL Auto-Target]-aktivitet i stället för [!UICONTROL Automated Personalization]. Se [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* Överväg att slutföra en [!UICONTROL A/B Test]-aktivitet mellan erbjudandena och platserna som du planerar att använda i din [!UICONTROL Automated Personalization]-aktivitet för att se till att platsen och erbjudandena påverkar optimeringsmålet. Om en [!UICONTROL A/B Test]-aktivitet inte visar på någon större skillnad, kommer [!UICONTROL Automated Personalization] troligtvis inte att generera någon lyft.

   * Om ett A/B...N-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är en eller flera av följande situationer troligen ansvariga:

      * Anbuden skiljer sig troligen inte tillräckligt mycket från varandra.
      * De platser du har valt påverkar inte resultatmåttet.
      * Optimeringsmålet ligger för långt i konverteringstratten för att påverkas av dina valda erbjudanden.

* Använd [Traffic Estimator](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) så att du får en uppfattning om hur lång tid det tar för personaliseringsmodeller att bygga in din [!UICONTROL Automated Personalization]-aktivitet.
* Bestäm allokeringen mellan kontrollen och målinriktningen innan du påbörjar aktiviteten utifrån dina mål.

  Det finns tre scenarier att tänka på baserat på målet för din aktivitet och vilken typ av kontroll du har valt:

   * **Slumpmässiga upplevelser som din kontroll och ditt aktivitetsmål är att testa personaliseringsalgoritmens effektivitet**: Om ditt mål är att utvärdera personaliseringsalgoritmen vill du få en mer korrekt bild av lyften. Du vill troligen också jämföra konverteringsgraden för dina upplevelser eller erbjudanden om du bara gjorde en [!UICONTROL A/B Test] (en slumpmässigt kontrollerad kontroll). I sådana fall rekommenderas att man använder en tilldelning på 50 % för att kontrollera slumpmässigt hanterade upplevelser.
   * **&quot;Slumpmässiga upplevelser&quot; som din kontroll och ditt aktivitetsmål är att maximera den personaliserade trafiken**: Om du är bekväm med algoritmen och vill ha den maximala mängden trafik som personaliseras, rekommenderas en allokering på 10 till 30 % för kontroll. Hantverket här är den precision som du ser i din lyftinformation. Konfidensintervallen för din kontrolltrafik är större eftersom det är mindre trafik som flödar på dem.
   * **Specifik upplevelse som din kontroll, med någon av måltyperna**: Om du vill jämföra en specifik marknadsföringsdriven upplevelse med personaliseringsmodellerna rekommenderas en allokering på 10 till 30 % som du kan kontrollera. När du bara väljer en upplevelse som kontroll sprids inte trafiken över alla erbjudanden eller upplevelser i aktiviteten.

* Målreglerna bör användas så sparsamt som möjligt eftersom de kan påverka modellens förmåga att optimera.
* Rapporteringsgrupper kan begränsa resultatet för din [!UICONTROL Automated Personalization]-aktivitet. Använd rapporteringsgrupper endast under särskilda förhållanden:

   * Använd bara rapportgrupper om följande villkor uppfylls:

      * Du planerar att ersätta eller lägga till nya erbjudanden medan aktiviteten körs.
      * Erbjudandena i rapporteringsgruppen tilltalar samma besökare.
      * Erbjudandena i den rapporteringsgruppen har ungefär samma totala svarsfrekvens.

   * Det finns ingen personalisering mellan erbjudanden i en rapporteringsgrupp. Erbjudandena behandlas på samma sätt av personaliseringsmodellen.
   * Lägg aldrig alla erbjudanden i en aktivitet i en enda rapporteringsgrupp. Om du gör det får alla erbjudanden en enhetlig och slumpmässig hantering av alla besökare i aktiviteten.

+++

## Vilka är några begränsningar i [!UICONTROL Automated Personalization]? {#section_08BA09ED51B547299963C94FE6417CFA}

+++Se detaljer

[!DNL Target] har en hård gräns på 30 000 upplevelser, men fungerar som bäst när färre än 10 000 upplevelser skapas.

Samma begränsning tillämpas även när aktiviteten har aktiverat alternativet [!UICONTROL Disalow Duplicates].

Mer information om teckenbegränsningar och andra begränsningar (erbjudandestorlek, målgrupper, profiler, värden, parametrar o.s.v.) som påverkar aktiviteter och andra element i [!DNL Target] finns i [Gränser](/help/main/r-troubleshooting-target/target-limits.md).

+++

## Hur implementeras målgruppsanpassning på erbjudandenivå? {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++Se detaljer

När varje besökare anländer bestäms de möjliga erbjudandena som besökaren kan se av reglerna för målinriktning på erbjudandenivå. Algoritmen väljer sedan det erbjudande som modellen förutspår har den bästa förväntade intäkten eller möjligheten till konvertering från dessa erbjudanden. Anpassa erbjudandet påverkar effekten av [!DNL Target] maskininlärningsalgoritmer och bör därför användas så sparsamt som möjligt.

+++

## Varför visas inte min [!UICONTROL Automated Personalization]-aktivitet som lyft? {#section_BFA07C8C258F45318F73A461B8F32737}

+++Se detaljer

Det krävs fyra faktorer för att en [!UICONTROL Automated Personalization]-aktivitet ska kunna generera lyft:

* Erbjudandena på varje plats måste vara tillräckligt olika för att påverka besökarna.
* Platserna måste vara någonstans som gör skillnad för optimeringsmålet.
* Det måste finnas tillräckligt med trafik och statistisk styrka i verksamheten för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av en enkel, icke-personlig [!UICONTROL A/B Test]-aktivitet. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om A/B-testresultaten visar en statistiskt signifikant förbättring av en eller flera upplevelser är det troligt att en personaliserad aktivitet blir framgångsrik. Personalization kan fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på erbjudanden eller platser som inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

Mer information finns i [Felsökning av Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

+++

## Hur tilldelar [!UICONTROL Automated Personalization] min aktivitets trafik? {#section_4369364F77804E0D9B78BEE551DA5659}

+++Se detaljer

[!UICONTROL Automated Personalization] dirigerar besökare till den upplevelse som har det högsta prognostiserade framgångsmåttet baserat på de senaste [Slumpmässig skog](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)-modellerna som skapats för varje modell. Denna prognos baseras på besökarens specifika information och besökskontext.

Anta till exempel att en [!UICONTROL Automated Personalization]-aktivitet har två platser med två erbjudanden vardera. På den första platsen har erbjudande A en prognostiserad konverteringsgrad på 3 % för en viss besökare, och erbjudande B har en prognostiserad konverteringsgrad på 1 %. På den andra platsen har Offer C en prognostiserad konverteringsgrad på 2 % för samma besökare och Offer D har en prognostiserad konverteringsgrad på 5 %. Därför visar [!UICONTROL Automated Personalization] besökaren en upplevelse av erbjudandet A och erbjudande D.

+++

## När ska jag stoppa min [!UICONTROL Automated Personalization]-aktivitet? {#section_C51F3DAB8887463BB147373F6FE06B93}

+++Se detaljer

[!UICONTROL Automated Personalization] kan användas som&quot;alltid aktiverad&quot;-personalisering som ständigt optimeras. I synnerhet för omogna innehåll finns det ingen anledning att stoppa din [!UICONTROL Automated Personalization]-aktivitet. Om du vill göra omfattande ändringar av innehållet som inte liknar erbjudandena i din [!UICONTROL Automated Personalization]-aktivitet är det bästa sättet att starta en ny aktivitet. Genom att starta en ny aktivitet kan andra användare granska rapporter för att inte förväxla eller relatera tidigare resultat med annat innehåll.

+++

## Hur länge ska jag vänta på att modeller ska byggas? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++Se detaljer

Hur lång tid det tar för modeller att bygga in din aktivitet beror vanligtvis på trafiken till de valda aktivitetsplatserna och hur framgångsrik aktiviteten är. Använd [Trafikberäkning](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) för att fastställa hur lång tid det förväntas ta för modeller att bygga in din aktivitet.

+++

## En modell har skapats i min [!UICONTROL Automated Personalization]-aktivitet. Är besöken till den upplevelsen personaliserade? {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++Se detaljer

Nej, det måste finnas minst två modeller i din aktivitet för att personaliseringen ska kunna börja.

+++

## När kan jag se resultaten av min [!UICONTROL Automated Personalization]-aktivitet? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++Se detaljer

Du kan börja titta på resultaten av din [!UICONTROL Automated Personalization]-aktivitet efter att du har minst två upplevelser med modeller byggda (grön bock) för upplevelsen som har modeller skapade.

+++

## Hur kan jag minska tiden som behövs för att modeller ska kunna byggas in i min [!UICONTROL Automated Personalization]-aktivitet? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++Se detaljer

Granska din aktivitetskonfiguration och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsfrekvens ökar de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller.
* Finns det några upplevelser du kan ta bort från din aktivitet? Genom att minska antalet upplevelser i en aktivitet går det snabbare att skapa modeller.
* Finns det en sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

+++

## Varför ser besökare upplevelser för en [!UICONTROL Automated Personalization]-aktivitet som de inte ska se? {#section_41CECEAE0881446A8D9F3B016857914B}

+++Se detaljer

[!UICONTROL Automated Personalization] aktiviteter utvärderas en gång per session. Om det finns aktiva sessioner som har kvalificerat sig för en viss upplevelse och nu har nya erbjudanden lagts till, kommer besökarna att se det nya innehållet tillsammans med tidigare visade erbjudanden. Eftersom dessa besökare tidigare var kvalificerade för dessa upplevelser, ser de fortfarande de upplevelserna under sessionen. Om du vill utvärdera det här vid varje sidbesök bör du ändra till aktivitetstypen [!UICONTROL Experience Targeting] (XT).

+++

## Kan jag ändra målmåttet genom en [!UICONTROL Automated Personalization]-aktivitet? {#change-metric}

+++Se detaljer

[!DNL Adobe] rekommenderar inte att du ändrar målmåttet genom en aktivitet. Även om det går att ändra målmåttet under en aktivitet med användargränssnittet för [!DNL Target] bör du alltid starta en ny aktivitet. [!DNL Adobe] garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Den här rekommendationen gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

+++

## Kan jag använda alternativet [!UICONTROL Reset Report Data] när jag kör en [!UICONTROL Automated Personalization]-aktivitet?

+++Se detaljer

[!DNL Adobe] rekommenderar inte att du använder alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Automated Personalization]-aktiviteter. Även om synliga rapportdata tas bort, tas inte alla utbildningsposter bort från modellen [!UICONTROL Automated Personalization]. Skapa en ny aktivitet och inaktivera den ursprungliga aktiviteten i stället för att använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Automated Personalization]-aktiviteter. Den här vägledningen gäller även för [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter.

+++

## Hur bygger [!UICONTROL Automated Personalization] modeller med hänsyn till miljöer?

+++Se detaljer

En modell är byggd för att identifiera den personaliserade strategins prestanda jämfört med slumpvis betjänad trafik jämfört med att skicka all trafik till den övergripande vinnande upplevelsen. Den här modellen hanterar endast träffar och konverteringar i standardmiljön.

Trafik från en andra uppsättning modeller har skapats för varje modellgrupp ([!UICONTROL Automated Personalization]) eller upplevelse ([!UICONTROL Auto-Target]). För var och en av dessa modeller beaktas träffar och konverteringar i alla miljöer.

Förfrågningar hanteras därför i samma modell, oavsett miljö. Den mångsidiga trafiken bör dock komma från standardmiljön för att säkerställa att den identifierade övergripande vinnarupplevelsen överensstämmer med det verkliga beteendet.

+++
