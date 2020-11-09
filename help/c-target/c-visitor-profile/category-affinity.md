---
keywords: affinity;category affinity
description: Med kategoritillhörighetsfunktionen i Adobe Target hämtas automatiskt de kategorier som en användare besöker och sedan beräknas användarens tillhörighet för kategorin så att den kan anpassas och segmenteras. Detta bidrar till att säkerställa att innehållet är riktat till besökare som är mest benägna att agera på den informationen.
title: Använd kategoritillhörighet i Adobe Target
feature: visitor profiles
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 3%

---


# Kategoritillhörighet{#category-affinity}

Kategoritillhörighetsfunktionen fångar automatiskt in kategorierna som en användare besöker och beräknar sedan användarens tillhörighet för kategorin så att den kan användas och segmenteras. Detta bidrar till att säkerställa att innehållet är riktat till besökare som är mest benägna att agera på den informationen.

## Överför kategoritillhörighetsinformation till Target {#section_B0C8E46EEBAC4549AD90352A47787D04}

När en användare besöker din webbplats registreras profilparametrar som är specifika för besökaren i [!DNL Target] databasen. Dessa data är knutna till användarens cookie. En särskilt användbar parameter är `user.categoryId`en mbox-parameter som tilldelats på en produktsida. När besökaren fortsätter att bläddra, eller återvänder till en annan session, kan de produktkategorier som en viss användare visar registreras. Du kan också registrera kategoriinformation genom att skicka den som mbox-parameter `user.categoryId` i en mbox (inklusive en kapslad mbox), som en URL-parameter `user.categoryId`eller i Target page-parametrar med en global mbox. Mer information finns hos din kontorepresentant.

Separera kategorier med kommatecken för att inkludera ett objekt i flera kategorier. Exempel:

* `user.categoryId=clothing,shoes,nike,running,nike clothing,nike shoes,nike running shoes`

Beroende på hur ofta och hur nyligen besök i dina produktkategorier har gjorts registreras kategoritillhörigheten (om någon) för en användare. Kategoritillhörighet kan användas för att rikta in populationer för dina aktiviteter.

Du kan använda `user.categoryAffinities[]` i ett profilskript för att returnera en array med tillhörigheterna som en besökare har fyllt i.

>[!IMPORTANT]
>
>Attributet som används för Adobe Target algoritm för kategoritillhörighet skiljer sig från det `user.categoryId` `entity.categoryId` attribut som används för Adobe Target Recommendations rekommendationer för produkter och innehåll. `user.categoryId` krävs för att spåra en användares favoritkategori. `entity.categoryId` krävs för att basera rekommendationer på den aktuella sidans eller det aktuella objektets kategori. Skicka båda värdena till Adobe Target om du vill använda båda funktionerna.

## Affärsärende för kategoritillhörighet {#section_D6FF913E88E6486B8FBCE117CA8B253B}

En besökares aktivitet i en session, t.ex. vilken kategori han eller hon tittar oftast, kan användas för målinriktning vid efterföljande besök. Varje kategorisida som en besökare visar under en session hämtas, och hans eller hennes favoritkategori beräknas utifrån en nyhet och frekvensmodell. Varje gång besökaren återgår till startsidan kan hjältebildområdet användas för att visa innehåll som är relaterat till användarens favoritkategori.

## Exempel på att använda kategoritillhörighet {#section_A4AC0CA550924CB4875F4F4047554C18}

Anta att ni säljer musikinstrument online och vill rikta säljkampanjer baserat på gitarrer till besökare som redan har uttryckt intresse för gitarrer tidigare. Med kategoritillhörighet kan du skapa erbjudanden som endast visas för besökare med den här kategoritillhörigheten.

## Algoritm för kategoritillhörighet {#section_8B86C7FF50294208866ABF16F07D5EB9}

Algoritmen för kategoritillhörighet fungerar så här:

* 10 poäng för den första kategorin som visas
* 5 poäng för varje kategori som klickas efter den första
* När du klickar på en ny kategori subtraheras 1 från alla kategorier som du tidigare klickat på
* Om du klickar på en kategori (visas) tas inte 1 bort från alla andra kategorier om du klickar på den igen
* Om man klickar på en sjätte kategori tas den kategori som har lägst poäng i de fem första kategorierna bort från beräkningen
* I slutet av sessionen dividerar du alla värden med 2

### Exempel: algoritm för kategoritillhörighet

Om du till exempel visar `mens-clothing` kategorin `accessories`och sedan `jewelry`sedan `accessories` igen i en session får du följande tillhörigheter:

* `accessories`: 9 (+5 – 1 + 5)

* `mens-clothing`: 8 (+10 – 1 – 1)

* `jewelry`: 5 (+5)

När sessionen avslutas och användaren senare återgår till webbplatsen halveras poängen:

* `accessories`: 4.5 (9/2)

* `mens-clothing`: 4 (8/2)

* `jewelry`: 2.5 (5/2)

Anta att användaren sedan visar, i ordning, `jewelry`, `accessories`, `beauty`, `shoes`och `womens-clothing`:

* `accessories`: 6.5 (4.5 + 5 – 1 – 1 - 1)

* `womens-clothing`: 5 (+5)

* `jewelry`: 4.5 (2.5 + 5 – 1 – 1 - 1)

* `shoes`: 4 (+5 – 1)

* `beauty`: 3 (+5 – 1 - 1)

* `mens-clothing` tas bort efter det sista klicket i `womens-clothing` kategorin med det lägsta poängvärdet 1 (4 - 1 - 1 - 1)

När sessionen avslutas och användaren senare återgår till webbplatsen halveras poängen:

* `accessories`: 3.3 (6.5/2)

* `womens-clothing`: 2.5 (5/2)

* `jewelry`: 2.3 (4.5/2)

* `shoes`: 2 (4/2)

* `beauty`: 1.5 (3/2)

## Använd kategoritillhörighet för mål {#concept_5750C9E6C97A40F8B062A5C16F2B5FFC}

Information som hjälper er att använda en [!UICONTROL Category Affinity] målgrupp för målinriktning i en aktivitet.

Detta avsnitt innehåller följande information:

* [Skapa en publik som ska använda kategoritillhörighet](/help/c-target/c-visitor-profile/category-affinity.md#section_A27C600BBA664FE7A74F8FE076B78F40)
* [Använd målgruppen för kategoritillhörighet i en aktivitet](/help/c-target/c-visitor-profile/category-affinity.md#section_91526B942D1B4AEBB8FCDF4EBFF931CF)

## Skapa en målgrupp som använder kategoritillhörighet {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. From the **[!UICONTROL Audiences]** list, click **[!UICONTROL + Create Audience]**.

   eller

   Om du vill kopiera en befintlig målgrupp håller du pekaren över den önskade målgruppen i listan Publiker och klickar sedan på ikonen Kopiera. Sedan kan ni redigera målgruppen för att skapa en liknande målgrupp.

1. Skriv ett beskrivande målgruppsnamn.
1. Klicka på **[!UICONTROL + Add Rule]** > **[!UICONTROL Visitor Profile]**.
1. I listrutan **[!UICONTROL Visitor Profile]** väljer du **[!UICONTROL Category Affinity]**.

   ![Besöksprofil > Kategoritillhörighet](assets/affinity.png)

1. Välj önskad kategori:

   ![Kategoritillhörighet > Kategori](/help/c-target/c-visitor-profile/assets/affinity-category.png)

   Kategorierna är:

   * Favoritkategori
   * Första kategorin
   * Andra kategorin
   * Tredje kategorin
   * Fjärde kategorin
   * Femte kategorin

   Alternativen &quot;Favoritkategori&quot; och &quot;Första kategori&quot; är likvärdiga.

1. Välj utvärderaren:

   * Innehåller (skiftlägesokänslig)
   * Innehåller inte (skiftlägesokänslig)
   * Lika med

1. Ange varje nytt värde på en separat rad (till exempel &quot;skor&quot;).
1. Klicka på **[!UICONTROL Save]**.

## Använd kategoritillhörighetspubliken i en aktivitet {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

Du kan använda målgrupper för kategoritillhörighet i alla aktiviteter. Under det guidade arbetsflödet i tre steg väljer du önskad målgrupp i steget Mål.
