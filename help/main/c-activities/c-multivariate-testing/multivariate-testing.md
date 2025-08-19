---
keywords: multivariat test;mvt;full factorial;mvt eller a/b;multivariate a/b;trafikskattare;när mvt;mvt Consider;multivariate;partiell factorial;partiell factorial;full factorial
description: Lär dig hur du använder en [!UICONTROL Multivariate Test] (MVT) i [!DNL Adobe Target]  för att jämföra kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst.
title: Vad är en [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 0%

---

# [!UICONTROL Multivariate Test] - översikt

En [!UICONTROL Multivariate Test]-aktivitet (MVT) i [!DNL Adobe Target] jämför kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp. En [!UICONTROL Multivariate Test]-aktivitet hjälper också till att identifiera vilket element som mest påverkar aktivitetens framgång.

Multivariata tester hjälper dig att identifiera den relativa påverkan specifika element har på konverteringen, jämfört med andra element på sidan. Multivariata tester kan också hjälpa dig att förfina en kombination av element som har visat sig vara effektiva.

En fördel med [!UICONTROL Multivariate Test] jämfört med ett A/B-test är möjligheten att visa vilka element på sidan som har störst påverkan på konverteringen. Den här fördelen kallas även&quot;huvudeffekt&quot;. Den här informationen är till exempel användbar för att hjälpa dig att avgöra var du ska placera innehåll som du vill ska få mest uppmärksamhet.

[!UICONTROL Multivariate Test]-aktiviteter hjälper dig även att hitta sammansatta effekter mellan två eller flera element på en sida. En viss annons kan till exempel ge fler konverteringar när den kombineras med en viss banderoll eller hjältebild. Detta kallas även&quot;interaktionseffekt&quot;.

[!DNL Target] använder multivariata helfaktoriella tester för att hjälpa dig att optimera ditt innehåll. I ett multivariat helfaktoriellt test undersöks alla möjliga kombinationer av innehåll med samma sannolikhet. Om du till exempel har två sidelement med tre olika erbjudanden finns det nio möjliga kombinationer (3x3). Tre element, med två som innehåller tre möjliga erbjudanden och en som har två erbjudanden, har 18 alternativ (3x3x2).

I [!DNL Target] är varje kombination en upplevelse. [!UICONTROL Multivariate Test] jämför varje upplevelse så att du kan ta reda på vilka kombinationer som är mest framgångsrika. Samtidigt samlas data in och analyseras för att förstå hur varje plats och erbjudanden påverkar mätresultatet.

![multivariatbild](assets/multivariate.png)

På grund av antalet kombinationer som kan genereras kräver en [!UICONTROL Multivariate Test] mer tid och trafik än ett A/B-test. Sidan måste få tillräckligt mycket trafik för att kunna ge statistiskt signifikanta resultat för varje upplevelse. För att få användbara resultat måste du förstå hur mycket trafik sidan tar emot och testa det optimala antalet kombinationer för rätt tidsåtgång för att få önskat resultat.

Målets [Trafikberäkning](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) kan hjälpa dig att utforma ett test som fungerar med trafiken. Innan du använder Traffic Estimator bör du ha bra statistik som visar hur många visningar och konverteringar webbplatsen normalt tar emot. Ta hänsyn till era trafiknivåer per dag. Ju fler upplevelser en aktivitet har, desto mer trafik måste aktiviteten omfatta, eller hur länge den måste köras. Om trafiken inte är så hög bör du testa några kombinationer. Annars kan det ta för lång tid att skapa meningsfulla testresultat.

## MVT-terminologi {#section_DF475CA7F34B4CFDB7BE7363761D64AE}

När du skapar ett multivariat-test är det bra att förstå vissa grundläggande termer.

Det finns flera termer som används på olika sätt i branschen. I det här avsnittet definieras de termer som används av [!DNL Target].

**Kombination:** Innehållsvariationerna som skapas när du testar flera innehållsalternativ på flera platser. Om du till exempel testar tre platser, var och en med tre innehållsalternativ, finns det 27 möjliga kombinationer (3x3x3). En besökare på din webbplats ser en kombination som också kallas upplevelse.

**Innehåll:** Texten eller bilden som består av en testvariation inom en plats. I ett multivariata test jämförs flera innehållsalternativ på flera platser. I MVT-metoden kallas innehållet ibland för *nivå*.

**Element:** Ett DOM-element som innehåller innehållsvariationer som ska testas i MVT-testet. Se även *Plats*.

**Plats:** Ett specifikt innehållsområde på en sida, som ofta finns i ett enskilt DOM-element. I MVT-metoden kallas en plats ibland för *faktor*. I ett multivariat helfaktoriellt test jämförs alla möjliga kombinationer av erbjudanden på dina platser.

## När [!UICONTROL Multivariate Test] ska användas jämfört med A/B {#section_3D2B966B6671406C861A1843EA41D28C}

Multivariata tester kan användas tillsammans med A/B-tester för att optimera sidan. Exempel på när du kanske vill använda dem tillsammans är:

* Använd ett A/B-test för att optimera sidlayouten, följt av ett MVT-test för att fastställa det bästa innehållet i varje element på sidan.

  Ett A/B-test kan ge viktig feedback om layouten, och MVT-tester är utmärkta när det gäller att testa innehållet i elementen i siddesignen. Genom att köra ett A/B-test på layouten innan du testar flera innehållsalternativ kan du avgöra den bästa layouten och det mest slagkraftiga innehållet.

* Använd ett MVT-test för att avgöra vilket element som är viktigast och följ sedan upp med ett mer fokuserat A/B-test på det elementet.

  När antalet olika upplevelser överstiger fem och sträcker sig över två eller fler element är det en bra idé att överväga ett MVT-test innan du kör A/B-testerna. MVT-testet visar vilka områden på sidan som mest sannolikt förbättrar konverteringen. Det här är de element som en marknadsförare ska fokusera på. MVT-testet kan till exempel visa att call to action är den viktigaste faktorn för att nå dina mål. När du har fastställt vilka element och vilket innehåll som är mest användbart för att du ska kunna uppnå dina mål, kan du köra ett A/B-test för att förfina resultatet ytterligare. Du kan till exempel testa två specifika bilder mot varandra eller jämföra ordalydelsen eller färgerna i en call to action. Genom att följa ett MVT-test med ett eller flera A/B-tester kan du fastställa vilket innehåll som är bäst för de resultat du vill ha.

## Överväganden {#section_979FE3F398654C1EA1C86E7DBC9A8DAD}

* Använd ett MVT-test när du har minst tre element att testa. Om du har färre ska du köra en serie A/B-tester.
* Markera de sidelement som du tror har störst effekt på resultatet.
* Ta inte med för många element eller platser i ett test. Ju större tal, desto längre testtid.
* Planera testdesignen i förväg. Redigera inte ett test efter att det publicerats och data börjar samlas in och analyseras.
* Elementen ska vara oberoende av varandra.

  Testa till exempel inte layouten och innehållet i samma test.

* Planera ytterligare tid för kvalitetskontrollen på grund av det ökade antalet upplevelser. Du kan också använda partiell-faktoriell testning för att minska mängden trafik som behövs för ett multivariat test. Mer information finns i Partiell faktoriell testning nedan:

## Delfaktoriell testning

[!DNL Target] erbjuder multivariata tester i helfakultet som ett inbyggt aktivitetsalternativ. I statistik
&quot;Design of Experiments&quot; erbjuder många metoder, eller utformningar, för att avgöra vilka faktorer som påverkar resultaten. En sådan metod är [Taguchi-metoden](https://en.wikipedia.org/wiki/Taguchi_methods) för partiell faktoriell testning. Taguchi gör det möjligt för marknadsförare att göra en uppsättning antaganden som minskar antalet permutationer i upplevelser som måste testas, och som i sin tur minskar trafikkraven för ett multivariat test. Den här funktionaliteten och testmetoden kan användas i [!DNL Target] med det här [offlinekalkylbladet](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Om ditt team använder andra designstrategier för experiment kan du använda det här beräkningskalkylbladet som en referensimplementering för anpassad experimentdesign.

När du använder offlineberäkningskalkylbladet bör du tänka på följande:

* Välj de element som du vill ändra och antalet versioner av varje element (3x2, 4x3 osv.).
* Se till att numreringen är konsekvent. Om knappen till exempel är Element 1 och alternativen är Blue, Green och Yellow, är den blå knappen 1-1, den gröna knappen är 1-2 och den gula knappen är 1-3.
* Offlinekalkylbladet innehåller rätt antal upplevelser (fyra för en 3x2, nio för en 4x3 och så vidare).
* Bygg upplevelserna i A/B-arbetsflödet med [Visual Experience Composer (VEC)](/help/main/c-experiences/experiences.md). Du kan använda anpassad kod, redigera HTML, WYSIWYG eller valfri kombination.
* När aktiviteten är över (baserat på beräknare av exempelstorlek) kör du resultatet via kalkylbladet för att få den andra informationen.

Mer information och metodtips finns i [Bästa praxis för multivariata tester](/help/main/c-activities/c-multivariate-testing/best-practices.md#reference_53635817FFB741EF8C4E56CC70688EDD).

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetstyper (9:03) ![Märket Översikt](/help/main/assets/overview.png)

I den här översiktsvideon förklaras vilka aktivitetstyper som är tillgängliga i [!DNL Target]. Multivariata tester diskuteras med början vid 4:20.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Skapar multivariata tester (9:25) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon förklaras hur du förstår, planerar och skapar ett multivariat-test med hjälp av det guidade arbetsflödet i tre steg för [!DNL]Target.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
