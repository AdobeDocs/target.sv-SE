---
keywords: välkomstpaket;målvälkomstpaket;introduktion;komma igång
description: Läs tips från vår expertpanel om hur du använder Adobe [!DNL Target] som en del av testnings- och personaliseringsarbetet.
title: Var hittar jag tips och tricks för att använda Target?
feature: Overview
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '2903'
ht-degree: 0%

---

# Kapitel 4: Tips för att använda Target

Baserat på vårt arbete med många [!DNL Target] har vi observerat sätt att få ut mer av dina [!DNL Target] lösning. Vi har sammanställt alla de tips vi har tagit med i det här kapitlet. Även om du inte är redo att använda alla dessa idéer med en gång, så håll fast vid den här listan. Ju mer du får en upplevelse av lösningen och ju mer programmet mognar desto mer får du se hur dessa tips kan hjälpa dig att uppnå mer med [!DNL Target].

## Tips 1: Öka personaliseringen genom att utöka besökarprofilen med ytterligare data.

Ni kan personalisera upplevelser med [!DNL Target] data direkt vid leverans. Men personalisera djupare genom att lägga in egna data i mixen. Du kan utöka din profil med historiska data från [!DNL Adobe Analytics] och realtidsdata från [!DNL Adobe Audience Manager]. Du kan också använda kundattribut, en funktion i personbastjänsten i [!DNL Adobe Experience Cloud]för att enkelt överföra CRM-data, data från andra leverantörer och data som köpts från tredje part till [!DNL Target].

Du kan till exempel koppla inköpsdata från ditt butikssystem till en besökarprofil. Det gör du genom att skapa en CSV-fil med upp till 200 offlinevariabler och sedan överföra den direkt till [!DNL Adobe Experience Cloud] via en filöverföring, eller använd FTP för att lagra och schemalägga filen så att den uppdateras regelbundet. När kundattributen är inlagda [!DNL Adobe Experience Cloud]kan du mappa dem till [!DNL Experience Cloud] lösningar som [!DNL Adobe Analytics] och [!DNL Target] där de kommer att finnas tillgängliga för analys, testning och personalisering.

Se [Anpassade attribut](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) för steg-för-steg-instruktioner.

**Bra att veta**: För [!DNL Target] är en öppen och agnostisk plattform som fungerar bra med olika tekniker, och du kan lägga till CRM- eller köpta data på många olika sätt. Det innebär att du kan välja en metod som fungerar bäst för din organisation.

Se [Metoder för att hämta data till Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/) för mer information.

## Tips 2: Gör personligare genom att blanda [!DNL Target] målgrupper med andra Adobe Experience Cloud-målgrupper.

Blanda målgrupper som lever i olika [!DNL Adobe Experience Cloud] -lösningar kan ge er en mycket vidare förståelse för era kunder och även förmågan att personalisera djupare. Till exempel, men [!DNL Target] tillhandahåller målgruppsdata i realtid, [!DNL Adobe Analytics] tillhandahåller historiska målgruppsdata. Genom att kombinera de två kan ni identifiera när en kunds beteende är konsekvent och när det kan finnas en möjlighet att agera på ett nytt beteende. Klicka bara på listrutan bredvid&quot;Alla besökare&quot; när du skapar en aktivitet. Markera sedan rutorna för upp till tjugo målgrupper, klicka på Kombinera flera målgrupper och klicka på Spara.

Se [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md) för steg-för-steg-instruktioner.

**Bra att veta**: [!DNL Adobe Audience Manager] målgrupper finns i [!DNL Target] automatiskt. Men [!DNL Adobe Analytics] målgruppsdelning kräver lite manuell konfiguration. Markera bara rutan&quot;Make this an Experience Cloud)&quot; under målgruppsprocessen i [!DNL Analytics]. Sedan från [!DNL Target]klickar du på Importera Experience Cloud-målgrupper.

## Tips 3: Exportera data från [!DNL Target] för att använda med verktyg från tredje part.

Med svarstoken kan administratörer enkelt få ut data från [!DNL Target] och till verktyg från tredje part. Detta kan vara praktiskt när du vill lägga till data till data som samlats in med ett undersökningsverktyg. Om en undersökning till exempel visar ett urval av en population som fick upplevelsen &quot;9&quot; och en annan fick upplevelsen &quot;4&quot;, kan du använda dina data för att se vem som fick upplevelsen A och vem som såg upplevelsen B. Du kan också använda svarstoken för att exportera [!DNL Target] data till data warehouse. Klicka bara på&quot;Administration&quot; och växla sedan till den aktuella positionen bredvid den önskade svarstoken. Skapa sedan en aktivitet. Data kan sedan överföras till tredjepartsleverantören. Du kan verifiera att [!DNL Target] exporterar data med felsökningsverktyg.

Se [Svarstoken](/help/main/administrating-target/response-tokens.md) för steg-för-steg-instruktioner.

**Användbar ledtråd**: Innan en administratör kan aktivera en svarstoken som är associerad med en tredje part måste en utvecklare skapa ett partnerskap med det tredjepartsföretaget.

Se [Svarstoken](/help/main/administrating-target/response-tokens.md) för steg-för-steg-instruktioner.

**Gör detta först**: Kontrollera att du använder at.js version 1.1 eller senare. Om du använder en tidigare version kommer du att se svarstoken, men at.js kommer inte att kunna använda den.

## Tips 4: Bygg målgrupper utifrån dessa nyckelvariabler för att öka värdet av er aktivitet.

När du skapar målgrupper för målinriktning eller testning av kampanjer och erbjudanden ska du först ta hänsyn till följande:

* Beteende. Mönster för webbplatsbesök och inköpsmönster
* Referent. Referera till webbplatser och kampanjer
* Tidsbestämd. Dagstid, veckodagar och säsongsrelaterade faktorer
* Offline. Besök och köp i fysiska butiker
* Miljö. Ursprungsland, operativsystem, webbläsartyp

## Tips 5: Ge användarna den åtkomstnivå de behöver för att kunna utföra sitt jobb.

Gör det enkelt att arbeta med organisationens data samtidigt som de är säkra. [!DNL Target Premium] ger administratörer möjlighet att styra åtkomstnivån för olika interna och externa team.

Se [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) för mer information.

**Användbar ledtråd**: När du lägger till användare och namnet på en teammedlem inte har lagts till i organisationen tidigare, vilket kan vara fallet med en tredjepartsanställd, utlöses en e-postinbjudan om att gå med i teamets arbetsyta om du anger deras e-postadress och lösenord.

Använder du målstandard? Du kan fortfarande [tilldela tre åtkomstnivåer](/help/main/administrating-target/c-user-management/c-user-management/user-management.md) för dina användare med skrivskyddade roller, redigeringsroller och godkännarroller!

## Tips 6: Upptäck hur ett erbjudande fungerar under en kundresa genom att testa det på alla sidor i resan.

Se hur ett erbjudande, till exempel fri frakt, fungerar under en kundresa som äger rum på flera sidor på er webbplats.

Se [Flersidig aktivitet](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md) för steg-för-steg-instruktioner.

**Användbar ledtråd**: Om du ändrar URL:en efter att du har angett ett sidintervall återställs upplevelsen. Det innebär att de angivna variationerna inte visas längre. Kom ihåg att definiera om upplevelsen om du behöver ändra URL-adressen.

## Tips 7: Testa ett erbjudande med olika målgrupper för att se om målgrupperna har olika preferenser.

Med Experience Versions kan ni göra ett test med variationer för så många målgrupper ni vill. Du kan t.ex. skapa en banner-annons som erbjuder fri frakt - med bild- och valutavariationer för kunder i USA, Storbritannien och USA - utan att behöva göra tester för tre olika målgrupper.

Se [Målgrupper med olika upplevelser i ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) och [Upplevelseversioner i Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) för steg-för-steg-instruktioner.

## Tips 8: Spara tid genom att replikera aktivitetsupplevelser på liknande sidor.

Skapa en variant på en webbsida, till exempel en ny knappfärg, och tillämpa den automatiskt på alla sidor som delar samma mall. Du kan ange sidor eller tillämpa variationerna på alla liknande sidor på webbplatsen.

Se [Inkludera samma upplevelse på liknande sidor](/help/main/c-experiences/c-visual-experience-composer/temtest.md) för steg-för-steg-instruktioner.

## Tips 9: Minska störande detaljer i målgruppsbiblioteket genom att skapa engångspubliker.

Om ni riktar in er på ett segment som ni vet inte riktar in er på igen - till exempel kunder som drabbats av ett oväntat väderläge - kan ni få jobbet gjort utan att ni behöver lära er mer om målgruppsbiblioteket. Det gör det enklare att hitta målgrupper som du använder om och om igen.

Se [Skapa en målgrupp som bara är aktiv](/help/main/c-target/creating-activity-only-audience.md) för steg-för-steg-instruktioner.

**Mycket efterfrågad funktion**: Våra kunder bad oss att göra det möjligt att förhindra att enstaka målgrupper sparas automatiskt i målgruppsbiblioteket. Nu behöver de inte längre ta bort målgrupper manuellt för att hålla sina bibliotek organiserade.

## Tips 10: Kör enkla tester snabbare genom att inte använda standardprocessen för kvalitetssäkring.

Det finns inget värre än att ha en aktivitet redo att gå och sedan vänta veckor på att den ska slutföra den vanliga kvalitetssäkringsprocessen. Du kan använda QA-funktioner i de flesta fall genom att bara skicka runt några QA-länkar till kollegor och testa dem i olika webbläsare. Du kommer troligen att vilja göra fler kvalitetstester för att få saker som förändrar webbplatsens funktion dramatiskt, men i verkligheten bör du ha färre av dessa aktiviteter och mycket mer av de mer grundläggande aktiviteterna. Genom att lägga till bättre behörighetskontroller så att färre personer kan ge liv åt saker och ting får du också meningsfulla begränsningar och kan uppnå det du behöver utan att offra hastighet och effektivitet. Ett annat alternativ är att ha en utsedd IT-resurs för att ge snabb överblick över QA-processen.

Se [Aktivitets-QA](/help/main/c-activities/c-activity-qa/activity-qa.md) för steg-för-steg-instruktioner.

## Tips 11: Kör tester på sidor med hög trafik så att de blir statistiskt signifikanta snabbare.

Många marknadsförare lanserar optimeringsprogram för målgruppssegmentering och målgruppsanpassning utan att kontrollera om trafiknivåerna och målgrupperna som representeras ger betydande resultat inom testtidsramen för optimerings- och konverteringsmålen. För att undvika detta vanliga misstag ska du besvara följande frågor i förväg:

* Hur många unika besökare har sidan dagligen?
* Vilken konverteringsgrad har sidan?
* Hur länge tror du att du behöver köra testet innan du kan kalla det fullständigt?

**Användbar tips**: Använd målet [exempelstorlekskalkylator](https://experienceleague.adobe.com/tools/calculator/testcalculator.html) för att avgöra vilken provstorlek som krävs för ett lyckat test.

## Tips 12: Utforma enklare tester för att vara säker på att du kan skapa och implementera dem.

Efter att ha övervägt alla aspekter av hur du utformar ett test kan en plan bli mycket komplex. Baserat på var ert företag är med testning och er grupps förmåga att utforma, koda, genomföra och analysera resultaten, kan ni avgöra om testet verkar för ambitiöst. Om så är fallet, var beredd att minska dess omfattning och komplexitet. Bättre att börja litet än att inte göra testet alls. Du kan inte ge en slagkraftig lyft om du aldrig startar testet. Det är viktigt att balansera teamets ambitioner med realiteterna i era resurser och förmågor.

## Tips 13: Dela upp komplexa tester i mindre testaktiviteter så att de blir möjliga att genomföra.

I stället för att utveckla ett stort test med flera variabler och komplex utveckling, kan du utveckla en mindre komplex serie med mindre tester med minimala variabler. Detta ger en djupare förståelse för testprestanda baserat på specifika variabler. Det minskar också eventuella tekniska problem som kan uppstå vid utveckling av större projekt.

![Bryt komplexa tester, illustration](/help/main/c-intro/assets/break-complex-tasks.png)

## Tips 14: Maximera testets påverkan genom att testa närmare slutet av konverteringsprocessen.

Testning så nära sidan där besökarna klickar på Complete Purchase, Submit Application eller på annat sätt slutför en konvertering tenderar att ge mest effektiva resultat. Besökare som kommer till slutet av processen är mer kvalificerade, har investerat mer tid och är redo att köpa, så att ni kan testa insikter om deras preferenser och åtgärder och göra lönsamma ändringar. Eftersom sidorna på köpbanan är avgörande för konverteringsgraden, bör testerna som utförs på dessa sidor integreras med viktiga intressenter innan de distribueras.

![Illustration av konverteringsprocessen](/help/main/c-intro/assets/conversion-funnel.png)

## Tips 15: Uppdatera testerna kontinuerligt och gör iterativa förbättringar.

Om din hypotes inte visar sig vara sann, tänk på sätt att förbättra testet. Tänk på att även om ingen av de testade upplevelserna fungerade bättre så var ditt experiment inte slöseri med tid. Ett lyckat test innebär inte alltid en ökning av intäkter eller konverteringar. Om testet faktiskt stödde er hypotes är ni på väg att utveckla en allmän teori. Men även om ni får ett tydligt vinnande resultat, sluta där. Alltför ofta gör marknadsförarna misstaget att testa en gång och sedan satsa på resultaten utan att förstå vad som ledde till framgången. I stället kan du iterera på dessa resultat för att ta reda på varför den främre körningsdelen var i framkanten. Detta kommer att leda till djupare insikter som ni kan använda i framtida kampanjer.

## Tips 16: Jämför tester och personaliseringsaktiviteter för idéer för att förbättra målinriktningen.

Genom att jämföra konverteringsresultatet för olika målgrupper i olika tester på olika platser kan du fokusera och förfina ett företags optimeringsstrategi. Använd testjämförelser för att identifiera vilka målgrupper som är mest värdefulla för att testa, vilka som ska få målinriktade upplevelser och vilka typer av upplevelser som mest sannolikt ger ett svar.

En kund inom finanssektorn har t.ex. kört en reklamkampanj för ett kreditkort som innefattade professionella sportevenemang. Genom partiell, faktoriell multivariattestning av landningssidorna kunde kunden optimalt balansera budskapen om kreditkortsförmåner med sporttjänster för att rikta distinkta målgrupper från kundbasen. På så sätt kunde företaget dra nytta av och maximera konverteringsgraden under ett tidskänsligt fönster runt ett stort idrottsevenemang.

## Tips 17: Gör tester användbara genom att bara starta dem om du vet att du kan agera på data.

Ett test är meningslöst om du inte är säker på hur du ska agera på data. Detta innefattar att känna till era viktigaste framgångsmått, vad som behöver hända för att pressa en vinnare, hur ni kommer att följa upp testresultaten och vad ni ska göra med målgruppsinformationen. För ett snabbt och framgångsrikt test är det av största vikt att alla grupper som deltar i testet (utvecklare, kreatörer, testspecialister och andra) är medvetna om dess roll innan teststarten.

## Tips 18: Innan du startar ett test bör du vara säker på att företaget stöder vinnaren.

Framgångsrika optimeringsorganisationer tror på begreppet testning och förstår att deras yrkesmässiga åsikter om vilken upplevelse som vinner testet inte alltid visar sig vara sanna. De avgör vinnaren baserat på en stabil grund av data och är angelägna och villiga att publicera den vinnande upplevelsen när resultatet är inne, även om det inte är i linje med deras förväntningar eller verkar vara kontraintuitivt.

En Adobe-vårdkund visade till exempel nyligen värdet av testning genom att visa hur en hjältebanderoll som teamet hade ansett vara en nedbantad bild faktiskt påverkade konverteringen negativt. Om ni ännu inte helt har accepterat testning är det bäst att först utföra enklare, mindre tester så att förändringar från testresultaten kan göras stegvis.

## Tips 19: Informera alla om att du har startat ett test för att undvika problem när webbplatsen ändras.

En av fördelarna med att konfigurera dina aktiviteter så att de använder QA-parametrar är att du kan dela länkarna med alla i teamet. Du gör fler människor medvetna om aktiviteten och ser till att de inte antar att webbplatsen inte fungerar som den ska när de träffar en testvariant.

När du är klar med testerna kan du öka medvetenheten om och intresset för testresultaten genom att kommunicera kampanjer, testresultat och särskilt lärdomar. Genom att dela resultaten med alla i organisationen undviker du också att testa en hypotes på nytt, utbildar alla om vad som fungerar och hjälper dem att i grunden utmana sina egna idéer om vad som fungerar baserat på vad ni har hittat. Det är en bra idé att ta fram en mall som du använder varje gång för att dela med dig av dina resultat och viktiga inlärningar.
Överväg sedan att skapa en delbar bok eller ett Microsoft PowerPoint-kassettdäck som kumulativt fångar dessa inlärningar.

## Tips 20: Utnyttja mobilfunktionerna för att skapa mer innovativa mobilaktiviteter.

Användarupplevelserna för surfplattor och smarttelefoner måste fokusera på pekstyrda kontroller som den primära besökarinteraktionen i stället för musklick och tangentbordskontroller. Dra nytta av mobila skärmkontroller, som svepning, beröring, dra, nypa och zooma med fingret. Använd enkla, stora knappar för att ange interaktioner och navigering, till exempel en stor kundvagn eller videouppspelningsknapp. Om du designar för mobilbutiker kan du använda avancerad produktvisualisering som är optimerad för enhetstypen. Leta alltid efter möjligheter att flytta fokus på användarupplevelsen till inbäddade, stora visningsprogram eller interaktiv zoom och panorering i helskärmsläge, 360-gradersrotation och utökade videofunktioner.

## Tips 21: Hjälp mobilbesökarna att hitta det de vill ha genom att optimera mobilsökningen.

Mobila användare har hög återgivning. De flesta använder sökningar innan de gör något annat på e-handelsplatser, vilket gör optimering av sökningar på mobilsajter avgörande. Om du vill förbättra sökmotoroptimeringen (SEO) för mobilen använder du explicita navigeringsmetoder för enkel surfning. Implementera också automatisk förslag och automatisk korrigering i sökrutor för att åtgärda svårigheterna med mobiltypning. Tillhandahåll övertygande, relevanta sökresultat optimerade för skärmstorlek och plats.

## Tips 22: Nå ut bättre till mobilmålgrupperna med tidsbaserad anpassning för mobila SEM-kampanjer.

Förstå hur och när ni ska nå era målgrupper och hur ni bättre ska hantera era dagliga annonser genom att&quot;dela&quot; era mobilkampanjer i olika segment under dagen.

Många marknadsförare gör misstag genom att inte tilldela tillräckligt med budget för att fånga upp den delen av rösten under de timmar då användningen av vissa enheter är tyngst, vilket ger stora intäkter och leder till bordet.

Till exempel ökar surfplatteanvändningen vanligen på kvällen och många användare surfar när de tittar på tv. Smarttelefonanvändare får däremot vanligtvis tillgång till innehåll var de än är. De högsta konverteringstiderna varierar också beroende på bransch, så det är viktigt att förstå när era unika kunder är mest benägna att agera.

## Kom ihåg

Tänk på följande innan vi går vidare till nästa kapitel: &quot;Inspiration for testing and personalization activity.&quot;

### När du skapar testerna, dekorera inte, var avsiktlig.

* Styr flödet med avsiktliga ögonbanor med fokus på konverteringspunkter.
* Försäkra dig om att du använder din fastighet till din fördel.
* Utnyttja bildfokus för att säkerställa att bilderna inte är dekorationer, utan fungerar för dig.
* Minska oskärpa, skärpa och oskärpa med förenklad kopia.
* Se till att du har effektiva anrop till funktionsmakron när du behöver att användaren gör något.
* Öka trovärdigheten genom användargenererat innehåll där det är möjligt.

### Förenkla er webbplats.

* Få inte kunderna att läsa. De kommer inte att göra det.
* Gör det enkelt att skanna.
* Använd punktlistor.
* Se till att texten följer en tydlig och sekventiell tankeprocess.

### Använda effektiva CTA-åtgärder

* Ställ dig själv i kundens skor.
* Använd åtgärdsorienterat språk.
* Tänk på motivation för konvertering.
* Åtgärda resultatet av konverteringen.
* Se till att CTA:er syns!
