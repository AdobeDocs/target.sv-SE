---
keywords: multivariate test;mvt;full factorial;mvt or a/b;multivariate a/b;traffic estimator;when to use mvt;mvt considerations;multivariate;partial-factorial;partial factorial;full-factorial
description: Multivariate Testing (MVT) i Adobe Target jämför kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp och identifierar vilket element som bäst påverkar aktivitetens framgång.
title: Multivariata tester
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '1439'
ht-degree: 0%

---


# Översikt över multivariata tester

[!UICONTROL Multivariate Testing] (MVT) i  [!DNL Adobe Target] jämförelser av kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp och identifiera vilket element som bäst påverkar aktivitetens framgång.

## MVT-översikt {#section_C73A2D1409EC42C9B0EDD4B976651C5E}

Multivariata tester kan hjälpa dig att identifiera den relativa påverkan specifika element har på konverteringen, jämfört med andra element på sidan. Det kan också hjälpa dig att förfina en kombination av element som har visat sig vara effektiva.

En fördel med ett multivariat-test jämfört med ett A/B-test är möjligheten att visa vilka element på sidan som har störst påverkan på konverteringen. Detta kallas även&quot;huvudeffekt&quot;. Den här informationen är användbar, till exempel genom att hjälpa dig att fastställa var du ska placera innehåll som du vill ska få störst uppmärksamhet.

Multivariata tester hjälper dig också att hitta sammansatta effekter mellan två eller flera element på en sida. En viss annons kan till exempel ge fler konverteringar när den kombineras med en viss banderoll eller hjältebild. Detta kallas även&quot;interaktionseffekt&quot;.

[!DNL Target] använder multivariata helfaktoriella tester som hjälper dig att optimera innehållet. Ett multivariat test med fullständig faktoriell testning av alla möjliga kombinationer av innehåll med samma sannolikhet. Om du till exempel har två sidelement med tre olika erbjudanden finns det nio möjliga kombinationer (3x3). Tre element, med två som innehåller tre möjliga erbjudanden och en som har två erbjudanden, har 18 alternativ (3x3x2).

I Target är varje kombination en upplevelse. I multivariata tester jämförs varje upplevelse så att du kan ta reda på vilka kombinationer som är mest framgångsrika. Samtidigt samlas data in och analyseras för att förstå hur varje plats och erbjudanden påverkar mätresultatet.

![](assets/multivariate.png)

På grund av antalet kombinationer som kan genereras kräver ett multivariat-test mer tid och trafik än ett A/B-test. Sidan måste få tillräckligt mycket trafik för att kunna ge statistiskt signifikanta resultat för varje upplevelse. För att få användbara resultat måste du förstå hur mycket trafik sidan tar emot och testa det optimala antalet kombinationer för rätt tidsåtgång för att få önskat resultat. Målets [trafikberäkning](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) kan hjälpa dig att utforma ett test som fungerar med trafiken. Innan du använder Traffic Estimator bör du ha bra statistik som visar hur många visningar och konverteringar sajten normalt tar emot. Ta hänsyn till era trafiknivåer per dag. Ju fler upplevelser en aktivitet har, desto mer trafik måste aktiviteten omfatta, eller hur länge den måste köras. Om trafiken inte är särskilt hög bör du testa ett litet antal kombinationer; I annat fall kan den tid som krävs för att skapa meningsfulla testresultat vara för lång för att vara användbar.

## MVT-terminologi {#section_DF475CA7F34B4CFDB7BE7363761D64AE}

När du skapar ett multivariat-test är det bra att förstå vissa grundläggande termer.

Det finns flera termer som används på olika sätt i branschen. I det här avsnittet definieras de termer som används av [!DNL Target].

**Kombination:** De innehållsvariationer som skapas när du testar flera innehållsalternativ på flera platser. Om du till exempel testar tre platser, var och en med tre innehållsalternativ, finns det 27 möjliga kombinationer (3x3x3). En besökare på din webbplats kommer att se en kombination som också kallas upplevelse.

**Innehåll:** Texten eller bilden som består av en provvariation inom en plats. I ett multivariata test jämförs ett antal innehållsalternativ på flera platser. I MVT-metoden kallas innehållet ibland *nivå*.

**Element:** Ett DOM-element som innehåller innehållsvariationer som ska testas i MVT-testet. Se även *Plats*.

**Plats:** Ett visst innehållsområde på en sida, som ofta finns i ett enskilt DOM-element. I MVT-metoden kallas en plats ibland *faktor*. I ett multivariat helfaktoriellt test jämförs alla möjliga kombinationer av erbjudanden på dina platser.

## När MVT ska användas jämfört med A/B {#section_3D2B966B6671406C861A1843EA41D28C}

Multivariata tester kan användas tillsammans med A/B-tester för att optimera sidan. Exempel på när du kanske vill använda dem tillsammans är:

* Använd ett A/B-test för att optimera sidlayouten, följt av ett MVT-test för att fastställa det bästa innehållet i varje element på sidan.

   Ett A/B-test kan ge viktig feedback om layouten, och MVT-tester är utmärkta när det gäller att testa innehållet i elementen i siddesignen. Genom att köra ett A/B-test på layouten innan du testar flera innehållsalternativ kan du avgöra den bästa layouten och det mest slagkraftiga innehållet.

* Använd ett MVT-test för att avgöra vilket element som är viktigast och följ sedan upp med ett mer fokuserat A/B-test på det elementet.

   När antalet olika upplevelser överstiger fem och sträcker sig över två eller fler element är det en bra idé att överväga ett MVT-test innan du kör A/B-testerna. MVT-testet visar vilka områden på sidan som mest sannolikt förbättrar konverteringen. Det här är de element som en marknadsförare ska fokusera på. MVT-testet kan till exempel visa att uppmaningen att vidta åtgärder är den viktigaste faktorn för att uppnå dina mål. När du har fastställt vilka element och vilket innehåll som är mest användbart för att du ska kunna uppnå dina mål, kan du köra ett A/B-test för att ytterligare förfina resultaten, till exempel för att testa två specifika bilder mot varandra eller jämföra ordalydelsen eller färgerna i en uppmaning till åtgärd. Genom att följa ett MVT-test med ett eller flera A/B-tester kan du fastställa vilket innehåll som är bäst för de resultat du vill ha.

## Överväganden {#section_979FE3F398654C1EA1C86E7DBC9A8DAD}

* Använd ett MVT-test när du har minst tre element att testa. Om du har färre ska du köra en serie A/B-tester.
* Markera de sidelement som du tror kommer att få störst effekt på resultatet.
* Ta inte med för många element eller platser i ett test. Ju större tal, desto längre testtid.
* Planera testdesignen i förväg. Det är inte tillrådligt att redigera ett test efter att det publicerats och data börjar samlas in och analyseras.
* Vi rekommenderar att elementen är oberoende av varandra.

   Testa till exempel inte layouten och innehållet i samma test.

* Planera ytterligare tid för kvalitetskontrollen på grund av det ökade antalet upplevelser. Du kan också använda partiell-faktoriell testning för att minska mängden trafik som behövs för ett multivariat test. Mer information finns i Delfaktoriell testning nedan:

## Delfaktoriell testning

[!DNL Target] erbjuder fullständig, faktoriell multivariattestning som ett inbyggt aktivitetsalternativ. I statistik ger Design of Experiments många strategier, eller design, för att avgöra vilka faktorer som påverkar resultaten. En sådan metod är [Taguchi-metoden](https://en.wikipedia.org/wiki/Taguchi_methods) för partiell faktoriell testning. Taguchi gör det möjligt för marknadsförare att göra en uppsättning antaganden som minskar antalet permutationer av upplevelser som behöver testas, och som i sin tur minskar trafikkraven för ett multivariat test. Denna funktionalitet och testmetod kan utnyttjas i [!DNL Target] med detta [offlinekalkylblad](/help/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Om ditt team använder andra designstrategier för experiment kan du använda det här beräkningskalkylbladet som en referensimplementering för anpassad experimentdesign.

När du använder offlineberäkningskalkylbladet bör du tänka på följande:

* Välj de element som du vill ändra och antalet versioner av varje element (3x2, 4x3 o.s.v.).
* Håll numreringen konsekvent. Om knappen till exempel är Element 1 och alternativen är Blå, Grön och Gul, är den blå knappen 1-1, den gröna knappen är 1-2 och den gula knappen är 1-3.
* Offlinekalkylbladet innehåller rätt antal upplevelser (fyra för en 3x2, nio för en 4x3 och så vidare).
* Bygg upplevelserna i A/B-arbetsflödet med [Visual Experience Composer (VEC)](/help/c-experiences/experiences.md). Du kan använda anpassad kod, redigera HTML, WYSIWYG eller valfri kombination.
* När aktiviteten är över (baserat på beräkningsverktyget för samplingsstorlek) kan du köra resultaten i kalkylbladet för att få den andra informationen.

Mer information och bästa praxis finns i [Bästa praxis för multivariata tester](/help/c-activities/c-multivariate-testing/best-practices.md#reference_53635817FFB741EF8C4E56CC70688EDD).

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetstyper (9:03) ![Översikt](/help/assets/overview.png)

I den här översiktsvideon förklaras vilka aktivitetstyper som finns i Target Standard/Premium. Multivariata tester behandlas från 4:20.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Skapa multivariata tester (9:25) ![Tutorial badge](/help/assets/tutorial.png)

I den här videon förklaras hur du förstår, planerar och skapar ett multivariat-test med hjälp av det guidade arbetsflödet i tre steg för Target.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)