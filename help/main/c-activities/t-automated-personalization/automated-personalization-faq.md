---
keywords: felsökning;vanliga frågor;Vanliga frågor;Vanliga frågor;Vanliga frågor;Automatisk personalisering;kontroll;standardupplevelse;bästa praxis
description: Se en lista med vanliga frågor och svar om [!UICONTROL Automated Personalization] (AP) aktiviteter i [!UICONTROL Adobe Target].
title: Hur hittar jag Frågor och svar om [!UICONTROL Automated Personalization] Verksamheter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 0%

---

# Vanliga frågor om Automated Personalization

Se följande frågor och svar när du arbetar med [!UICONTROL Automated Personalization] verksamhet i [!DNL Adobe Target].

## Kan jag ange en specifik upplevelse som ska användas som kontroll i en [!UICONTROL Automated Personalization] aktivitet?

+++Se information

Du kan välja en upplevelse som ska användas som kontroll när du skapar en [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) aktivitet.

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använd en specifik upplevelse som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

## Hur kan jag jämföra [!UICONTROL Automated Personalization] till en standardupplevelse? {#section_46C1A620A2384C2C8392D6716DD18495}

+++Se information

Det finns inget alternativ för att jämföra [!UICONTROL Automated Personalization] till en standardupplevelse. Om det finns ett standarderbjudande eller en standardupplevelse som en del av den övergripande aktiviteten kan du lösa problemet genom att klicka på[!UICONTROL Control]&quot; i rapporter och hitta just det erbjudandet i den rapport som skapas. Den konverteringsgrad som registreras för det här erbjudandet kan användas för att jämföra konverteringsgraden för hela segmentet &quot;Slumpskog&quot;. Detta hjälper till att jämföra hur datorn fungerar jämfört med standarderbjudandet.

+++

## Vilka är de bästa sätten att skapa en [!UICONTROL Automated Personalization] aktivitet? {#section_E155B26282BE49B58EA2683413D11DE6}

+++Se information

* Om du vill anpassa en sida med lägre trafik eller vill göra strukturella ändringar av den upplevelse du personaliserar bör du överväga att använda en [!UICONTROL Auto-Target] verksamhet i stället för [!UICONTROL Automated Personalization]. Se [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* Överväg att slutföra en [!UICONTROL A/B Test] aktivitet mellan erbjudanden och platser som du tänker använda i [!UICONTROL Automated Personalization] för att säkerställa att platsen och erbjudandena påverkar optimeringsmålet. Om en [!UICONTROL A/B Test] aktiviteten inte visar på någon betydande skillnad, [!UICONTROL Automated Personalization] sannolikt inte heller genererar lyft.

   * Om ett A/B...N-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är en eller flera av följande situationer troligen ansvariga:

      * Anbuden skiljer sig troligen inte tillräckligt mycket från varandra.
      * De platser du har valt påverkar inte resultatmåttet.
      * Optimeringsmålet ligger för långt i konverteringstratten för att påverkas av dina valda erbjudanden.

* Se till att du använder [Trafikberäkning](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) så att ni kan förstå hur lång tid det tar för personaliseringsmodeller att bygga in [!UICONTROL Automated Personalization] aktivitet.
* Bestäm allokeringen mellan kontrollen och målinriktningen innan du påbörjar aktiviteten utifrån dina mål.

  Det finns tre scenarier att tänka på baserat på målet för din aktivitet och vilken typ av kontroll du har valt:

   * **Random Experiences as your control and your activity target is to test the effective of the personalization algorithm**: Om ditt mål är att utvärdera personaliseringsalgoritmen vill du få en mer korrekt bild av lyft. Ni vill också troligen jämföra konverteringsgraden för era upplevelser och erbjudanden om ni bara gjorde en [!UICONTROL A/B Test] (en slumpmässig styrning). I sådana fall rekommenderas att man använder en tilldelning på 50 % för att kontrollera slumpmässigt hanterade upplevelser.
   * **&quot;Slumpmässiga upplevelser&quot; när din kontroll och ditt verksamhetsmål är att maximera personaliserad trafik**: Om du känner dig trygg med algoritmen och vill ha maximalt antal personaliserade trafikdata rekommenderar vi att du använder 10 till 30 % för att kontrollera. Hantverket här är den precision som du ser i din lyftinformation. Konfidensintervallen för din kontrolltrafik är större eftersom det är mindre trafik som flödar på dem.
   * **En specifik upplevelse som din kontroll, med båda måltyperna**: Om du vill jämföra en specifik marknadsföringsstyrd upplevelse med personaliseringsmodellerna rekommenderar vi att du anger 10 till 30 % för att få kontroll. När du bara väljer en upplevelse som kontroll sprids inte trafiken över alla erbjudanden eller upplevelser i aktiviteten.

* Målreglerna bör användas så sparsamt som möjligt eftersom de kan påverka modellens förmåga att optimera.
* Rapportgrupper kan begränsa dina [!UICONTROL Automated Personalization] aktivitet. Använd rapporteringsgrupper endast under särskilda förhållanden:

   * Använd bara rapportgrupper om följande villkor uppfylls:

      * Du planerar att ersätta eller lägga till nya erbjudanden medan aktiviteten körs.
      * Erbjudandena i rapporteringsgruppen tilltalar samma besökare.
      * Erbjudandena i den rapporteringsgruppen har ungefär samma totala svarsfrekvens.

   * Det finns ingen personalisering mellan erbjudanden i en rapporteringsgrupp. Erbjudandena behandlas på samma sätt av personaliseringsmodellen.
   * Lägg aldrig alla erbjudanden i en aktivitet i en enda rapporteringsgrupp. Om du gör det får alla erbjudanden en enhetlig och slumpmässig hantering av alla besökare i aktiviteten.

+++

## Vad finns det för begränsningar i [!UICONTROL Automated Personalization]? {#section_08BA09ED51B547299963C94FE6417CFA}

+++Se information

[!DNL Target] har en hård gräns på 30 000 upplevelser, men den fungerar som bäst när färre än 10 000 upplevelser skapas.

Samma gräns gäller även när aktiviteten har aktiverat [!UICONTROL Disalow Duplicates] alternativ.

Mer information om teckenbegränsningar och andra begränsningar (erbjudandestorlek, målgrupper, profiler, värden, parametrar o.s.v.) som påverkar aktiviteter och andra element i [!DNL Target], se [Gränser](/help/main/r-troubleshooting-target/target-limits.md).

+++

## Hur implementeras målgruppsanpassning på erbjudandenivå? {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++Se information

När varje besökare anländer bestäms de möjliga erbjudandena som besökaren kan se av reglerna för målinriktning på erbjudandenivå. Algoritmen väljer sedan det erbjudande som modellen förutspår har den bästa förväntade intäkten eller möjligheten till konvertering från dessa erbjudanden. Målgruppsanpassning påverkar effektiviteten hos [!DNL Target] Maskininlärningsalgoritmer och därför bör användas så sparsamt som möjligt.

+++

## Varför är min [!UICONTROL Automated Personalization] aktiviteten inte lyfter? {#section_BFA07C8C258F45318F73A461B8F32737}

+++Se information

Det krävs fyra faktorer för [!UICONTROL Automated Personalization] Aktivitet för att skapa lyft:

* Erbjudandena på varje plats måste vara tillräckligt olika för att påverka besökarna.
* Platserna måste vara någonstans som gör skillnad för optimeringsmålet.
* Det måste finnas tillräckligt med trafik och statistisk styrka i verksamheten för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av en enkel, icke-personaliserad [!UICONTROL A/B Test] aktivitet. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om A/B-testresultaten visar en statistiskt signifikant förbättring av en eller flera upplevelser är det troligt att en personaliserad aktivitet blir framgångsrik. Personalisering kan fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på erbjudanden eller platser som inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

Mer information finns i [Felsökning av Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

+++

## Hur [!UICONTROL Automated Personalization] tilldelar min aktivitet trafik? {#section_4369364F77804E0D9B78BEE551DA5659}

+++Se information

[!UICONTROL Automated Personalization] dirigerar besökarna till upplevelsen som har den högsta prognosen för framgång baserat på den senaste [Slumpmässig skog](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) modeller som är byggda för varje modell. Denna prognos baseras på besökarens specifika information och besökskontext.

Anta till exempel att [!UICONTROL Automated Personalization] aktiviteten hade två platser med två erbjudanden vardera. På den första platsen har erbjudande A en prognostiserad konverteringsgrad på 3 % för en viss besökare, och erbjudande B har en prognostiserad konverteringsgrad på 1 %. På den andra platsen har Offer C en prognostiserad konverteringsgrad på 2 % för samma besökare och Offer D har en prognostiserad konverteringsgrad på 5 %. Därför bör [!UICONTROL Automated Personalization] ger besökaren en upplevelse av erbjudandet A och erbjudandet D.

+++

## När borde jag stoppa min [!UICONTROL Automated Personalization] aktivitet? {#section_C51F3DAB8887463BB147373F6FE06B93}

+++Se information

[!UICONTROL Automated Personalization] kan användas som&quot;alltid on&quot;-personalisering som ständigt optimeras. I synnerhet när det gäller innehåll som alltid är grönt behöver du inte stoppa [!UICONTROL Automated Personalization] aktivitet. Om du vill göra väsentliga ändringar i innehållet som inte liknar de erbjudanden som finns i [!UICONTROL Automated Personalization] är det bästa sättet att starta en ny aktivitet. Genom att starta en ny aktivitet kan andra användare granska rapporter för att inte förväxla eller relatera tidigare resultat med annat innehåll.

+++

## Hur länge ska jag vänta på att modeller ska byggas? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++Se information

Hur lång tid det tar för modeller att bygga in din aktivitet beror vanligtvis på trafiken till de valda aktivitetsplatserna och hur framgångsrik aktiviteten är. Använd [Trafikberäkning](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) för att avgöra hur lång tid det tar för modellerna att bygga in din aktivitet.

+++

## En modell har byggts i [!UICONTROL Automated Personalization] aktivitet. Är besöken till den upplevelsen personaliserade? {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++Se information

Nej, det måste finnas minst två modeller i din aktivitet för att personaliseringen ska kunna börja.

+++

## När kan jag se resultaten av [!UICONTROL Automated Personalization] aktivitet? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++Se information

Du kan börja titta på resultaten av [!UICONTROL Automated Personalization] efter att du har skapat minst två upplevelser med modeller (grön bockmarkering) för den upplevelse som har modeller.

+++

## Hur kan jag minska tiden för modeller att bygga in [!UICONTROL Automated Personalization] aktivitet? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++Se information

Granska din aktivitetskonfiguration och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsfrekvens ökar de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller.
* Finns det några upplevelser du kan ta bort från din aktivitet? Genom att minska antalet upplevelser i en aktivitet går det snabbare att skapa modeller.
* Finns det en sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

+++

## Varför ser besökarna upplevelser för en [!UICONTROL Automated Personalization] aktivitet som de inte borde se? {#section_41CECEAE0881446A8D9F3B016857914B}

+++Se information

[!UICONTROL Automated Personalization] aktiviteter utvärderas en gång per session. Om det finns aktiva sessioner som har kvalificerat sig för en viss upplevelse och nu har nya erbjudanden lagts till, kommer besökarna att se det nya innehållet tillsammans med tidigare visade erbjudanden. Eftersom dessa besökare tidigare var kvalificerade för dessa upplevelser, ser de fortfarande de upplevelserna under sessionen. Om du vill utvärdera detta vid varje sidbesök ska du ändra till [!UICONTROL Experience Targeting] (XT) aktivitetstyp.

+++

## Kan jag ändra målmåttet genom en [!UICONTROL Automated Personalization] aktivitet? {#change-metric}

+++Se information

[!DNL Adobe] rekommenderar inte att du ändrar målmåttet på halvvägs genom en aktivitet. Även om det är möjligt att ändra målmåttet under en aktivitet med [!DNL Target] Gränssnittet, du bör alltid starta en ny aktivitet. [!DNL Adobe] garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Denna rekommendation gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

+++

## Kan jag använda [!UICONTROL Reset Report Data] alternativ när en [!UICONTROL Automated Personalization] aktivitet?

+++Se information

[!DNL Adobe] rekommenderar inte att du [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Automated Personalization] verksamhet. Även om det tar bort synliga rapportdata, tas inte alla utbildningsposter bort från [!UICONTROL Automated Personalization] modell. I stället för att använda [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Automated Personalization] skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. Denna vägledning gäller även för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet.

+++

## Hur [!UICONTROL Automated Personalization] bygga modeller med avseende på miljöer?

+++Se information

En modell är byggd för att identifiera den personaliserade strategins prestanda jämfört med slumpvis betjänad trafik jämfört med att skicka all trafik till den övergripande vinnande upplevelsen. Den här modellen hanterar endast träffar och konverteringar i standardmiljön.

Trafik från en andra uppsättning modeller byggs för varje modellgrupp ([!UICONTROL Automated Personalization]) eller upplevelse ([!UICONTROL Auto-Target]). För var och en av dessa modeller beaktas träffar och konverteringar i alla miljöer.

Förfrågningar hanteras därför i samma modell, oavsett miljö. Den mångsidiga trafiken bör dock komma från standardmiljön för att säkerställa att den identifierade övergripande vinnarupplevelsen överensstämmer med det verkliga beteendet.

+++
