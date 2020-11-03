---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content
description: A/B-tester jämför två eller flera versioner av webbplatsinnehållet för att se vilken version som förbättrar konverteringen under en fördefinierad testperiod.
title: A/B-test
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: 130edc89b2c324a0d892a4221f644248e23357a4
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 0%

---


# A/B-test

I ett manuellt A/B-test jämförs två eller flera versioner av webbplatsinnehållet för att se vilken version som optimerar konverteringen under en fördefinierad testperiod.

>[!NOTE]
>
>Utöver den manuella (standard) A/B-testaktiviteten (som beskrivs i detta avsnitt) finns det två ytterligare typer av A/B-testningsaktiviteter som [!DNL Target] ingår: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].
>
>Mer information finns i [Typer av A/B-testningsaktiviteter](#types) nedan.

Ett manuellt A/B-test (kallas ibland A/B...N-test) jämför två eller flera versioner av webbplatsinnehållet för att se vilka som är bäst på att lyfta upp konverteringar, försäljning eller andra mätvärden du identifierar. Använd ett A/B-test för att jämföra ändringar av sidan med standardsiddesignen för att avgöra vilken upplevelse som ger bäst resultat.

Manuella A/B-tester är särskilt användbara när du har en tydlig hypotes om hur du kan förbättra sidans prestanda baserat på framgångsmått eller alternativ innehållsleverans.

Manuella A/B-tester är väl lämpade för stora förändringar som kan innebära nya layouter eller drastiskt olika behandlingar av elementen. Om testdesignen inte så lätt bryts ned i enskilda sidelement bör du köra ett A/B-test före ett multivariattest.

När du ställer in testet kan du bestämma hur många procent av besökarna som ska se varje upplevelse. Du kan till exempel dela upp trafiken jämnt mellan kontrollen och en andra upplevelse, eller testa en ny, mer riskfylld upplevelse genom att visa den för endast 5 % av er målgrupp.

>[!NOTE]
>
>Mer information om hur du fastställer den optimala provstorleken för ett A/B-test finns i [Planera A/B-testet](../../c-activities/t-test-ab/sample-size-determination.md#concept_2801F552DB874C20B8A17C1B774C0383).

När antalet olika upplevelser överstiger fem och sträcker sig över två eller fler platser är det en bra idé att överväga ett [MVT-test](/help/c-activities/c-multivariate-testing/multivariate-testing.md) innan du kör A/B-testerna. Multivariattestet visar vilka områden på sidan som mest sannolikt förbättrar konverteringen. Det här är de platser som en marknadsförare ska fokusera på. MVT-testet kan till exempel visa att uppmaningen att vidta åtgärder är den viktigaste platsen för att uppnå dina mål. När du har fastställt vilka platser och vilket innehåll som är mest användbart för att du ska kunna uppnå dina mål, kan du köra ett A/B-test för att ytterligare förfina resultaten, till exempel för att testa två specifika bilder mot varandra eller jämföra ordalydelsen eller färgerna i en uppmaning till åtgärd. Genom att följa ett MVT-test med ett eller flera A/B-tester kan du fastställa vilket innehåll som är bäst för de resultat du vill ha.

## Typ av A/B-testning {#types}

Utöver den manuella (standard) A/B-testaktiviteten (som beskrivs i detta avsnitt) finns det två ytterligare typer av A/B-testningsaktiviteter som [!DNL Target] ingår: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].

| Typ av aktivitet | Beskrivning |
| --- | --- |
| Manuellt A/B-test | Jämför två eller flera upplevelser för att se vilken som är bäst på att förbättra konverteringarna under en fördefinierad testperiod.<br>I det här avsnittet beskrivs hur du ställer in en manuell A/B-testningsaktivitet, men stegen för de andra typerna av A/B-testningsaktiviteter är liknande. |
| [!UICONTROL Auto-Allocate] | Identifierar en vinnare bland två eller fler upplevelser och dirigerar sedan om trafiken till vinnaren, vilket ökar konverteringsgraden när testet körs och lär sig.<br>Mer information finns i [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Premium-märke](/help/assets/premium.png) [!UICONTROL Auto-Target] | Använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.<br>Mer information finns i [Automatiskt mål](/help/c-activities/auto-target-to-optimize.md). |

Mer information om vilken av dessa A/B-tester som är rätt för dig finns i PDF [-handboken om interaktiva](/help/c-activities/target-activities-guide.md)Adobe Target-aktiviteter.

Stegen för att skapa de tre typerna av A/B-testning är desamma. Om du vill skapa en [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target] aktivitet börjar du med att [skapa en A/B-testningsaktivitet](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), men när du kommer till [!UICONTROL Targeting] sidan väljer du önskad metod för trafikallokering:

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![Inställningar för trafikallokeringsmetod](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Utbildningsvideo: Aktivitetstyper (9:03) ![Översikt](/help/assets/overview.png)

I den här videon förklaras vilka aktivitetstyper som finns i [!DNL Target Standard/Premium].

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
