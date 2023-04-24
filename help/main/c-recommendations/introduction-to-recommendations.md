---
keywords: Recommendations;intro;introduction;webbinar;demo
description: Läs om Recommendations aktiviteter i Adobe [!DNL Target] som automatiskt visar innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter eller andra algoritmer.
title: Vad är Recommendations aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '2114'
ht-degree: 0%

---

# Introduktion till Recommendations

Texten i den här artikeln kommer från *Introduktion till Recommendations* webbinarium, som du kan visa i sin helhet nedan.

The *Introduktion till Recommendations* webbinariet innehåller en djupgående undersökning av hur man utnyttjar [!DNL Adobe Target Recommendations]. Ta reda på hur detta [!DNL Target] Aktiviteten visar automatiskt produkter eller innehåll som kan intressera dina kunder genom att optimera realtidsförslag baserat på tidigare besök. Gå vidare till [!DNL Target] Ett användargränssnitt som ger dig en stegvis översikt över hur du skapar en [!DNL Recommendations] aktivitet.

## Introduktion

Vi känner alla till den typ av rekommendationer vi ser inom detaljhandeln. Allt fler kunder förväntar sig den här typen av rekommendationer och använder dem som utgångspunkt för att utforska andra tillgängliga alternativ. Om du tänker på ditt eget shoppingbeteende fungerar dessa rekommendationer verkligen bra. Nästan alla av oss har köpt en produkt som vi såg först i en rekommendation någonstans, oavsett om den fanns i en butik eller på en digital egendom.

Följande bild visar en rekommendation som visar tillbehör som vanligen köps med en ny telefon, inklusive laddningsstationer, fall och hörlurar.

![Rekommendationer som visar tillbehör som andra har köpt med en ny telefon.](/help/main/c-recommendations/assets/intro-1.png)

Men det vi inte alltid tänker på är hur varumärken som sätter det digitala först ökar ribban för kundernas förväntningar. Det sätt vi konsumerar media och innehåll på styrs i allt högre grad av personaliserade rekommendationer. Tänk på det första du ser när du öppnar Netflix, Spotify eller YouTube. Dessa varumärken utgör grunden för kundupplevelsen med rekommendationer. I en värld där det finns fler alternativ än någonsin är det viktigt att ni kan identifiera det mest relevanta innehållet för kunden vid interaktionen.

![Rekommendation som visar varumärken som tänker&quot;digitalt först&quot;](/help/main/c-recommendations/assets/intro-2.png)

Marknadsförarna använder [!DNL Adobe Target] för att skapa personaliserade upplevelser i en rad olika branscher, kundtyper och kanaler.

[!DNL Adobe Target] levererar personaliserat innehåll överallt.

![Bild som visar hur Target levererar rekommendationer på olika platser](/help/main/c-recommendations/assets/intro-3.png)

* **Publicering**: Webbutgivare använder [!DNL Target Recommendations] att rekommendera artiklar till besökare på webbplatsen och öka engagemanget.
* **Video Tutorials**: [!DNL Adobe Creative Cloud] använder [!DNL Target] för att rekommendera videokurser till Photoshop-användare i Photoshop.
* **Spel**: Spelföretag använder [!DNL Target] för att rekommendera spel och innehåll till användare på deras konsoler.
* **B2B-försäljning**: [Företag kan använda Target för att rekommendera videor, rapporter och blogginlägg till B2B-prospects. leverera nedladdningar, och hjälpa befintliga kunder](https://theblog.adobe.com/testing-shifts-high-gear-intel).

* **Resa**: [En tysk resebokförare använder Target för att rekommendera hotell och mycket mer till resenärer](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Detaljhandel**: [En ledande B2B-handlare använder Target för att rekommendera de viktigaste kategorierna och produkterna för att returnera besökare i webbläsaren och i mobilappen](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/).

Detta är bara några exempel på hur kunderna använder Target för att leverera personaliserade rekommendationer.

Vad är bra rekommendationer?

![Bild som visar de tre elementen som ger bra rekommendationer](/help/main/c-recommendations/assets/intro-4.png)

Stora rekommendationer bör vara relevanta och personaliserade. Det innebär att ni behöver tre saker för att öka relevansen och personaliseringen:

* **Marknadsföringskontroller** för att öka relevansen för de objekt som rekommenderas. Som marknadsförare ger ni tabellen ett värdefullt sammanhang och vet vilka attribut som är relevanta för en rekommendationsmodell. Om du kör en videowebbplats vet du att användarna kanske är intresserade av att se filmer från samma regissör, men du bryr dig antagligen inte om att se filmer som har producerats i samma studio. [!DNL Target] ger dig möjlighet att använda kontroller som gör att du kan förbättra dina algoritmer med den här domänkunskapen.
* **Sofistikerade modeller** för att förstå miljontals objekt i katalogen och interaktionshändelser. [!DNL Target] har sofistikerade maskininlärningsfunktioner som byggts under ett decennium av erfarenhet och vi hanterar miljarder rekommendationer per år.
* **Användarkontext** för att säkerställa att rekommendationerna är aktuella och relevanta för användarna. Du vill inte rekommendera videon som någon just tittat på eller skjortan som någon just lagt till i kundvagnen. Målets omfattande användarprofil kan användas i rekommendationer för att säkerställa personalisering.

## Implementera [!DNL Target] Recommendations

Börja med en strategi.

![Illustration som visar rekommendationsstrategi](/help/main/c-recommendations/assets/intro-5.png)

* **Vilka objekt vill du rekommendera?** Börja med att fundera på vilka objekt du vill rekommendera. Det kan vara produkter, videor eller innehåll.
* **Var vill du visa rekommendationer?** Tänk sedan på var du vill ge rekommendationer. Se vilka kanaler (webb, mobil, butiker, kioskdatorer och så vidare) som finns. Vilka delar av kundresan kommer att innehålla rekommendationer? Vilka sidor på din webbplats kommer att innehålla rekommendationer?
* **Hur avgör ni om rekommendationerna lyckas?** Anta att du har en erfarenhet utan rekommendationer och erfarenhet av rekommendationer, eller att du har två olika typer av rekommendationer. Hur skulle ni avgöra vilken upplevelse som var en bättre upplevelse för era kunder? Vissa mätvärden kan vara svårare än andra att mäta. Till exempel är effekten av rekommendationer på kundens livstidsvärde ofta svår att komma åt direkt. Det är därför ofta enklare att få till en mindre abstrakt mätmetod som är mer konkret, till exempel intäkter per besök, genomsnittligt ordervärde eller antal klick. I vissa fall kanske du vill minimera ett mått, till exempel antalet supportsamtal.

När ni har kommit fram till er strategi är ni redo att börja implementera [!DNL Target Recommendations].

Det finns tre stora steg för att skapa implementering av dina rekommendationer:

![Bild som visar hur du skapar implementering av rekommendationer](/help/main/c-recommendations/assets/intro-6.png)

1. Undervisa [!DNL Target] om ditt sammanhang eller dina produkter.
1. Hämta användarbeteende.
1. Få rekommendationer i rätt sammanhang.

### Undervisa [!DNL Target] om ditt sammanhang eller dina produkter

När du börjar med [!DNL Recommendations]skickar du information om varje objekt som du vill rekommendera. [!DNL Target] har flera integreringsalternativ för att skapa katalogen.

![Illustration som visar hur du lär ut Target om ditt sammanhang eller dina produkter](/help/main/c-recommendations/assets/intro-7.png)

Den enklaste och vanligaste metoden är att skicka en CSV-fil varje dag eller vecka från ert system för produktinformationshantering eller från ert innehållshanteringssystem. Men du kan också skicka information på datalagret från sidan med [!DNL Adobe Target] Javascript-bibliotek, utnyttja våra API:er för att skicka information direkt från källsystemet, eller använda vårt [!DNL Adobe Analytics] integrering om du redan skickar katalogdata till [!DNL Analytics].

Ibland kanske du vill använda flera alternativ tillsammans, till exempel skicka de flesta data dagligen via en CSV-fil och skicka lageruppdateringar oftare via ett API.

IT-avdelningen brukar hjälpa till att förbereda sig.

Oavsett vilken metod du väljer bör du inkludera metadata om varje objekt i tre kategorier:

![Bild som visar metadatainformation för katalogen](/help/main/c-recommendations/assets/intro-8.png)

* Data som du vill visa för användaren som tar emot rekommendationen. Filmens namn och en URL för miniatyrbild.
* Data som är användbara för att tillämpa marknadsförings- och marknadsföringskontroller. Exempel: filmens klassificering så att du inte rekommenderar NC-17-filmer.
* Data som är användbara när du vill fastställa likheter mellan objekt och andra objekt. Till exempel filmens genre eller de skådespelare som finns i filmen.

### Hämta användarbeteende

Därefter bör du lägga till taggar eller utnyttja befintliga [!DNL Analytics] implementering för att spåra konverteringshändelser (som vyer och köp) som driver [!DNL Target] algoritmer.

![Illustration som visar hur man fångar upp användarbeteenden](/help/main/c-recommendations/assets/intro-9.png)

Du måste se till att [!DNL Target] är medveten om vilka objekt dina användare visar och köper. Om köpet inte är relevant för ditt sammanhang kan du spåra en annan typ av konverteringshändelse, till exempel hämtning av PDF, slutförande av en enkät, prenumeration på ett nyhetsbrev, titta på en video o.s.v.

Om du redan använder [!DNL Target] Om du vill köra A/B-tester på din webbplats kanske du redan har slutfört det här steget. Eller om du redan använder [!DNL Adobe Analytics] om du vill rapportera om webbplatsbesök och konverteringsbeteenden kan du använda [!DNL Analytics] som din beteendedatakälla. Annars är det enklast att konfigurera detta med en tagghanterare som taggar i [[!DNL Adobe Experience Platform]](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html){target=_blank}. Du kan också skicka interaktioner offline eller i appen till [!DNL Target] via API i realtid.

### Få rekommendationer i rätt sammanhang

Skicka information om användaren och sammanhanget vid interaktionen till [!DNL Target] för att returnera relevanta och personaliserade rekommendationer.

![Bild som visar hur du får rekommendationer i rätt sammanhang](/help/main/c-recommendations/assets/intro-10.png)

Förutom användarbeteendet i sammanställningen måste du skicka [!DNL Target] det specifika sammanhang där rekommendationer visas. Detta inkluderar information om sidan och information från användarprofilen. [!DNL Target] använder den här informationen för att göra personaliserade rekommendationer. På en återförsäljarwebbplats vill du t.ex. veta vilken produkt och produktkategori besökaren tittar på just nu. Du vill också veta mer om den användaren (favoritmärke, favoritproduktkategori, lojalitetsnivå osv.). Den här informationen är viktig så att [!DNL Target] kan filtrera objekt och förbättra personaliseringen av rekommendationer.

## Bygg din första Recommendations-aktivitet

Vad är en [!DNL Recommendations] aktivitet?

![Bild som visar de delar som ger en bra rekommendationsaktivitet](/help/main/c-recommendations/assets/intro-11.png)

A [!DNL Recommendations] aktiviteten består av följande komponenter:

* **Målgrupp**: Vem ska se de här rekommendationerna?
* **Kriterier**: Vilka objekt bör rekommenderas?
* **Design**: Hur ska de rekommenderade objekten visas?

![Bild som visar vad som utgör en rekommendationsaktivitet: Målgrupper, kriterier och design](/help/main/c-recommendations/assets/intro-12.png)

Ut ur lådan, [!DNL Target] innehåller 14 inbyggda målgrupper, 42 inbyggda kriterier och 10 inbyggda designmallar. Du kan anpassa vart och ett av dessa objekt eller lägga till ett eget. Vi har haft tidigare [webbinarier om att bygga målgrupper](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. I det här avsnittet fokuseras på att definiera villkor, som definierar vilka objekt som ska rekommenderas.

Target använder konceptet med kriteriekortet. Ett villkorskort är som ett recept för personalisering.

![Illustration av kriteriekort](/help/main/c-recommendations/assets/intro-13.png)

Det är viktigt att välja eller skapa rätt kriterier för att uppnå de personaliseringsresultat ni vill ha. Ett villkor är som en kanal som tar dig från hela katalogen till den slutliga uppsättningen rekommendationer.

![Tratt illustration](/help/main/c-recommendations/assets/intro-14.png)

I följande avsnitt beskrivs de olika delarna av tratten och hur de fungerar i [!DNL Target]:

### Statiska filter (samlingar och uteslutningar)

Statiska filter är i stort sett tillämpliga regler för katalogattribut som du inte förväntar dig att ändras ofta.

![Bild på samlingar och uteslutningar](/help/main/c-recommendations/assets/intro-16.png)

I en innehållskontext kanske du vill inkludera alla filmer i rekommendationerna, men exkludera filmer med klassificering NC-17. Inom detaljhandeln kan du ha flera varumärken i olika delar av världen, men du vill bara rekommendera produkter som finns i USA. Du kanske också vill utesluta produkter från en regional privat etikett.

Det här är alla katalogattribut som är allmänt tillämpliga och som du kanske vill använda i flera rekommendationer, och du förväntar dig inte att de ska ändras ofta.

### Algoritm (rekommendationsnyckel och logik)

Nästa steg är att välja en rekommendationsnyckel och logik. Här bestämmer du vad som är grunden för din rekommendation.

![Illustration av algoritm](/help/main/c-recommendations/assets/intro-17.png)

Det första du behöver välja är rekommendationsnyckeln. Rekommendationsnyckeln är vad du &quot;letar upp&quot; för att välja rekommendationen. Det här är vad du baserar din rekommendation på.

Du kan basera din rekommendation på:

* Det objekt som besökaren för närvarande visar
* Den kategori som besökaren för närvarande visar
* Artikeln som besökaren senast köpte eller lade till i kundvagnen
* Ett anpassat attribut relaterat till en besökare eller ett objekt

Baserat på dessa tangenter väljer du sedan önskad logik för rekommendationer:

* Objekt med liknande attribut
* De senast visade objekten i en viss kategori
* Kunder som köpte den här artikeln köpte även dessa artiklar
* Ett anpassat attribut

Ut ur lådan, [!DNL Target] innehåller en portfölj med algoritmer.

![Portfolio i algoritmbild](/help/main/c-recommendations/assets/intro-15.png)

* **Popularitetsbaserade algoritmer** inkluderar Mest visade och populära säljare.
* **Innehållsbaserade algoritmer** inkludera Likhet för innehåll.
* **Objektbaserade filteralgoritmer för samarbete** inkludera Visad/Visad, Visad/Köpt och Köpt/Köpt. Observera att&quot;köpt&quot; kan vara vilken konvertering som helst.
* **Personaliserade algoritmer** innehåller nyligen visade, platstillhörighet och profilförbättrad samarbetsfiltrering.
* **Använd egna algoritmer** gör att du kan använda egna algoritmer.

### Affärsregler online

Det sista steget är att tillämpa onlineaffärsregler. Här kan du ge dina algoritmer domänkunskap och aktuell kontext baserat på vad besökaren gör på din digitala egendom.

![Illustration av onlineregler](/help/main/c-recommendations/assets/intro-18.png)

I innehållskontexten kanske du vill utesluta filmer som besökaren tidigare har tittat på, rekommendera filmer av samma regissör eller lyfta filmer i samma genre. Inom detaljhandeln kanske du vill utesluta produkter som inte finns i lager, visa artiklar i ett prisintervall på 5 till 500 dollar eller lyfta artiklar från samma varumärke.

## Demo

När du har slutfört de uppgifter som illustreras i rekommendationstratten som beskrivs ovan, får du din slutgiltiga rekommendation. Titta på en produktdemonstration inuti [!DNL Target], börjar filmen klockan 21:00 i *Adobe Target Basics Webinar*, länkat till nedan.

## Adobe [!DNL Target] Basics Webinar: Introduktion till Recommendations {#intro-to-recs}

[Introduktion till Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
