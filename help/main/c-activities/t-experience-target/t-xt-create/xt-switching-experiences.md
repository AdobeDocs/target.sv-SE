---
keywords: prioritet;upplevelseskapa;prioritet;upplevelse;målgrupp;upplevelse;växla upplevelser;kompositör för visuell upplevelse
description: Se hur besökare kan växla mellan upplevelser i en [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) i takt med att deras profiler utvecklas.
title: Kan besökare byta upplevelser i en [!UICONTROL Experience Targeting] Aktivitet?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---

# Byta upplevelser i [!UICONTROL Experience Targeting]

Med [!UICONTROL Experience Targeting]kan ni styra vilken upplevelse besökarna ser när deras profiler utvecklas.

I följande lista visas bara några scenarier där besökarprofiler kan utvecklas och du kanske vill presentera olika innehåll baserat på dessa ändringar:

| Scenario | Information |
|--- |--- |
| Geografisk plats | När besökare reser för företag eller nöjes skull kan de se din webbplats eller mobilapp från olika geografiska platser. |
| Kundstatus | Besökare kan betraktas som potentiella kunder innan de skapar ett konto eller köper en produkt. |
| Kategoritillhörighet | The [kategoritillhörighet](/help/main/c-target/c-visitor-profile/category-affinity.md) funktion i [!DNL Target] hämtar automatiskt kategorivyn för besökare och beräknar sedan besökarnas tillhörighet för kategorin för målinriktningsändamål. Besökare som har visat flera artiklar på din webbplats om ett visst ämne får till exempel innehåll som är relaterat till det ämnet. |
| Veckodag | När helgen närmar sig kanske du vill visa besökarna innehåll om filmer, matningar eller andra former av underhållning. |

Så här använder du funktionerna i [!DNL Target]är det viktigt att du förstår följande information när du arbetar med [!UICONTROL Experience Targeting] verksamhet:

* **Prioriteten styrs av upplevelseordningen, uppifrån och ned.** Om en besökare kvalificerar sig för fler än två målgrupper får den besökaren innehåll från upplevelsen med högre prioritet.
* **Besökarna växlar mellan upplevelserna i en [!UICONTROL Experience Targeting] om de börjar kvalificera sig för en högre prioritet.**

  I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Tyskland och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). Efter att ha besökt er webbplats från Tyskland bytte besökaren till Experience B (tyska besökare).

  ![Prioritet US > Tyskland](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Besökarna växlar också mellan upplevelserna om de slutar kvalificera sig för sin nuvarande målgrupp men börjar kvalificera sig för en upplevelse med lägre prioritet.**
* **Om besökarna slutar kvalificera sig för sin aktuella upplevelse och inte kvalificerar sig för en annan upplevelse, ser de standardinnehållet.**

  I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Frankrike och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). När du har visat din webbplats från Frankrike är besökaren kvar i den ursprungliga upplevelsen.

  ![Prioritet US > Tyskland](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **En upplevelse som är inriktad på&quot;Alla besökare&quot; kan användas som den sista upplevelsen i [!UICONTROL Experience Targeting] aktivitet för att&quot;fånga&quot; besökare som inte har kvalificerat sig för någon annan upplevelse. Om en upplevelse som är inriktad på&quot;Alla besökare&quot; inte är den sista i ordningen utvärderas även andra målinriktade upplevelser som är lägre än den här upplevelsen.**

  I följande aktivitetskonfiguration besökte en besökare din webbplats från USA och reste sedan till Tyskland och besökte din webbplats en andra gång. Under det första besöket var denna besökare kvalificerad för Experience A (amerikanska besökare). När du har visat din webbplats från Tyskland finns besökaren kvar i Experience A (amerikanska besökare).

  ![Prioritet US > Alla besökare](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  Om detta inte är önskvärt kan du skapa en ny målgrupp som uttryckligen definieras som den omvända målgruppen, vilket visas i följande exempel:

  ![Prioritet US > Inte USA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Med en enda upplevelse [!UICONTROL Experience Targeting] besökarna fortsätter att vara i en upplevelse även om de inte längre är kvalificerade för den målgrupp som fick dem i den upplevelsen.**

  Om detta inte är önskvärt kan du skapa en ny upplevelse som är riktad till den omvända publiken (till exempel&quot;Inte USA&quot; till skillnad från&quot;USA&quot;).

  Som ett annat alternativ kan du skapa en [!UICONTROL A/B Test] verksamhet som riktar sig till den önskade målgruppen med 100 % trafiktilldelning, vilket visas nedan:

  ![Prioriterad upplevelse](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **Prioriteten för upplevelserna definieras av deras ordning (uppifrån och ned) när de visas i dialogrutan [!DNL Target] Gränssnitt.**

  Detta är viktigt att tänka på i scenarier där en besökare kan kvalificera sig för fler än en av era målgrupper. Om du till exempel har två upplevelser: en som är riktad till&quot;USA&quot; och en som är inriktad på&quot;New York&quot;, kvalificerar en besökare som finns i New York sig för båda målgrupperna. Därför måste du se till att&quot;New York&quot;-upplevelsen definieras innan&quot;USA&quot;-upplevelsen i [!DNL Target] Gränssnitt. Detta säkerställer att den mer målinriktade&quot;New York&quot;-upplevelsen har högre prioritet, vilket visas i följande exempel:

  ![Prioritet NY > US](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
