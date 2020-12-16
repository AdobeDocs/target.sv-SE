---
keywords: activities list;activities;activity;activity types;edit activity;activity actions;activity attribute;activity list filter;activity limitations;personalize;personalization
description: Med funktionerna i Adobe Target kan ni personalisera innehåll efter specifika målgrupper och testa siddesign
title: Med Adobe Target kan ni personalisera innehåll efter specifika målgrupper och testa siddesign.
feature: activities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '2069'
ht-degree: 1%

---


# Aktiviteter{#activities}

Med Adobe Target kan ni personalisera innehåll efter specifika målgrupper och testa siddesign.

Du kan till exempel utforma en aktivitet som testar två olika landningssidor, en som markerar information om damernas sommarskor och en annan landningssida som markerar mer allmänna sommarkläder. Aktiviteten avgör vilka villkor som styr när var och en av dessa landningssidor visas och vilka mått som avgör vilken sida som blir mest framgångsrik. Aktiviteten är konfigurerad att starta och avsluta när vissa villkor uppfylls, till exempel mellan specifika datum, eller att starta när aktiviteten har godkänts och att sluta när den har inaktiverats.

När du utformar en aktivitet bör du planera noggrant. Bestäm när aktiviteten ska starta och hur länge den ska vara. Ange sedan era erbjudanden och tilldela målgrupper till var och en av dem.

## Typ av aktivitet

Målet innehåller flera aktivitetstyper. Följande tabell innehåller en översikt över varje aktivitetstyp med länkar som hjälper dig att lära dig mer. För att du bättre ska kunna välja den bästa aktivitetstypen har vi även skapat [Adobe Target aktivitetsguide](/help/c-activities/target-activities-guide.md).

| Typ av aktivitet | Beskrivning |
|--- |--- |
| [A/B-test](/help/c-activities/t-test-ab/test-ab.md) | A/B-tester jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som förbättrar konverteringen under en fördefinierad testperiod.<br>**Obs!** Du kan nu inkludera  [rekommendationer i A/B-testaktiviteter](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Automatisk tilldelning identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.<br>**Obs!** Du kan nu inkludera  [rekommendationer i Automatisk allokering av aktiviteter](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Auto-](/help/c-activities/auto-target/auto-target-to-optimize.md)<br>![TargetPremium](/help/assets/premium.png) | Auto Target använder avancerad maskininlärning för att identifiera flera högpresterande marknadsföringsdefinierade upplevelser och levererar den mest anpassade upplevelsen till varje besökare baserat på deras individuella kundprofil och beteendet hos tidigare besökare med liknande profiler, för att personalisera innehåll och driva konverteringar.<br>**Obs!** Du kan nu inkludera  [rekommendationer i Automatisk målaktivitet](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en sådan funktion. Den kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Använda analysdata](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md)  (A4T) | Du kan konfigurera en aktivitet så att [!DNL Adobe Analytics] används som rapportkälla. Den här aktivitetstypen kräver att du länkar ditt [!DNL Adobe Experience Cloud]-konto till både [!DNL Analytics] och [!DNL Target]. |
| [Multivariata tester](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | Med multivariata tester (MVT) jämförs kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp och det element som har störst påverkan på aktivitetens framgång identifieras. |
| [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) | Experience Targeting (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.<br>**Obs!** Du kan nu inkludera  [rekommendationer i Experience Targeting-aktiviteter](/help/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/c-intro/intro.md#premium). |
| [Automatiserad ](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![personaliseringTarget Premium](/help/assets/premium.png) | Automated Personalization (AP) kombinerar erbjudanden och meddelanden och använder avancerad maskininlärning för att matcha olika varianter av varje besökare baserat på deras individuella kundprofil, för att personalisera innehåll och driva konverteringar. |
| [](/help/c-recommendations/recommendations.md)<br>![RecommendationsTarget Premium](/help/assets/premium.png) | En rekommendation avgör hur en produkt föreslås för en webbplatsanvändare, beroende på den användarens aktiviteter på webbplatsen.<br>Du kanske till exempel vill uppmuntra personer som köper en ryggsäck att överväga att köpa vandrande skor och trikåpoler. Du kan skapa en rekommendation som visar objekt som ofta köpts tillsammans med hjälp av algoritmen&quot;Personer som köpte det här&quot;. Eller så kanske du vill uppmuntra besökarna att spendera mer tid på din mediewebbplats genom att rekommendera liknande video som den de tittar på, med algoritmen&quot;Personer som såg det här&quot;.<br>**Obs!** Du kan nu inkludera rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatisk målning) och XT-aktiviteter (Experience Targeting). Se [Recommendations som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md). |

## Aktivitetslista {#section_DE8E2DB30D534962A931EF8BB48240F5}

Listan [!UICONTROL Activities] är standardvy när du öppnar [!DNL Target]. Du kan skapa nya aktiviteter från den här sidan och hantera befintliga aktiviteter.

Du kan även visa listan [!UICONTROL Activities] genom att klicka på fliken [!UICONTROL Activities] högst upp i användargränssnittet för [!DNL Target].

![Aktivitetslista](/help/c-activities/assets/activities-list.png)

Listan Verksamheter innehåller en översikt över alla aktiviteter:

| Element | Beskrivning |
|--- |--- |
| Typ | Aktivitetstypen, till exempel A/B eller MVT. |
| Namn | Namnet på aktiviteten. |
| URL | URL:en visas med ljusare text under namnet.<br>URL:en för aktiviteten identifierar var aktiviteten visas. Detta hjälper dig att snabbt identifiera en aktivitet och avgöra om en viss sida redan har ett test som körs på den.<br>Om ett test körs på flera URL-adresser, visar en länk hur många fler URL-adresser som används. Klicka på länken för att visa den fullständiga listan med URL:er för den aktiviteten.<br>Du kan söka baserat på URL. Använd listrutan bredvid sökrutan och välj [!UICONTROL Search URL]. |
| Status | Aktivitetens status kan vara något av följande:<ul><li>**Live**: Aktiviteten körs.</li><li>**Utkast**: Aktivitetsinställningarna har startats men aktiviteten är inte klar att köras än.</li><li>**Schemalagd**: Aktiviteten är klar att aktiveras när angivet startdatum och angiven starttid kommer.</li><li>**Inaktiv**: Aktiviteten har pausats eller inaktiverats.</li><li>**Synkroniserar**: Aktiviteten har sparats och synkroniseras till målleveransnätverket.</li><li>**Avslutat**: Aktivitetens angivna slutdatum och sluttid har nåtts och aktiviteten betjänas inte längre.</li><li>**Arkiverad**: Aktiviteten har arkiverats. Du kan aktivera en arkiverad aktivitet och använda den igen.</li></ul>**Obs**: När du utför vissa åtgärder, t.ex. aktiverar en aktivitet utanför användargränssnittet med API-metoder, kan det ta upp till tio minuter innan uppdateringen skickas till användargränssnittet. |
| Källa | Visar var aktiviteten skapades:<ul><li>Adobe Target</li><li>Adobe Target Classic</li><li>Adobe Experience Manager (AEM)</li><li>Adobe mobiltjänster (AMS)</li></ul> |
| Egenskap | Visar [egenskapen](/help/administrating-target/c-user-management/property-channel/property-channel.md) för aktiviteten. |
| Uppskattat lyft i intäkt | Visar den förväntade intäktsökningen om 100 % av publiken ser den vinnande upplevelsen.<br>Beräknas med följande formel:<br>`(<winning experience> - <control experience>)*<total number of visitors>`<br>Talet avrundas till en decimal, max, om det kondenserade formuläret bara har en siffra före decimaltalet. Till exempel: 1,6 miljoner dollar, 60 000 dollar, 900 dollar, 8,5 000 dollar, 205 000 dollar<br>Denna kolumn visar &quot;—&quot; för aktiviteter som inte har tillräckligt med data för att ringa till ett vinnarprogram eller som inte har någon kostnadsberäkning.<br>Mer information finns i  [Beräkna Lyft i ](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) intäkter. |
| Senast uppdaterad | Det datum då aktiviteten senast uppdaterades och av vem. |

För musen över en aktivitet för att se tillgängliga åtgärder.

![Åtgärder för hovring i aktivitetslista](/help/c-activities/assets/activities_list_hover.png)

Följande åtgärder är tillgängliga (beroende på dina behörigheter):

| Åtgärd | Beskrivning |
| --- | --- |
| Redigera | Ändra aktiviteten. Alla aktiviteter kan redigeras.<br>Mer information om olika sätt att redigera aktiviteter finns i  [Redigera en aktivitet eller Spara som utkast](/help/c-activities/edit-activity.md). |
| Inaktivera | Stoppa en aktiv eller schemalagd aktivitet. En inaktiverad kampanj kan återaktiveras eller arkiveras<br>Om du inaktiverar eller arkiverar en aktivitet och sedan återaktiverar den, fortsätter en besökare att vara en del av den aktiviteten efter omaktiveringen om de fanns i den innan den inaktiverades eller arkiverades. Konverteringsvärden som registreras under tiden mellan de två händelserna kommer inte att tillskrivas den aktiviteten. |
| Aktivera | Starta en inaktiv eller klar aktivitet. |
| Arkiv | Skicka aktiviteten till arkivet. Som standard visas inte längre arkiverade aktiviteter i aktivitetslistan. Ändra filtret för aktivitetslistan så att den innehåller arkiverade aktiviteter för att se dem. Du kan aktivera en arkiverad aktivitet och använda den igen.<br>Om du inaktiverar eller arkiverar en aktivitet och sedan återaktiverar den, fortsätter besökaren att vara en del av den aktiviteten efter omaktiveringen om de fanns i den innan den inaktiverades eller arkiverades. Konverteringsvärden som registreras under tiden mellan de två händelserna kommer inte att tillskrivas den aktiviteten. |
| Kopiera | Kopiera en aktivitet. Alla aktiviteter kan kopieras. När du kopierar en aktivitet skapas en ny aktivitet med samma namn, som läggs till med &quot;Kopiera&quot;. Ett test med namnet&quot;Browser Offers&quot; kopieras till exempel till&quot;Browser Offers Copy&quot;.<br>Visuella erbjudanden kopieras med aktiviteten. Du kan redigera erbjudandena i kopian utan att det påverkar den ursprungliga aktiviteten. Det enda undantaget är sparade erbjudanden och bilder i mappen Innehåll/resurser. |
| Ta bort | Ta bort ett utkast eller en aktivitet.<BR>**OBS**: Borttagna aktiviteter kan inte återställas. Använd åtgärden [!UICONTROL Archive] om du inte är helt säker på att du aldrig behöver den här aktiviteten igen. Du kan sedan återaktivera aktiviteten om det behövs. |

Observera följande information om aktivitetslistan:

* Arkiverade och avslutade aktiviteter visas inte i listan [!UICONTROL Activities]. Om du vill visa de här aktiviteterna filtrerar du dem med de avancerade filterinställningarna på den vänstra listen.
* När en aktivitet som ursprungligen skapades i [!DNL Target Classic] inaktiveras eller tas bort tas den bort från [!DNL Target Standard/Premium]. Borttagna aktiviteter som ursprungligen skapades i [!DNL Target Classic] skickas inte till mappen [!UICONTROL Archive] i [!DNL Target Standard/Premium]. Funktionen för arkiverade mappar gäller endast aktiviteter som skapats i [!DNL Target Standard/Premium].
* Alla aktivitetstyper förutom [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] ger dig möjlighet att använda antingen [!DNL Target] eller [!DNL Adobe Analytics] som datakälla. [!UICONTROL AP],  [!UICONTROL Auto-Allocate]och  [!UICONTROL Auto-Target] ** använder alltid  [!DNL Target] data.
* Verksamheter är tillgängliga i flera kanaler:

   * Webbplatser och mobilsajter
   * Internetanslutna skärmar och enheter, inklusive kioskdatorer och uttagsautomater
   * E-post och andra förvärvskanaler eller partnersajter
   * Mobilappar
   * Var du än är kan du leverera taggat innehåll

## Sortera och filtrera aktivitetslistan {#section_41DAD479FFF740E2BB67BF4825955670}

Som standard sorteras listan efter det datum då aktiviteten senast ändrades, med det senaste överst. Det finns dock flera filtreringsalternativ som du kan använda för att anpassa listan så att den visar de aktiviteter du vill se.

### Sök {#search-heading}

Använd sökfältet för att söka efter aktiviteter som matchar sökvillkoren.

![Aktivitetssökning](/help/c-activities/assets/activities_search_new.png)

Sökfältet innehåller en listruta där du kan begränsa sökningen genom att ange ett av följande sökfilter: [!UICONTROL Activity Name] och [!UICONTROL URL].

### Filter för aktivitetslista

Du kan avgöra vilka aktiviteter som visas i aktivitetslistan genom att välja listfilter.

![Filtrera aktiviteter efter typ](/help/c-activities/assets/activities_filters_new.png)

Du kan filtrera efter följande alternativ. Om inget är markerat i varje kategori är standardvärdet Alla.

| Filterkategori | Filter |
|--- |--- |
| Typ | A/B-test: [Manuell](/help/c-activities/t-test-ab/test-ab.md), [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) och [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md).<br>[Automatiserad ](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>[personaliseringUpplev ](/help/c-activities/t-experience-target/experience-target.md)<br>[målanpassningMultivariata ](/help/c-activities/c-multivariate-testing/multivariate-testing.md)<br>[testrekommendationer](/help/c-recommendations/recommendations.md) |
| Status | Live<br>Utkast<br>Schemalagt<br>Inaktivt<br>Synkronisering<br>Avslutat<br>Arkiverat |
| Rapporteringskälla | Mål<br>Analys |
| Experience Composer | Visual<br>Formulärbaserad |
| Mätningstyp | Konvertering<br>Intäkter<br>Åtaganden |
| Aktivitetskälla | Adobe Target<br>Adobe Target Classic<br>Adobe Experience Manager<br>Adobe Mobile Services |

### Sortera efter aktivitetsattribut

Klicka på en av följande rubriker för att växla om aktiviteterna visas i stigande eller fallande ordning enligt den valda rubriken.

* Aktivitetsnamn
* Typ av aktivitet

![Aktivitetslista stigande ordning](/help/c-activities/assets/activities_list_ascending.png)

## Tips och tricks {#section_F77F30A246A14B538D9363B7F3639F97}

Få ut mesta möjliga av Adobe Target genom att lära dig mer om olika funktioner och se varför du bör testa dem. Tips- och tricks-funktionen innehåller länkar till videoklipp, användningsfall, bloggar, dokumentation och mycket annat.

Tips- och tricks-funktionen visas regelbundet på aktivitetslistsidan. När du har läst eller stängt ett tips visas det inte igen förrän nästa tips är tillgängligt. Du kan även inaktivera visningen av alla tips genom att klicka på hjälpikonen > [!UICONTROL Disable Tip of the Day].

![Inaktivera dagens tips](/help/c-activities/assets/tip-disable-new.png)

## Begränsningar {#section_049D4684403A4E07B998067EB8E9BE56}

Varje Target-aktivitet har följande innehållsbegränsningar:

| Objekt | Gräns |
|--- |--- |
| Unika väljare | 300 Om en väljare upprepas med en annan upplevelse räknas den en gång. Om det upprepas med samma erfarenhet räknas det dock igen. |
| Erbjudanden för varje upplevelse | 350 |
| Klicka på spåra väljare i mätvärden | 50 |
| Måttfält | 50 |
| Målgrupper och platser | Kombinationen av målgrupper och platser (mbox) får inte vara större än 50. |

Det går inte att spara aktiviteten om du överskrider någon av dessa gränser.

Om du ökar antalet av dessa objekt i din aktivitet ökar även tiden det tar att synkronisera aktiviteten över målet.

Ytterligare begränsningar för Visual Experience Composer finns i [Gränser för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attribut som har importerats till Target för aktiviteter som har uppdaterats utanför mål {#section_802B0D174E6A44E1A96F404CA81AAE44}

Om aktiviteter som skapats i [!DNL Target] uppdateras utanför [!DNL Target] (till exempel via Adobe I/O) importeras följande aktivitetsattribut tillbaka till [!DNL Target]:

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

Det här importjobbet körs när aktivitetssidan öppnas, med en maximal fördröjning på tio minuter. (KB-1526)

## Utbildningsvideor {#section_BE80D13A2E81460C885F902010E1AD87}

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetstyper (9:03) ![Översikt](/help/assets/overview.png)

I den här videon förklaras aktivitetstyperna som är tillgängliga i [!DNL Target Standard/Premium].

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Hantera aktiviteter (5:55) ![Översikt](/help/assets/overview.png)

I den här videon förklaras hur du använder aktivitetslistan för att hantera aktiviteter.

* Definiera termen *aktivitet*
* Sök efter aktiviteter i aktivitetslistan
* Redigera, inaktivera, kopiera och ta bort aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/18550)
