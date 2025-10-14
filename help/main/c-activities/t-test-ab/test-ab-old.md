---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-assign
description: Lär dig mer om de olika typerna av A/B-testaktiviteter i Adobe [!DNL Target] - handbok, Automatisk allokering och Automatiskt mål. Välj den som passar dig.
title: Vilken typ av A/B-aktiviteter är tillgängliga i mål?
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# Översikt över A/B-test

En manuell [!UICONTROL A/B Test]-aktivitet jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som förbättrar dina konverteringar under en fördefinierad testperiod.

>[!NOTE]
>
>Utöver aktiviteten Manuell (standard) [!UICONTROL A/B Test] (beskrivs i det här avsnittet) innehåller [!DNL Target] ytterligare två typer av [!UICONTROL A/B Test]-aktiviteter: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]. Mer information finns i [Typer av A/B-testningsaktiviteter](#types) nedan.

En manuell [!UICONTROL A/B Test]-aktivitet (kallas ibland A/B...N-test) jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som bäst lyfter dina konverteringar, försäljning eller andra mätvärden du identifierar. Använd ett A/B-test för att jämföra ändringar av sidan med standardsiddesignen för att avgöra vilken upplevelse som ger bäst resultat.

Manuella A/B-tester är användbara när du har en tydlig hypotes om hur du kan förbättra sidans prestanda baserat på framgångsmått eller alternativ innehållsleverans.

Manuella A/B-tester passar bra för stora förändringar som kan innebära nya layouter eller drastiskt olika behandlingar av elementen. Om testdesignen inte så lätt bryts ned i enskilda sidelement bör du köra ett A/B-test före ett [multivariat-test](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

När du konfigurerar A/B-testet kan du bestämma hur många procent besökare som ska se varje upplevelse. Du kan till exempel dela upp trafiken jämnt mellan kontrollen och en andra upplevelse, eller testa en ny, mer riskfylld upplevelse genom att visa den för endast 5 % av er målgrupp.

>[!NOTE]
>
>Mer information om hur du fastställer den optimala provstorleken för ett A/B-test finns i [Planera A/B-testet](/help/main/c-activities/t-test-ab/sample-size-determination.md).

När antalet olika upplevelser överstiger fem och sträcker sig över två eller fler platser är det en bra idé att överväga ett [MVT-test](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) innan du kör A/B-testerna. Multivariattestet visar vilka områden på sidan som mest sannolikt förbättrar konverteringen. Dessa områden är de platser som en marknadsförare ska fokusera på. Till exempel kan MVT-testet visa att call to action är den viktigaste platsen för att nå dina mål. När du har fastställt vilka platser och vilket innehåll som är mest användbart för att du ska kunna uppnå dina mål kan du köra ett A/B-test för att ytterligare förfina resultaten. Du kan till exempel testa två specifika bilder mot varandra eller jämföra ordalydelsen eller färgerna i en call to action. Genom att följa ett MVT-test med ett eller flera A/B-tester kan du fastställa vilket innehåll som är bäst för de resultat du vill ha.

## Typ av A/B-testning {#types}

Utöver den manuella [!UICONTROL A/B Test]-aktiviteten (som beskrivs i det här avsnittet) innehåller [!DNL Target] ytterligare två typer av A/B-testningsaktiviteter: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].

| Typ av aktivitet | Beskrivning |
| --- | --- |
| [!UICONTROL Manual A/B Test] | Jämför två eller flera upplevelser för att se vilken som ger bäst konvertering under en förspecificerad testperiod.<P>I det här avsnittet beskrivs hur du konfigurerar en manuell [!UICONTROL A/B Test]-aktivitet, men stegen för de andra typerna av [!UICONTROL A/B Test]-aktiviteter är liknande. |
| [!UICONTROL Auto-Allocate] | Identifierar en vinnare bland två eller fler upplevelser och dirigerar sedan om trafiken till vinnaren, vilket ökar konverteringsgraden när testet körs och lär sig.<P>Om du vill veta mer om fördelarna med att använda en [!UICONTROL Auto-Allocate]-aktivitet kan du läsa [Automatisk fördelning](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) i *Hur länge ska du köra ett A/B-test* och [Översikt över automatisk fördelning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Premium-märke](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | Använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser. Den mest skräddarsydda upplevelsen betjänas sedan av besökarna baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.<P>Mer information finns i [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Mer information om vilka av dessa [!UICONTROL A/B Test] aktiviteter som är rätt för dig finns i den interaktiva [Adobe Target Activity Guide PDF](/help/main/c-activities/target-activities-guide.md).

Stegen för att skapa de tre typerna av [!UICONTROL A/B Test]-aktiviteter liknar varandra. Om du vill skapa en [!UICONTROL Auto-Allocate]- eller [!UICONTROL Auto-Target]-aktivitet börjar du med [att skapa en A/B-testaktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), men när du kommer till sidan [!UICONTROL Targeting] väljer du den trafikallokeringsmetod du vill använda, som visas nedan:

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![Inställningar för trafikallokeringsmetod](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Inkludera rekommendationer i A/B-aktiviteter

Du kan inkludera rekommendationer inuti [!UICONTROL A/B Test]-, [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter (och [!UICONTROL Experience Targeting] (XT)). Mer information finns i [Rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

Den här funktionen kräver att du har en [Target Premium-licens](/help/main/c-intro/intro.md#premium)

## Utbildningsvideo: Aktivitetstyper (9:03) ![Översikt &#x200B;](/help/main/assets/overview.png)

I den här videon förklaras de aktivitetstyper som är tillgängliga i [!DNL Target Standard/Premium].

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
