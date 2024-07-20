---
keywords: aktivitetslista;aktiviteter;aktivitet;aktivitetstyper;redigera aktivitet;aktivitetsåtgärder;aktivitetsattribut;aktivitetslista filter;aktivitetsbegränsningar;anpassa;personalisering
description: Lär dig hur du med aktiviteter i  [!DNL Target] kan anpassa innehåll efter specifika målgrupper och testa siddesign.
title: Hur kan jag personalisera innehåll och testa siddesign med  [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: be63fa4c89f229e3f4566cb400e1268d2cdf08d2
workflow-type: tm+mt
source-wordcount: '2290'
ht-degree: 0%

---

# Verksamhet

Med aktiviteter i [!DNL Adobe Target] kan du anpassa innehåll efter specifika målgrupper och testa siddesign.

Du kan till exempel utforma en aktivitet som testar två olika landningssidor, en som markerar information om damernas sommarskor och en annan landningssida som markerar mer allmänna sommarkläder. Aktiviteten avgör vilka villkor som styr när var och en av dessa landningssidor visas och vilka mått som avgör vilken sida som blir mest framgångsrik. Aktiviteten är konfigurerad att starta och avsluta när vissa villkor uppfylls, till exempel mellan specifika datum, eller att starta när aktiviteten har godkänts och att sluta när den har inaktiverats.

När du utformar en aktivitet bör du planera noggrant. Bestäm när aktiviteten startar och hur länge den varar. Ange sedan era erbjudanden och tilldela målgrupper till var och en av dem.

## Aktivitetslista {#section_DE8E2DB30D534962A931EF8BB48240F5}

Listan [!UICONTROL Activities] är standardvy när du öppnar [!DNL Target]. Du kan skapa aktiviteter från den här sidan och hantera befintliga aktiviteter.

Du kan också visa listan [!UICONTROL Activities] genom att klicka på fliken [!UICONTROL Activities] högst upp i användargränssnittet i [!DNL Target].

![Aktivitetslista](/help/main/c-activities/assets/activities-list-new.png)

Listan [!UICONTROL Activities] innehåller en översikt över alla aktiviteter och du kan utföra olika åtgärder:

| Element | Beskrivning |
|--- |--- |
| Vänster navigeringsspår | Växla mellan dina sparade eller aktiva aktiviteter och misslyckade eller [utkast till aktiviteter](/help/main/c-activities/edit-activity.md). |
| ikonen [!UICONTROL Show filters]<P>![Ikonen Visa filter](/help/main/c-activities/assets/show-filters-icon.png) | Du kan få åtkomst till filter genom att klicka på ikonen **[!UICONTROL Show Filters]** uppe i listan.<P>Mer information finns i [Använda filter i aktivitetslistan](#filters) nedan. |
| Sökruta | Hitta snabbt en aktivitet eller minska antalet aktiviteter som visas i listan [!UICONTROL Activity]. Du kan söka efter [!UICONTROL Name], [!UICONTROL URL] eller [!UICONTROL ID]. |
| [!UICONTROL Create Activity] | Skapa en aktivitet. Mer information om hur du skapar de olika aktivitetstyperna finns i: <ul><li>[Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Skapa en automatiskt fördelad aktivitet](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Skapa en Automatisk målaktivitet](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Skapa en Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Skapa en Experience Targeting-aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Skapa ett multivariattest](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Skapa en Recommendations-aktivitet](/help/main/c-recommendations/recommendations.md)</li></ul>Mer information om de olika typerna finns i [Aktivitetstyper](#types) nedan. |
| [!UICONTROL Create mobile preview link]<P>![Menyn Fler åtgärder](/help/main/c-activities/assets/icon-create-mobile-link.png) | Använd [länkar för förhandsgranskning av mobiler](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html) för att utföra enkla QA-åtgärder från början till slut för mobilappsaktiviteter.<P>Klicka på ikonen **Fler alternativ** (den lodräta ellipsen), markera **Skapa länk för förhandsvisning av mobila enheter** och välj sedan de aktiviteter du vill testa på mobila enheter. |
| Anpassa tabell<P>![Ikonen Anpassa tabell](/help/main/c-activities/assets/icon-customize-table.png) | Ändra vilka kolumner som ska visas i listan [!UICONTROL Activity] genom att klicka på ikonen **[!UICONTROL Customize Table]** längst upp till höger i tabellen och sedan markera eller avmarkera de kolumner du vill använda.<P>Ändringarna tillämpas på ditt konto och förblir aktiva även efter att du loggat ut från [!DNL Target]. |
| Kryssrutor för gruppåtgärd | Utför massåtgärder för alla aktiviteter eller för valda aktiviteter.<P>En lista med tillgängliga åtgärder (beroende på dina behörigheter och aktivitetsstatus) finns i [Utför snabbåtgärder](#quick-actions) nedan. |
| [!UICONTROL Type] | Aktivitetstypen. I kolumnen [!UICONTROL Type] kan du snabbt identifiera varje aktivitet efter typ. <ul><li>AB-M: manuell [!UICONTROL A/B Test]</li><li>AB-AA: [!UICONTROL Auto-Allocate]</li><li>AB-AT: [!UICONTROL Auto-Target]</li><li>AP: [!UICONTROL Automated Personalization]</li><li>XT: [!UICONTROL Experience Targeting]</li><li>MVT: [!UICONTROL Multivariate Test]</li><li>REC: [!UICONTROL Recommendations]</li></ul>Mer information om de olika typerna finns i [Aktivitetstyper](#types) nedan. |
| [!UICONTROL Name] | Namnet på aktiviteten. Klicka på ett aktivitetsnamn för att visa aktivitetens [!UICONTROL Overview]-sida. <P>Klicka på ikonen **[!UICONTROL Quick Info]** bredvid varje aktivitetsnamn om du vill visa mer information om aktiviteten på ett popup-kort.<p>Klicka på ikonen **[!UICONTROL More actions]** (den vågräta ellipsen) bredvid varje aktivitetsnamn för att öppna en meny där du kan utföra snabbåtgärder för en aktivitet. Följande åtgärder är tillgängliga (beroende på dina behörigheter och aktivitetsstatus): [!UICONTROL Edit], [!UICONTROL Activate], [!UICONTROL Deactivate], [!UICONTROL Copy], [!UICONTROL Delete] och [!UICONTROL Archive]. Mer information om de olika åtgärderna finns i [Utför snabbåtgärder](#quick-actions) nedan.<P>Klicka på tabellrubriken om du vill sortera listan i stigande eller fallande ordning efter namn. |
| [!UICONTROL Status] | Aktivitetens status kan vara något av följande:<ul><li>**Live**: Aktiviteten körs.</li><li>**Utkast**: Aktivitetsinställningarna har startats men aktiviteten är i [utkastläge](/help/main/c-activities/edit-activity.md) och är inte klar att köras än.</li><li>**Schemalagd**: Aktiviteten är klar att aktiveras när det angivna startdatumet och den angivna starttiden kommer.</li><li>**Inaktiv**: Aktiviteten har pausats eller inaktiverats.</li><li>**Synkroniserar**: Aktiviteten har sparats och synkroniseras med leveransnätverket [!DNL Target].</li><li>**Slutet**: Aktivitetens angivna slutdatum och sluttid har uppnåtts och aktiviteten hanteras inte längre.</li><li>**Arkiverad**: Aktiviteten har arkiverats. Du kan aktivera en arkiverad aktivitet och använda den igen.</li></ul>**Obs!** När du utför vissa åtgärder, t.ex. aktiverar en aktivitet utanför [!DNL Target]-gränssnittet med API-metoder, kan det ta upp till tio minuter att uppdatera till [!DNL Target]-gränssnittet. |
| [!UICONTROL Last Updated] | Datum och tid när aktiviteten senast uppdaterades och av vem.<P>Klicka på tabellrubriken om du vill sortera listan i stigande eller fallande ordning efter datum. |
| [!UICONTROL Priority] | Aktivitetens prioritet.<P>Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.<P>Beroende på dina [inställningar](/help/main/administrating-target/reporting.md) varierar användargränssnittet för [!DNL Target] och alternativen för [!UICONTROL Priority]. Du kan använda de äldre inställningarna Låg, Medium eller Hög, eller aktivera finjusterade prioriteringar mellan 0 och 999. |
| [!UICONTROL Property] | Visar [egenskapen](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) för aktiviteten.<P>Enterprise-användarbehörigheter är en [Target Premium](/help/main/c-intro/intro.md#premium)-funktion. |
| [!UICONTROL Estimated Lift in Revenue] | Visar den förväntade intäktsökningen om 100 % av publiken ser den vinnande upplevelsen.<P>Beräknas med följande formel:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>Talet avrundas till en decimal, max, om det komprimerade formuläret bara har en siffra före decimaltalet. Exempel: $1,6 MB, $60 K, $900, $8,5 K, $205 K<P>I den här kolumnen visas &quot;—&quot; för aktiviteter som inte har tillräckligt med data för att ringa till en vinnarshow eller som inte har en kostnadsberäkning.<P>Mer information finns i [Beräknar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| [!UICONTROL Source] | Visar var aktiviteten skapades: [!DNL Adobe Target], [Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html) eller [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Location] | URL:en för aktiviteten identifierar var aktiviteten visas. Med den här kolumnen kan du snabbt identifiera en aktivitet och avgöra om en viss sida redan har en aktivitet som körs på den.<P>Om en aktivitet körs på flera URL-adresser, visar en länk hur många fler URL-adresser som används. Klicka på länken för att visa den fullständiga listan med URL:er för den aktiviteten.<P>Du kan söka baserat på URL. Använd listrutan bredvid sökrutan och välj [!UICONTROL URL]. |
| Upphovsman | Namnet på den person som skapade aktiviteten. |
| [!UICONTROL Decisioning Method] | Beslutsmetoden som används i varje aktivitet: [Serversidan](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html) eller [Klientsidan](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## Typ av aktivitet {#types}

[!DNL Target] innehåller flera aktivitetstyper. Följande tabell innehåller en översikt över varje aktivitetstyp med länkar som hjälper dig att lära dig mer. För att du bättre ska kunna välja den bästa aktivitetstypen har vi även skapat [Adobe Target aktivitetshandbok](/help/main/c-activities/target-activities-guide.md).

| Typ av aktivitet | Beskrivning |
|--- |--- |
| [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) | A/B-tester jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som optimerar konverteringarna under en fördefinierad testperiod. |
| [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate], en typ av A/B-test, identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig. |
| [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | Auto-Target, som är en typ av A/B-test, använder avancerad maskininlärning för att identifiera flera högpresterande marknadsföringsdefinierade upplevelser och levererar den mest anpassade upplevelsen till varje besökare baserat på den enskilda kundens profil och beteendet hos tidigare besökare med liknande profiler, för att personalisera innehåll och driva konverteringar. |
| [Multivariattest](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) jämför kombinationer av erbjudanden i element på en sida för att avgöra vilken kombination som fungerar bäst för en viss målgrupp och identifierar vilket element som mest påverkar aktivitetens framgång. |
| [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier. |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) kombinerar erbjudanden eller meddelanden och använder avancerad maskininlärning för att matcha olika varianter till varje besökare baserat på deras individuella kundprofil för att anpassa innehåll och driva konverteringar. |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | En rekommendation avgör hur en produkt föreslås för en besökare, beroende på besökarens aktiviteter på webbplatsen.<P>Du kanske till exempel vill uppmuntra personer som köper en ryggsäck att överväga att köpa vandrande skor och trikåpoler. Du kan skapa en rekommendation som visar objekt som ofta köpts tillsammans med hjälp av algoritmen&quot;Personer som köpte det här&quot;. Eller så kanske du vill uppmuntra besökarna att spendera mer tid på din mediewebbplats genom att rekommendera liknande videor som den video de tittar på, med algoritmen&quot;Personer som såg det här&quot;.<P>**Obs!**: Du kan även inkludera rekommendationer i aktiviteterna [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] och [!UICONTROL Experience Targeting] (XT). Mer information finns i [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/main/c-intro/intro.md#premium). |

## Använda filter i aktivitetslistan {#filters}

Du kan få åtkomst till filter genom att klicka på ikonen **[!UICONTROL Show Filters]** uppe i listan.

![Filteralternativ](/help/main/c-activities/assets/show-filters-options.png)

På menyn kan du filtrera aktiviteter efter följande attribut:
|Attribut|Information|
| — | — |
|[!UICONTROL Type]|Filtrera efter [aktivitetstyp](#types).|
|[!UICONTROL Status]|Filtrera efter aktivitetsstatus.|
|[!UICONTROL Reporting Source]|Filtrera efter rapportkälla.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md): Visa aktiviteter som använder [!UICONTROL Analytics for Target] (A4T) som rapportkälla.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): Visa aktiviteter som använder [!DNL Target] som rapportkälla.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): Visa aktiviteter som använder [!DNL Adobe Customer Analytics] som rapportkälla.</li></ul>|
|[!UICONTROL Experience Composer]|Filter som Experience Composer användes efter när aktiviteten skapades:<ul><li>[Visuell](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): Visar aktiviteter som har skapats med [!UICONTROL Visual Experience Composer] (VEC).</li><li>[Formulärbaserad](/help/main/c-experiences/form-experience-composer.md): Visa aktiviteter som har skapats med [!UICONTROL Form-Based Experience Composer].</li></ul>|
|[!UICONTROL Metrics Type]|Filter som [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md) valdes för när aktiviteten skapades.<ul><li>Konvertering</li><li>Intäkter</li><li>Engagemang</li></ul>|
|[!UICONTROL Decisioning Method]|Filtrera efter den beslutsmetod som används i varje aktivitet<ul><li>[Serversida](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html): Visa aktiviteter som använder serversidesbeslut.</li><li>[Klientsida](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html): Visa aktiviteter som använder beslut på klientsidan.</li></ul>|
|[!UICONTROL Activity Source]|Filtrera efter aktivitetskällan som används för att skapa varje aktivitet.<ul><li>[!DNL Adobe Target]</li><li>[Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)</li><li>[Mobiltjänster för Adobe](https://developer.adobe.com/client-sdks/documentation/)</li></ul>|
|[!UICONTROL Property]|Filtrera efter den [egenskap](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) som aktiviteten skapades i.|

## Utför snabbåtgärder {#quick-actions}

Klicka på ikonen **[!UICONTROL More actions]** (den vågräta ellipsen) bredvid varje aktivitetsnamn för att öppna en meny där du kan utföra snabbåtgärder för en aktivitet.

![Alternativ för snabbåtgärder](/help/main/c-activities/assets/quick-actions.png)

Följande åtgärder är tillgängliga (beroende på dina behörigheter och aktivitetsstatus):

| Åtgärd | Beskrivning |
| --- | --- |
| [!UICONTROL Edit] | Ändra aktiviteten. Alla aktiviteter kan redigeras.<P>Mer information om olika sätt att redigera aktiviteter finns i [Redigera en aktivitet eller Spara som utkast](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Deactivate] | Stoppa en aktiv eller schemalagd aktivitet. En inaktiverad aktivitet kan återaktiveras eller arkiveras.<P>Om du inaktiverar eller arkiverar en aktivitet och sedan återaktiverar den, fortsätter besökaren att vara en del av den aktiviteten efter omaktiveringen om de fanns i den innan den inaktiverades eller arkiverades. Konverteringsvärden som registreras under tiden mellan de två händelserna kommer inte att tillskrivas den aktiviteten. |
| [!UICONTROL Activate] | Starta en inaktiv aktivitet eller en aktivitet som är klar att aktiveras. |
| [!UICONTROL Archive] | Skicka aktiviteten till arkivet. Som standard visas inte längre arkiverade aktiviteter i listan [!UICONTROL Activities]. Ändra filtret för aktivitetslistan så att den innehåller arkiverade aktiviteter för att se dem. Du kan aktivera en arkiverad aktivitet och använda den igen.<P>Om du inaktiverar eller arkiverar en aktivitet och sedan återaktiverar den fortsätter besökaren att vara en del av den aktiviteten efter omaktiveringen om de befann sig i den aktiviteten innan den inaktiverades eller arkiverades. Konverteringsvärden som registreras under tiden mellan de två händelserna kommer inte att tillskrivas den aktiviteten. |
| [!UICONTROL Copy] | Kopiera en aktivitet. Alla aktiviteter kan kopieras. När du kopierar en aktivitet skapas en ny aktivitet med samma namn, som läggs till med &quot;Kopiera&quot;. Ett test med namnet&quot;Browser Offers&quot; kopieras till exempel till&quot;Browser Offers Copy&quot;.<P>Visuella erbjudanden kopieras med aktiviteten. Du kan redigera erbjudandena i kopian utan att det påverkar den ursprungliga aktiviteten. Det enda undantaget är sparade erbjudanden och bilder i mappen Content/Assets. |
| [!UICONTROL Delete] | Ta bort ett utkast eller en aktivitet.<P>**Obs!** Borttagna aktiviteter kan inte återställas. Använd åtgärden [!UICONTROL Archive] om du inte är säker på att du aldrig behöver den här aktiviteten igen. Du kan sedan återaktivera aktiviteten om det behövs. |

## Överväganden

Observera följande information om listan [!UICONTROL Activity]:

* Arkiverade och avslutade aktiviteter visas inte i listan [!UICONTROL Activities]. Om du vill visa de här aktiviteterna filtrerar du dem med [filterikonen](#filters) högst upp i listan.
* När en aktivitet som ursprungligen skapades i [!DNL Target Classic] inaktiveras eller tas bort tas den bort från [!DNL Target Standard/Premium]. Borttagna aktiviteter som ursprungligen skapats i [!DNL Target Classic] skickas inte till mappen [!UICONTROL Archive] i [!DNL Target Standard/Premium]. Den arkiverade mappfunktionen gäller endast aktiviteter som skapats i [!DNL Target Standard/Premium].
* Alla aktivitetstyper förutom [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] ger dig möjlighet att använda antingen [!DNL Target] eller [!DNL Adobe Analytics] som datakälla. [!UICONTROL AP], [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] *always* använder [!DNL Target] data.
* Verksamheter är tillgängliga i flera kanaler:

   * Webbplatser och mobilsajter
   * Internetanslutna skärmar och enheter, inklusive kioskdatorer och uttagsautomater
   * E-post och andra förvärvskanaler eller partnersajter
   * Mobilappar
   * Var du än är kan du leverera taggat innehåll

## Begränsningar {#section_049D4684403A4E07B998067EB8E9BE56}

Varje Target-aktivitet har följande innehållsbegränsningar:

| Objekt | Gräns |
|--- |--- |
| Unika väljare | 300 Om en väljare upprepas med en annan upplevelse räknas den en gång. Om det upprepas med samma erfarenhet räknas det dock igen. |
| Erbjudanden för varje upplevelse | 350 |
| Klicka på spåra väljare i mätvärden | 50 |
| Måttfält | 50 |
| Målgrupper och platser | 50 målgrupper och platskombinationer (mbox) får inte vara större än 50. |

Det går inte att spara aktiviteten om du överskrider någon av dessa gränser.

Om du ökar antalet av dessa objekt i din aktivitet ökar även tiden det tar att synkronisera aktiviteten över [!DNL Target].

Mer information om begränsningar för V[!UICONTROL isual Experience Composer] VEC finns i [Gränser för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attribut som importerats till [!DNL Target] för aktiviteter som uppdaterats utanför [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Om aktiviteter som skapats i [!DNL Target] uppdateras utanför [!DNL Target] (till exempel via API) importeras följande aktivitetsattribut tillbaka till [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` och `marketingCloudMetadata(remoteModifiedBy)`.

Det här importjobbet körs när aktivitetssidan öppnas, med en maximal fördröjning på tio minuter.

## Utbildningsvideor {#section_BE80D13A2E81460C885F902010E1AD87}

Följande video innehåller mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetstyper (9:03)

I den här videon förklaras de aktivitetstyper som är tillgängliga i [!DNL Target Standard/Premium].

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

