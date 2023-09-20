---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-assign
description: Lär dig mer om de olika typerna av A/B-testaktiviteter i Adobe [!DNL Target] - Manuell, Automatisk allokering och Automatisk målning. Välj den som passar dig.
title: Vilken typ av A/B-aktiviteter är tillgängliga i mål?
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: b5da2f5d41739af39d97e0ce9761006794c04d2b
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 0%

---

# Översikt över A/B-test

En handbok [!UICONTROL A/B Test] -aktiviteten jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som förbättrar dina konverteringar under en fördefinierad testperiod.

>[!NOTE]
>
>Förutom manualen (standard) [!UICONTROL A/B Test] verksamhet (diskuteras i detta avsnitt), [!DNL Target] innehåller ytterligare två typer av [!UICONTROL A/B Test] verksamhet: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]. Se [Typ av A/B-testning](#types) nedan för mer information.

En handbok [!UICONTROL A/B Test] aktiviteten (kallas ibland A/B...N-test) jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som bäst lyfter din konvertering, försäljning eller andra mätvärden du identifierar. Använd ett A/B-test för att jämföra ändringar av sidan med standardsiddesignen för att avgöra vilken upplevelse som ger bäst resultat.

Manuella A/B-tester är användbara när du har en tydlig hypotes om hur du kan förbättra sidans prestanda baserat på framgångsmått eller alternativ innehållsleverans.

Manuella A/B-tester passar bra för stora förändringar som kan innebära nya layouter eller drastiskt olika behandlingar av elementen. Om testdesignen inte så lätt bryts ned i enskilda sidelement bör du köra ett A/B-test före en [multivariata tester](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

När du konfigurerar A/B-testet kan du bestämma hur många procent besökare som ska se varje upplevelse. Du kan till exempel dela upp trafiken jämnt mellan kontrollen och en andra upplevelse, eller testa en ny, mer riskfylld upplevelse genom att visa den för endast 5 % av er målgrupp.

>[!NOTE]
>
>Mer information om hur du avgör den optimala provstorleken för ett A/B-test finns i [Planera ditt A/B-test](/help/main/c-activities/t-test-ab/sample-size-determination.md).

När antalet olika upplevelser överstiger fem och sträcker sig över två eller fler platser är det en bra idé att överväga en [MVT-test](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) innan du kör A/B-testerna. Multivariattestet visar vilka områden på sidan som mest sannolikt förbättrar konverteringen. Dessa områden är de platser som en marknadsförare ska fokusera på. MVT-testet kan till exempel visa att uppmaningen att vidta åtgärder är den viktigaste platsen för att uppnå dina mål. När du har fastställt vilka platser och vilket innehåll som är mest användbart för att du ska kunna uppnå dina mål kan du köra ett A/B-test för att ytterligare förfina resultaten. Om du till exempel vill testa två specifika bilder mot varandra eller jämföra ordalydelsen eller färgerna i en uppmaning till åtgärd. Genom att följa ett MVT-test med ett eller flera A/B-tester kan du fastställa vilket innehåll som är bäst för de resultat du vill ha.

## Typ av A/B-testning {#types}

Utöver handboken [!UICONTROL A/B Test] verksamhet (diskuteras i detta avsnitt), [!DNL Target] innehåller ytterligare två typer av A/B-testningsaktiviteter: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].

| Typ av aktivitet | Beskrivning |
| --- | --- |
| [!UICONTROL Manual A/B Test] | Jämför två eller flera upplevelser för att se vilken som ger bäst konvertering under en förspecificerad testperiod.<P>I det här avsnittet beskrivs hur du konfigurerar en handbok [!UICONTROL A/B Test] -aktivitet, men steg för andra typer av [!UICONTROL A/B Test] liknande verksamhet. |
| [!UICONTROL Auto-Allocate] | Identifierar en vinnare bland två eller fler upplevelser och dirigerar sedan om trafiken till vinnaren, vilket ökar konverteringsgraden när testet körs och lär sig.<P>Lär dig mer om fördelarna med att använda [!UICONTROL Auto-Allocate] aktivitet, se [Automatisk allokering](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) in *Hur länge ska du köra ett A/B-test?* och [Automatisk allokering - översikt](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Premium-märke](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | Använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser. Den mest skräddarsydda upplevelsen betjänas sedan av besökarna baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.<P>Mer information finns i [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Mer information om vilka av dessa [!UICONTROL A/B Test] aktiviteter passar dig bäst, se [Adobe Target Activity Guide PDF](/help/main/c-activities/target-activities-guide.md).

Stegen för att skapa de tre typerna av [!UICONTROL A/B Test] liknande verksamhet. Skapa en [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target] aktivitet, börja med [skapa en A/B-testaktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), men när du kommer till [!UICONTROL Targeting] väljer du den trafikallokeringsmetod som visas nedan:

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![Inställningar för trafikallokeringsmetod](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Inkludera rekommendationer i A/B-aktiviteter

Du kan inkludera rekommendationer i [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate]och [!UICONTROL Auto-Target] verksamhet (och [!UICONTROL Experience Targeting] (XT). Mer information finns i [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

Den här funktionen kräver att du har en [Target Premium-licens](/help/main/c-intro/intro.md#premium)

## Utbildningsvideo: Aktivitetstyper (9:03) ![Märket Översikt](/help/main/assets/overview.png)

I den här videon förklaras aktivitetstyperna som finns i [!DNL Target Standard/Premium].

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
