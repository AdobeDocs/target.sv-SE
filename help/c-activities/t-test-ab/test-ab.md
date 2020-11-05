---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: I en manuell A/B-testaktivitet jämförs två eller flera versioner av webbplatsinnehållet för att se vilken version som optimerar dina konverteringar under en fördefinierad testperiod.
title: Översikt över A/B-test
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 0%

---


# Översikt över A/B-test

En manuell [!UICONTROL A/B Test] aktivitet jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som förbättrar konverteringen under en fördefinierad testperiod.

>[!NOTE]
>
>Förutom den manuella (standard) [!UICONTROL A/B Test] -aktiviteten (som beskrivs i det här avsnittet), finns det ytterligare två typer av [!DNL Target] [!UICONTROL A/B Test] aktiviteter: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].
>
>Mer information finns i [Typer av A/B-testningsaktiviteter](#types) nedan.

En manuell [!UICONTROL A/B Test] aktivitet (kallas ibland A/B...N-test) jämför två eller flera versioner av webbplatsinnehållet för att se vilka som är bäst på att lyfta upp konverteringar, försäljning eller andra mätvärden du identifierar. Använd ett A/B-test för att jämföra ändringar av sidan med standardsiddesignen för att avgöra vilken upplevelse som ger bäst resultat.

Manuella A/B-tester är särskilt användbara när du har en tydlig hypotes om hur du kan förbättra sidans prestanda baserat på framgångsmått eller alternativ innehållsleverans.

Manuella A/B-tester är väl lämpade för stora förändringar som kan innebära nya layouter eller drastiskt olika behandlingar av elementen. Om testdesignen inte så lätt bryts ned i enskilda sidelement bör du köra ett A/B-test före ett [multivariattest](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

När du konfigurerar A/B-testet kan du bestämma hur många procent besökare som ska se varje upplevelse. Du kan till exempel dela upp trafiken jämnt mellan kontrollen och en andra upplevelse, eller testa en ny, mer riskfylld upplevelse genom att visa den för endast 5 % av er målgrupp.

>[!NOTE]
>
>Mer information om hur du fastställer den optimala provstorleken för ett A/B-test finns i [Planera A/B-testet](/help/c-activities/t-test-ab/sample-size-determination.md).

När antalet olika upplevelser överstiger fem och sträcker sig över två eller fler platser är det en bra idé att överväga ett [MVT-test](/help/c-activities/c-multivariate-testing/multivariate-testing.md) innan du kör A/B-testerna. Multivariattestet visar vilka områden på sidan som mest sannolikt förbättrar konverteringen. Det här är de platser som en marknadsförare ska fokusera på. MVT-testet kan till exempel visa att uppmaningen att vidta åtgärder är den viktigaste platsen för att uppnå dina mål. När du har fastställt vilka platser och vilket innehåll som är mest användbart för att du ska kunna uppnå dina mål, kan du köra ett A/B-test för att ytterligare förfina resultaten, till exempel för att testa två specifika bilder mot varandra, eller för att jämföra ordalydelsen eller färgerna i en uppmaning till åtgärd. Genom att följa ett MVT-test med ett eller flera A/B-tester kan du fastställa vilket innehåll som är bäst för de resultat du vill ha.

## Typ av A/B-testning {#types}

Förutom den manuella [!UICONTROL A/B Test] aktiviteten (som beskrivs i detta avsnitt) [!DNL Target] finns ytterligare två typer av A/B-testningsaktiviteter: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].

| Typ av aktivitet | Beskrivning |
| --- | --- |
| [!UICONTROL Manual A/B Test] | Jämför två eller flera upplevelser för att se vilken som är bäst på att förbättra konverteringarna under en fördefinierad testperiod.<br>I det här avsnittet beskrivs hur du ställer in en manuell [!UICONTROL A/B Test] aktivitet, men stegen för de andra typerna av [!UICONTROL A/B Test] aktiviteter är liknande. |
| [!UICONTROL Auto-Allocate] | Identifierar en vinnare bland två eller fler upplevelser och dirigerar sedan om trafiken till vinnaren, vilket ökar konverteringsgraden när testet körs och lär sig.<br>Om du vill veta mer om fördelarna med att använda en automatisk fördelning läser du [Automatisk fördelning](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) i *Hur länge ska du köra en A/B-test* - och [Automatisk fördelning-översikt](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Premium-märke](/help/assets/premium.png) [!UICONTROL Auto-Target] | Använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.<br>Mer information finns i [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md). |

Mer information om vilken av dessa [!UICONTROL A/B Test] aktiviteter som passar dig finns i PDF-filen med handboken om interaktiva [Adobe Target-aktiviteter](/help/c-activities/target-activities-guide.md).

Stegen för att skapa de tre typerna av [!UICONTROL A/B Test] aktiviteter är liknande. Om du vill skapa en [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target] aktivitet börjar du med att [skapa en A/B-testaktivitet](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), men när du kommer till [!UICONTROL Targeting] sidan väljer du den trafikallokeringsmetod som visas nedan:

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![Inställningar för trafikallokeringsmetod](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Utbildningsvideo: Aktivitetstyper (9:03) ![Översikt](/help/assets/overview.png)

I den här videon förklaras vilka aktivitetstyper som finns i [!DNL Target Standard/Premium].

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
