---
keywords: Målgrupper;målgruppsfilter;målgrupper;filter
description: Lär dig hur du använder målgruppsfilter i  [!DNL Adobe Target]  för att visa data från besökare som delar egenskaper.
title: Kan jag använda målgruppsfilter för rapportering?
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---

# Målgruppsfilter för rapportering

Målgruppsfilter (eller målgrupper) i [!DNL Adobe Target] är grupper med besökare som delar en specifik egenskap eller uppsättning med egenskaper.

Använd målgruppsfilter för att ange vilka målgrupper som ska användas för rapportering. Du kan välja en målgrupp och jämföra dess prestanda med den övergripande trafiken. Ni kanske vill förstå om era vinnare var annorlunda för de olika trafikkällorna jämfört med den allmänna trafiken. Målgruppsfilter hjälper er att identifiera målgrupper som kan vara inriktade på olika innehåll. En vinnare passar inte all trafik i många fall.

Besökare som kommer till din sida från en viss sökmotor kan till exempel vara en enda publik. Andra målgrupper kan baseras på kön, ålder, plats, registreringsstatus, inköpshistorik eller på någon annan information du kan samla in om besökarna. Använd målgruppsfilter för att dela upp besökstrafiken och jämföra upplevelseprestanda för varje trafiksegment.

Tänk på följande när du planerar att använda målgruppsfilter för en aktivitet:

* **Besökare kan finnas i flera målgrupper.** Om två målgrupper har konfigurerats (till exempel&quot;nya besökare&quot; och&quot;besökare från Google&quot;) och en person uppfyller båda kriterierna, räknas och spåras den här besökaren i båda målgrupperna. Resultatet blir att besökarnas antal inte matchar antalet besökare i en aktivitet.
* **Konfigurera målgrupper innan aktiviteten startas.** Målgruppsdata kan inte hämtas retroaktivt. Om du inte konfigurerar målgruppsfilter innan du startar aktiviteten och sedan bestämmer dig för att använda dem efter att aktiviteten har körts en stund, kommer du inte att samla in data för den tid som redan har gått.
* **Börja med två till fyra målgrupper.** Fokuserar på grundläggande information, t.ex. trafikkällan.
* **Byt namn på målgrupper efter behov.** Du kan byta namn på en målgrupp utan att påverka data för att göra målgruppsnamnet mer meningsfullt för de resultat som samlas in, även om aktiviteten är aktiv.
* **Ange exakta värden.** målgruppsfiltervärden är skiftlägeskänsliga. Om du t.ex. använder en målgrupp som filtrerar efter städer bör du använda ett &quot;OR&quot;-villkor för att inkludera eventuella stavnings- och skiftlägesvariationer, t.ex. &quot;Wien&quot;, &quot;vienn&quot;, &quot;wien&quot; och &quot;Wien&quot;.
* **Publiker som skapats från listan [!UICONTROL Audiences] kan återanvändas.** Publiker som skapats som en del av en aktivitet kan inte återanvändas.

I följande avsnitt finns mer information om hur du skapar och rapporterar om målgrupper:

| Uppgift | Ämne |
|--- |--- |
| Skapa lämplig aktivitet eller test. | [Aktiviteter och tester](/help/main/c-intro/target-key-concepts.md) |
| Skapa målgrupper, om det behövs. | [Skapa en publik](/help/main/c-target/c-audiences/create-audience.md) |
| Kombinera flera målgrupper, om det behövs. | [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md) |
| Använd målgrupper på aktivitetens sida med mål och inställningar. | A/B-test: [Mål och inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization: [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>Upplevelsemål: [Mål och inställningar](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Multivariata tester: [Mål och inställningar](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Rekommendationer: [Rekommendationer för aktivitetsinställningar](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Aktivitetsinställningar: [Aktivitetsinställningar](/help/main/c-activities/activity-settings.md) |
| Visa rapporter med information om era målgruppsfilter. | [Rapportinställningar](/help/main/c-reports/c-report-settings/report-settings.md) |
