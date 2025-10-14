---
keywords: flera målgrupper;upplevelseversioner;målversioner
description: Upptäck hur ni kan inrikta er på olika målgruppssegment med versioner av samma upplevelse i A/B-aktiviteter.
title: Kan jag använda flera Experience-versioner i en A/B-aktivitet?
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 0%

---

# Målgrupper med olika upplevelser i ett A/B-test

Du kan rikta versioner av samma upplevelse till olika målgrupper i [!DNL Adobe Target] A/B-aktiviteter. Du kan konfigurera flera målgrupper för en upplevelse i [!UICONTROL Visual Experience Composer] (VEC) eller i den formulärbaserade Experience Composer.

Besökarna kan växla mellan olika upplevelsegrupper när deras profil ändras. Besökarna sitter inte fast i samma upplevelse under aktivitetens livstid.

Om webbplatsen till exempel använder en enhetlig design för flera sidor eller produkter och du vill använda samma upplevelse för flera målgrupper (till exempel besökare med olika webbläsarspråk), kan du skapa flera versioner av upplevelsen. Du kanske ger engelska och japanska talare samma upplevelse, men den enda skillnaden är att texten presenteras på besökarens språk. Data samlas in för upplevelsen, oavsett språk, så rapporten visar upplevelsens prestanda i stället för versionen.

Utan möjligheten att konfigurera upplevelseversioner måste du skapa olika tester för varje språk (i det här exemplet) och sedan manuellt sammanställa resultaten för att försöka få en uppfattning om hur en upplevelse med båda språken kan fungera. Resultatet blir mindre exakt. För vissa tester är dessa beräkningar kanske inte ens användbara på grund av det sätt besökarna är slumpmässiga.

Genom att skapa olika versioner av en upplevelse får ni mer korrekt information utan att behöva göra manuella beräkningar och antaganden.

## Scenario

Ni testar två upplevelser, en geo-riktad banderoll jämfört med en allmän banderoll. Banderollen för varje geografi måste vara olika, men det övergripande testet är att avgöra om geoanpassning är bättre än att visa generiskt innehåll. Om ni skapar en separat upplevelse för varje plats skulle ni faktiskt mäta hur varje geo fungerar i förhållande till den andra, i stället för om geoanpassning hjälper er att uppnå era framgångsrika mål när de mäts mot den allmänna banderollen.

I det här fallet behöver ni geospecifika versioner av upplevelsen, så att ni kan testa den geo-riktade upplevelsen mot en icke-geo-riktad kontroll.

1. [Skapa en A/B-aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) som vanligt.

   När du konfigurerar en upplevelse som ska ha flera versioner väljer du målgrupp för varje version, vilket visas i följande steg.

1. Välj upplevelsen och klicka sedan på **[!UICONTROL Configure]** > **[!UICONTROL Multiple Audiences]**.

1. Klicka på ikonen **[!UICONTROL Add Audience]** ( ![&#x200B; Lägg till ikon &#x200B;](/help/main/assets/icons/Add.svg) ) i rutan [!UICONTROL Experience Audiences] och välj sedan den första målgrupp du vill ha. Upprepa för varje publik.

   Om målgruppen inte finns än klickar du på [Skapa målgrupp](/help/main/c-target/c-audiences/create-audience.md#task_E18BD77A9A8F4ED0AC50569F94556558) och konfigurerar den.

   Om en besökare kvalificerar sig för mer än en målgrupp returneras innehållet för alla målgrupper, och det sista innehållet i listan återges faktiskt på sidan.

1. Fortsätt att konfigurera aktiviteten.

## Bästa praxis

* Välj ömsesidigt uteslutande målgrupper. Om aktiviteten skapades i VEC och en besökare matchar mer än en målgrupp, returneras innehållet för varje målgrupp med innehållet för målgruppen som listades senast på sidan.
* De målgrupper som definieras i diagrammet kombineras med upplevelsemålgrupperna med ett AND-villkor. För att kunna delta i aktiviteten måste besökaren vara berättigad till aktivitetsgruppen och en av upplevelsemålgrupperna.
* Lägg till samma målgrupper som segment för rapporter. Detta hjälper dig att se testresultaten på den höga upplevelsen A jämfört med B och på den lägre upplevelsen A jämfört med B för bara&quot;browser lang ja_JP&quot;. Detta fungerar endast för [!DNL Target]-baserade rapporter, inte [!DNL Analytics]-baserade rapporter.
