---
keywords: prioritet;upplevelseskapa;prioritet;upplevelse;målgrupp;upplevelse;växla upplevelser;kompositör för visuell upplevelse
description: Se hur besökare kan växla mellan upplevelser på Adobe [!DNL Target] Upplev målgruppsaktiviteten (XT) i takt med att deras profiler utvecklas.
title: Kan besökare byta upplevelser i en upplevelseinriktad aktivitet?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: ceae12da7ee3580a943da180e8705fc5d4ab646a
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

---

# Byta upplevelser i Experience Targeting

Information om hur besökare kan växla mellan upplevelser i en XT-aktivitet (Experience Targeting) allt eftersom deras profiler utvecklas.

Med Experience Targeting kan ni styra vilka upplevelsebesökare ser när deras profiler utvecklas. I följande lista visas bara några scenarier där besökarprofiler kan utvecklas och du kanske vill presentera olika innehåll:

| Scenario | Detaljer |
|--- |--- |
| Geografisk plats | När besökare reser för företag eller nöjes skull kan de se din webbplats eller mobilapp från olika geografiska platser. |
| Kundstatus | Besökare kan betraktas som potentiella kunder innan de skapar ett konto eller köper en produkt. |
| Kategoritillhörighet | The [kategoritillhörighet](/help/main/c-target/c-visitor-profile/category-affinity.md) funktionen i Target fångar automatiskt de kategorier som användare besöker och beräknar sedan användarnas tillhörighet för kategorin för målinriktningsändamål. Besökare som har visat flera artiklar på din webbplats om ett visst ämne kan till exempel få innehåll som är relaterat till det ämnet. |
| Veckodag | När helgen närmar sig kanske du vill visa besökarna innehåll om filmer, matningar eller andra former av underhållning. |

Att utnyttja dessa funktioner i [!DNL Target]är det viktigt att du förstår följande information när du arbetar med XT-aktiviteter:

* **Prioriteten styrs av upplevelseordningen, uppifrån och ned.** Om en besökare kvalificerar sig för fler än två målgrupper får han eller hon innehåll från upplevelsen med högre prioritet.
* **Besökarna kommer att växla mellan upplevelserna i en XT-aktivitet om de börjar kvalificera sig för en upplevelse med högre prioritet.**

   I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Tyskland och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). Efter att ha besökt er webbplats från Tyskland bytte besökaren till Experience B (tyska besökare).

   ![Prioritet US > Tyskland](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Besökarna kommer också att växla mellan upplevelserna om de slutar kvalificera sig för sin nuvarande målgrupp men börjar kvalificera sig för en upplevelse med lägre prioritet.**
* **Om besökarna slutar kvalificera sig för sin aktuella upplevelse och inte kvalificerar sig för en annan upplevelse, kommer de att se standardinnehållet.**

   I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Frankrike och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). När du har tittat på din webbplats från Frankrike är besökaren kvar i den ursprungliga upplevelsen.

   ![Prioritet US > Tyskland](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **En upplevelse som är inriktad på&quot;Alla besökare&quot; kan användas som den sista upplevelsen i aktiviteten för målinriktning av upplevelser för att&quot;fånga&quot; besökare som inte har hamnat i någon annan upplevelse. Om en upplevelse som är inriktad på&quot;Alla besökare&quot; inte är den sista i ordningen kommer andra målinriktade upplevelser som är listade under den här upplevelsen fortfarande att utvärderas.**

   I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Tyskland och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). När du har tittat på din webbplats från Tyskland finns besökaren kvar i Experience A (amerikanska besökare).

   ![Prioritet US > Alla besökare](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

   Om detta inte är önskvärt kan du skapa en ny målgrupp som uttryckligen definieras som den omvända målgruppen, vilket visas i följande exempel:

   ![Prioritet US > Inte USA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Med en enda upplevelse av XT-aktiviteten har besökarna kvar en upplevelse även om de inte längre är kvalificerade för den målgrupp som ger dem den upplevelsen.**

   Om detta inte är önskvärt kan du skapa en ny upplevelse som är riktad till den omvända publiken (till exempel&quot;Inte USA&quot; till skillnad från&quot;USA&quot;).

   Som ett annat alternativ kan du skapa en A/B-aktivitet som är riktad till den önskade publiken med 100 % trafikallokering, vilket visas nedan:

   ![Prioriterad upplevelse](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **Prioriteten för upplevelserna definieras av deras ordning (högst upp ned) när de visas i målgränssnittet.**

   Detta är viktigt att tänka på i scenarier där en besökare kan kvalificera sig för fler än en av era målgrupper. Om du till exempel har två upplevelser: en besökare i New York skulle kvalificera sig för båda målgrupperna. Därför måste du se till att&quot;New York&quot;-upplevelsen definieras före&quot;United States&quot;-upplevelsen i Target-användargränssnittet. Detta garanterar att den mer målinriktade&quot;New York&quot;-upplevelsen har högre prioritet, vilket visas i följande exempel:

   ![Prioritet NY > US](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
