---
keywords: Targeting;audience filter;audiences;filter
description: Målgruppsfilter i Adobe Target (eller målgrupper) är grupper med besökare som delar en specifik egenskap eller uppsättning egenskaper.
title: Målgruppsfilter för rapportering i Adobe Target
uuid: ca2632c0-87e4-4a85-95e6-e63cf800ab2f
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Målgruppsfilter för rapportering{#audience-filters-for-reporting}

Målgruppsfilter (eller målgrupper) är grupper med besökare som delar en specifik egenskap eller uppsättning egenskaper.

Använd målgruppsfilter för att ange vilka målgrupper som ska användas för rapportering. Du kan välja en målgrupp och jämföra dess prestanda med den övergripande trafiken. Ni kanske vill förstå om era vinnare var annorlunda för de olika trafikkällorna jämfört med den allmänna trafiken. Detta hjälper er att identifiera målgrupper som kan vara inriktade på olika innehåll. En vinnare passar inte all trafik i många fall.

Besökare som kommer till din sida från en viss sökmotor kan till exempel vara en enda publik. Andra målgrupper kan baseras på kön, ålder, plats, registreringsstatus, inköpshistorik eller på någon annan information du kan samla in om besökarna. Använd målgruppsfilter för att dela upp besökstrafiken och jämföra upplevelseprestanda för varje trafiksegment.

Tänk på följande när du planerar att använda målgruppsfilter för en aktivitet:

* **Besökarna kan finnas i flera olika målgrupper.** Om det finns två målgrupper (till exempel&quot;nya besökare&quot; och&quot;besökare från Google&quot;) och en person uppfyller båda kriterierna, räknas och spåras den här besökaren i båda målgrupperna. Resultatet blir att besökarnas antal inte matchar antalet besökare i en aktivitet.
* **Ställ in målgrupper innan du startar aktiviteten.** Det går inte att hämta målgruppsdata retroaktivt. Om du inte konfigurerar målgruppsfilter innan du startar aktiviteten och sedan bestämmer dig för att använda dem efter att aktiviteten har körts en stund, kommer du inte att samla in data för den tid som redan har gått.
* **Börja med två till fyra målgrupper.** Fokusera på grundläggande information, t.ex. trafikkällan.
* **Byt namn på målgrupperna efter behov.** Du kan byta namn på en målgrupp utan att påverka data för att göra målgruppsnamnet mer meningsfullt för de resultat som samlas in, även om aktiviteten är aktiv.
* **Ange exakta värden.** Målgruppsfiltervärden är skiftlägeskänsliga. Om du t.ex. använder en målgrupp som filtrerar efter städer bör du använda ett &quot;OR&quot;-villkor för att inkludera eventuella stavnings- och skiftlägesvariationer, t.ex. &quot;Wien&quot;, &quot;vienn&quot;, &quot;wien&quot; och &quot;Wien&quot;.
* **Publiker som har skapats från publiklistan kan återanvändas.** Målgrupper som skapats som en del av en aktivitet kan inte återanvändas.

I följande avsnitt finns mer information om hur du skapar och rapporterar om målgrupper:

| Uppgift | Ämne |
|--- |--- |
| Skapa lämplig aktivitet eller test. | [Verksamheter och tester](/help/c-intro/target-key-concepts.md) |
| Skapa målgrupper, om det behövs. | [Skapa en publik](/help/c-target/c-audiences/create-audience.md) |
| Kombinera flera målgrupper, om det behövs. | [Kombinera flera målgrupper](/help/c-target/combining-multiple-audiences.md) |
| Använd målgrupper på aktivitetens sida med mål och inställningar. | A/B-test: [Mål och](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>inställningarAutomatiserad personalisering:  [Automatiserad](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>personaliseringUpplevelser: [Mål och](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>inställningarMultivariattest:  [Mål och](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>inställningarRekommendationer: [Rekommendationer](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>aktivitetsinställningarAktivitetsinställningar: [Aktivitetsinställningar](/help/c-activities/activity-settings.md) |
| Visa rapporter med information om era målgruppsfilter. | [Rapportinställningar](/help/c-reports/c-report-settings/report-settings.md) |

