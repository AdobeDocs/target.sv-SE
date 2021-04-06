---
keywords: Översikt och referens;aktivitetstyper;introduktion
description: Lär dig grunderna i Adobe Target. I den här artikeln beskrivs Target, dess aktivitetstyper och andra funktioner.
title: Hur använder jag Target?
feature: Översikt
exl-id: c9555d79-d505-41ff-ba4b-ab94793f9efa
translation-type: tm+mt
source-git-commit: 094756ac64e2740e81834fde4b07d4b643ac39b9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Målgrupper

Information om viktiga begrepp som hjälper dig att förstå funktionerna och funktionerna i [!DNL Adobe Target].

## Aktiviteter och tester {#section_BEA0A0C51A8847579B566060206DE7E8}

En aktivitet avgör vilka upplevelser en besökare kan stöta på.

Du kan till exempel utforma en aktivitet som testar två olika landningssidor, en som visar information om damernas sommarskor och en som markerar mer allmänna sommarkläder. Aktiviteten avgör vilka villkor som styr när var och en av dessa landningssidor visas och vilka mått som avgör vilken sida som blir mest framgångsrik. Aktiviteten är konfigurerad att starta och avsluta när specifika villkor uppfylls. Dessa villkor kan vara att starta och avsluta aktiviteten mellan specifika datum eller att starta när aktiviteten har godkänts och att sluta när den har inaktiverats.

Planera noggrant när du utformar en aktivitet. Bestäm när aktiviteten startar och hur länge den varar. Ange sedan era erbjudanden och tilldela målgrupper till var och en av dem.

Målet innehåller flera aktivitetstyper. Följande tabell innehåller en översikt över varje aktivitetstyp med länkar som hjälper dig att lära dig mer. För att du bättre ska kunna välja den bästa aktivitetstypen har Target-teamet också skapat [Adobe Target aktivitetshandbok](/help/c-activities/target-activities-guide.md).

| Typ av aktivitet | Beskrivning |
|--- |--- |
| [A/B-test](/help/c-activities/t-test-ab/test-ab.md) | A/B-tester jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som förbättrar konverteringen under en fördefinierad testperiod.<br>**Obs!** Du kan nu inkludera  [rekommendationer i A/B-testaktiviteter](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Med Automatisk tilldelning identifieras en vinnare bland två eller fler upplevelser och fler kunder tilldelas automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.<br>**Obs!** Du kan nu inkludera  [rekommendationer i Automatisk allokering av aktiviteter](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Auto-](/help/c-activities/auto-target/auto-target-to-optimize.md)<br>![TargetPremium](/help/assets/premium.png) | Auto Target använder avancerad maskininlärning för att identifiera flera högpresterande marknadsföringsdefinierade upplevelser. AutoTarget-aktiviteter ger varje besökare den mest skräddarsydda upplevelsen baserat på deras individuella kundprofil och beteendet hos tidigare besökare med liknande profiler, för att personalisera innehåll och driva konverteringar.<br>**Obs!** Du kan nu inkludera  [rekommendationer i Automatisk målaktivitet](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Använda analysdata](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md)  (A4T) | Du kan konfigurera en aktivitet så att [!DNL Adobe Analytics] används som rapportkälla. Den här aktivitetstypen kräver att du länkar ditt [!DNL Adobe Experience Cloud]-konto till både [!DNL Analytics] och [!DNL Target]. |
| [Multivariata tester](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | Med multivariata tester (MVT) jämförs kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp och det element som har störst påverkan på aktivitetens framgång identifieras. |
| [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) | Experience Targeting (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.<br>**Obs!** Du kan nu inkludera  [rekommendationer i Experience Targeting-aktiviteter](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Automatiserad ](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![personaliseringTarget Premium](/help/assets/premium.png) | Automated Personalization (AP) kombinerar erbjudanden och meddelanden och använder avancerad maskininlärning för att matcha olika varianter av varje besökare baserat på deras individuella kundprofil, för att personalisera innehåll och driva konverteringar. |
| [](/help/c-recommendations/recommendations.md)<br>![RecommendationsTarget Premium](/help/assets/premium.png) | En rekommendation avgör hur en produkt föreslås för en webbplatsanvändare, beroende på den användarens aktiviteter på webbplatsen.<br>Du kanske till exempel vill uppmuntra personer som köper en ryggsäck att överväga att köpa vandrande skor och trikåpoler. Du kan skapa en rekommendation som visar objekt som ofta köpts tillsammans med hjälp av algoritmen&quot;Personer som köpte det här&quot;. Eller så kanske du vill uppmuntra besökarna att spendera mer tid på din mediewebbplats genom att rekommendera liknande video som den de tittar på, med algoritmen&quot;Personer som såg det här&quot;.<br>**Obs!** Du kan nu inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatisk målning) och XT-aktiviteter (Experience Targeting). Se [Recommendations som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md). |

## Platser {#section_F18FBF1ED23340ED9F39C51971A4E874}

I första hand är en plats en sida på webbplatsen. Det kan även avse en plats i en mobilapp, ett e-postmeddelande eller någon annan plats där du kör en optimering.

Platser är viktiga för aktiviteter och upplevelser. Du avgör om någon plats kan göra något, båda eller inget av följande:

* Visa och byt innehåll för besökare.
* Logga besökarbeteende.

I [!DNL Target Standard] kan en plats vara vilket element som helst på en sida, förutsatt att sidan innehåller en enda kodrad som aktiverar [!DNL Target] i `<head>`-avsnittet på varje sida som du vill spåra. Den här kodraden anropar de JavaScript-bibliotek som behövs för att samla in information och leverera riktade upplevelser till besökarna.

Platserna kombineras med målgrupperna för att ge ett nästan oändligt antal alternativ för målgruppsinformation till era kunder. Om en besökare aldrig har besökt webbplatsen tidigare kan du visa en rabattkupong för nya kunder. På samma sätt kan sidan ändras så att den visar erbjudanden som är mer optimerade för återkommande kunder.

Du kan också använda platser för att spåra besökarens förlopp på webbplatsen. Du kan också använda platser för att spåra om besökaren har fyllt i ett visst mått, som att lägga till en artikel i kundvagnen eller slutföra ett köp.

## Erfarenheter och siddesign {#section_B806FB752EC1470784755C1EB3D4AC70}

En upplevelse, som ibland kallas recept, definierar innehållet som visas på sidan och andra sidelement, till exempel länkar.

En upplevelse avgör vilket erbjudande som visas på en viss plats när specifika villkor för målinriktning uppfylls. Erfarenheten avgör till exempel att när en besökare besöker er webbplats visas ett erbjudande om tvådagars frakt högst upp på sidan. Erfarenheten avgör också att när en förstagångsbesökare tittar på sidan visas 10 % rabatt på samma plats.

En upplevelse består av erbjudanden, bildresurser eller andra HTML-element (t.ex. länkar) som visas på sidan för att hjälpa besökaren att uppnå önskat resultat. [!DNL Target] kombinerar platser, erbjudanden och upplevelser för att avgöra vilket innehåll som visas på din webbplats under ett visst test.

En upplevelse kan också vara en annan siddesign. En upplevelse kan till exempel ha en uppsättning länkar längst upp på sidan, där en annan upplevelse har olika länkar eller samma länkar ordnade i en annan ordning. Du kanske vill testa om en bild ger mer lyft än en annan, eller om det är mer sannolikt att en annons klickas i sidans övre del eller på en annan plats.

[!DNL Target] optimerar upplevelserna för var och en av era besökare över alla era digitala kontaktytor och testar olika upplevelser för att avgöra vilka som blir mest framgångsrika. Genom att noggrant planera målgruppsanpassningen av upplevelserna kan ni se till att besökarna på webbplatsen ser de mest relevanta erbjudandena på rätt platser på sidan, vilket förbättrar era chanser att besöka webbplatsen.

## Erbjudanden {#section_973D4CC4CEB44711BBB9A21BF74B89E9}

Ett erbjudande är det innehåll som visas på dina webbsidor under kampanjer eller aktiviteter.

När du testar dina webbsidor mäter du framgången för varje upplevelse med olika erbjudanden på dina platser.

Ett erbjudande kan innehålla olika typer av innehåll, bland annat:

* Bild
* Text
* HTML
* Länk
* Knapp

En webbsida kan t.ex. visa ett av två erbjudanden, beroende på om besökaren har besökt din webbplats tidigare.

En *upplevelse* avgör vilket innehåll som visas när vissa villkor uppfylls.

## Målgrupper {#section_3F32DA46BDF947878DD79DBB97040D01}

Optimera målanpassat innehåll för aktivitetsdeltagare som uppfyller specifika kriterier.

Målgrupperna definierar målet för din aktivitet och används var som helst där målinriktning finns tillgänglig.

[!DNL Target] målgrupper är en definierad uppsättning besökskriterier. Erbjudandena kan riktas till specifika målgrupper (eller segment). Det är bara besökare som tillhör den målgruppen som ser upplevelsen som är riktad till dem.

Du kan till exempel rikta en aktivitet mot en målgrupp som består av besökare som använder en viss webbläsare eller ett visst operativsystem.

Din aktivitet kan också vara inriktad på besökare från en geografisk region eller personer som kommer åt sidan från en viss sökmotor.

Publiker kan sparas för återanvändning i flera aktiviteter eller skapas för en viss aktivitet.

| Målgruppstyp | Beskrivning |
|--- |--- |
| Återanvändbara målgrupper | Återanvändbara målgrupper kan väljas för alla aktiviteter. Om du ändrar en av dessa målgrupper ändras den för alla aktiviteter som använder den. |
| Egna segment | Anpassade segment (kallas även kampanjspecifika segment) är specifika för en kampanj i Target Classic. De skapas som en del av kampanjen och kan inte återanvändas i andra kampanjer. |
| Delade målgrupper | Målgrupper kan delas mellan [!DNL Adobe Experience Cloud]-lösningar. Se [Publiker](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) för exempel. |

Mer information om hur besökarprofilen spårar information om besökare på platsen finns i [Besökarprofiler](/help/c-target/c-visitor-profile/visitor-profile.md#concept_5E53D1A6DF224D7BAE76F4AE390B9DA1).

## Utbildningsvideor:

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetstyper (9:03) ![Översikt](/help/assets/overview.png)

I den här videon förklaras aktivitetstyperna som är tillgängliga i [!DNL Target Standard/Premium].

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Använda målgrupper i Adobe Target (6:21) ![Översikt](/help/assets/overview.png)

I den här videon förklaras hur du använder målgrupper i [!DNL Target Standard/Premium].

* Förklara termen&quot;Målgrupp&quot;
* Förklara de två sätt på vilka målgrupper används för optimering
* Hitta målgrupper i publiklistan
* Rikta en aktivitet mot en målgrupp
* Använd målgrupper för passiv rapportering i en aktivitet

>[!VIDEO](https://video.tv.adobe.com/v/17398)
