---
keywords: prioritet;upplevelseskapa;prioritet;upplevelse;målgrupp;upplevelse;växla upplevelser;kompositör för visuell upplevelse
description: Lär dig hur besökare kan växla mellan upplevelser i en  [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT)-aktivitet allt eftersom deras profiler utvecklas.
title: Kan besökare byta upplevelser i en [!UICONTROL Experience Targeting]-aktivitet?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 0%

---

# Byta upplevelser i [!UICONTROL Experience Targeting]

Med [!UICONTROL Experience Targeting] kan du styra vilka upplevelsebesökare ser när deras profiler utvecklas.

I följande lista visas bara några scenarier där besökarprofiler kan utvecklas och du kanske vill presentera olika innehåll baserat på dessa ändringar:

| Scenario | Information |
|--- |--- |
| Geografisk plats | När besökare reser för företag eller nöjes skull kan de se din webbplats eller mobilapp från olika geografiska platser. |
| Kundstatus | Besökare kan betraktas som potentiella kunder innan de skapar ett konto eller köper en produkt. |
| Kategoritillhörighet | [kategoritillhörigheten](/help/main/c-target/c-visitor-profile/category-affinity.md) i [!DNL Target] fångar automatiskt kategorivyn för besökare och beräknar sedan besökarnas tillhörighet för kategorin för målsyften. Besökare som har visat flera artiklar på din webbplats om ett visst ämne får till exempel innehåll som är relaterat till det ämnet. |
| Veckodag | När helgen närmar sig kanske du vill visa besökarna innehåll om filmer, matningar eller andra former av underhållning. |

Om du vill använda de här funktionerna i [!DNL Target] är det viktigt att du förstår följande information när du arbetar med [!UICONTROL Experience Targeting]-aktiviteter:

* **Prioriteten styrs av upplevelseordningen, uppifrån och ned.** Om en besökare kvalificerar sig för fler än två målgrupper tar besökaren emot innehåll från upplevelsen med högre prioritet.
* **Besökare växlar mellan upplevelser i en [!UICONTROL Experience Targeting]-aktivitet om de börjar kvalificera sig för målgruppen i en upplevelse med högre prioritet.**

  I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Tyskland och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). Efter att ha besökt er webbplats från Tyskland bytte besökaren till Experience B (tyska besökare).

  ![Prioritet, USA > Tyskland](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Besökare växlar också mellan upplevelser om de slutar kvalificera sig för sin nuvarande målgrupp men börjar kvalificera sig för en upplevelse med lägre prioritet.**
* **Om besökare slutar kvalificera sig för sin aktuella upplevelse och inte kvalificerar sig för en annan upplevelse, visas standardinnehållet.**

  I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Frankrike och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). När du har visat din webbplats från Frankrike är besökaren kvar i den ursprungliga upplevelsen.

  ![Prioritet, USA > Tyskland](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **En upplevelse som är inriktad på Alla besökare kan användas som den sista upplevelsen i [!UICONTROL Experience Targeting] -aktiviteten för att&quot;fånga&quot; besökare som inte har kvalificerat sig för någon annan upplevelse. Om en upplevelse som är inriktad på Alla besökare inte är den sista i ordningen utvärderas fortfarande andra målupplevelser som är lägre än den här.**

  I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Tyskland och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). När du har visat din webbplats från Tyskland finns besökaren kvar i Experience A (amerikanska besökare).

  ![Prioritet, USA > Alla besökare](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  Om detta inte är önskvärt kan du skapa en ny målgrupp som uttryckligen definieras som den omvända målgruppen, vilket visas i följande exempel:

  ![Prioritet, USA > Inte USA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Med en upplevelse [!UICONTROL Experience Targeting] har besökarna kvar en upplevelse även om de inte längre är kvalificerade för den målgrupp som fick dem.**

  Om detta inte är önskvärt kan du skapa en ny upplevelse som är riktad till den omvända publiken (till exempel&quot;Inte USA&quot; till skillnad från&quot;USA&quot;).

  Som ett annat alternativ kan du skapa en [!UICONTROL A/B Test]-aktivitet som är riktad till den önskade publiken med 100 % trafikallokering, vilket visas nedan:

  ![Prioritera en upplevelse](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **Prioriteten för upplevelserna definieras av deras ordning (uppifrån och ned) när de visas i [!DNL Target] användargränssnittet.**

  Detta är viktigt att tänka på i scenarier där en besökare kan kvalificera sig för fler än en av era målgrupper. Om du till exempel har två upplevelser: en som är riktad till&quot;USA&quot; och en som är inriktad på&quot;New York&quot;, kvalificerar en besökare som finns i New York sig för båda målgrupperna. Därför måste du se till att upplevelsen av&quot;New York&quot; definieras före upplevelsen av&quot;USA&quot; i användargränssnittet för [!DNL Target]. Detta säkerställer att den mer målinriktade&quot;New York&quot;-upplevelsen har högre prioritet, vilket visas i följande exempel:

  ![Prioritet NY > US](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
