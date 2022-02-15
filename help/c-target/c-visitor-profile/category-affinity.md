---
keywords: tillhörighet;kategoritillhörighet
description: Läs om kategoritillhörighet i [!DNL Adobe Target] som automatiskt hämtar kategorier från ett användarbesök och sedan beräknar användarens tillhörighet för kategorin så att den kan anpassas och segmenteras.
title: Vad är kategoritillhörighet?
feature: Audiences
exl-id: 9478a7fb-e4b5-46d9-be73-b72cb99c3e5e
source-git-commit: fd292f72fbd9a245848bc917c7bfe5d27d43a4b9
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 3%

---

# Kategoritillhörighet

Kategoritillhörighetsfunktionen i [!DNL Adobe Target] hämtar automatiskt de kategorier på webbplatsen som en användare besöker och beräknar sedan användarens tillhörighet för varje kategori så att den kan anpassas och segmenteras. Kategoritillhörighet hjälper till att se till att innehåll är riktat till besökare som är mest benägna att agera på den informationen.

## Överför kategoritillhörighetsinformation till [!DNL Target] {#section_B0C8E46EEBAC4549AD90352A47787D04}

När en användare besöker webbplatsen registreras profilparametrar som är specifika för besökaren i [!DNL Target] databas. Dessa data är knutna till användarens cookie. En användbar parameter är `user.categoryId`, en mbox-parameter som tilldelats på en produktsida. När besökaren fortsätter att bläddra, eller återvänder till en annan session, kan de produktkategorier som en viss användare visar registreras. Du kan även registrera kategoriinformation genom att skicka den som mbox-parameter `user.categoryId` i valfri ruta (inklusive en kapslad ruta), som en URL-parameter `user.categoryId`eller i [!DNL Target] sidparametrar med en global mbox. Mer information finns hos din kontorepresentant.

Separera kategorier med kommatecken för att inkludera ett objekt i flera kategorier. Exempel:

* `user.categoryId=clothing,shoes,nike,running,nike clothing,nike shoes,nike running shoes`

Beroende på hur ofta och hur nyligen besök i dina produktkategorier har gjorts registreras kategoritillhörigheten (om någon) för en användare. Kategoritillhörighet kan användas för att rikta in populationer för dina aktiviteter.

Du kan använda `user.categoryAffinities[]` i ett profilskript för att returnera en array med tillhörigheter som en besökare har fyllt i. Mer information finns i [user.categoryAffinties under Objekt och metoder i profilattribut](/help/c-target/c-visitor-profile/profile-parameters.md#objects).

>[!IMPORTANT]
>
>The `user.categoryId` attributet som används för algoritmen för kategoritillhörighet skiljer sig från `entity.categoryId` attribut som används för [!DNL Adobe Target Recommendations]&#39; produktrekommendationer och innehållsrekommendationer. `user.categoryId` krävs för att spåra en användares favoritkategori. `entity.categoryId` krävs för att basera rekommendationer på den aktuella sidans eller det aktuella objektets kategori. Skicka båda värdena till [!DNL Target] om du vill använda båda funktionerna.

## Affärsärende för kategoritillhörighet {#section_D6FF913E88E6486B8FBCE117CA8B253B}

En besökares aktivitet i en session, t.ex. vilken kategori de oftast ser, kan användas för målinriktning vid efterföljande besök. Varje kategorisida som en besökare visar under en session hämtas, och hans eller hennes favoritkategori beräknas utifrån en nyhet och frekvensmodell. Varje gång besökaren återgår till startsidan kan hjältebildområdet användas för att visa innehåll som hör till användarens favoritkategori.

## Exempel på att använda kategoritillhörighet {#section_A4AC0CA550924CB4875F4F4047554C18}

Anta att ni säljer musikinstrument online och vill rikta säljkampanjer baserat på gitarrer till besökare som redan har uttryckt intresse för gitarrer tidigare. Med kategoritillhörighet kan du skapa erbjudanden som endast visas för besökare med den här kategoritillhörigheten.

## Algoritm för kategoritillhörighet {#section_8B86C7FF50294208866ABF16F07D5EB9}

Algoritmen för kategoritillhörighet fungerar så här:

* Tio poäng för den första kategorin
* Fem poäng för varje kategori som klickas efter den första
* När du klickar på en ny kategori subtraheras 1 från alla kategorier som du tidigare klickat på
* Om du klickar på en kategori (visas) subtraheras inte 1 från alla andra kategorier om du klickar på den igen
* Om man klickar på en sjätte kategori tas den kategori som har lägst poäng i de fem första kategorierna bort från beräkningen
* I slutet av sessionen dividerar du alla värden med 2

### Exempel: algoritm för kategoritillhörighet

Du kan till exempel visa `mens-clothing` kategori, sedan `accessories`sedan `jewelry`sedan `accessories` igen i en session resulterar i följande tillhörigheter:

* `accessories`: 9 (+5 - 1 + 5)

* `mens-clothing`: 8 (+10 - 1 - 1)

* `jewelry`: 5 (+5)

När sessionen avslutas och användaren senare återgår till webbplatsen halveras poängen:

* `accessories`: 4.5 (9/2)

* `mens-clothing`: 4 (8/2)

* `jewelry`: 2.5 (5/2)

Anta att användaren sedan tittar i ordning, `jewelry`, `accessories`, `beauty`, `shoes`och `womens-clothing`:

* `accessories`: 6.5 (4.5 + 5 - 1 - 1 - 1)

* `womens-clothing`: 5 (+5)

* `jewelry`: 4.5 (2.5 + 5 - 1 - 1 - 1)

* `shoes`: 4 (+5 - 1)

* `beauty`: 3 (+5 - 1 - 1)

* `mens-clothing` släpps när du klickar sist på `womens-clothing` som kategorin med lägst poäng med poängen 1 (4 - 1 - 1 - 1)

När sessionen avslutas och användaren senare återgår till webbplatsen halveras poängen:

* `accessories`: 3.3 (6.5/2)

* `womens-clothing`: 2.5 (5/2)

* `jewelry`: 2.3 (4.5/2)

* `shoes`: 2 (4/2)

* `beauty`: 1.5 (3/2)

## Använd kategoritillhörighet för mål {#concept_5750C9E6C97A40F8B062A5C16F2B5FFC}

Följande avsnitt innehåller information som hjälper dig att använda en kategoritillhörighetspublik för att målinrikta en aktivitet.

### Skapa en målgrupp som använder kategoritillhörighet {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. Från **[!UICONTROL Audiences]** lista, klicka på **[!UICONTROL Create Audience]**.

   eller

   Om du vill kopiera en befintlig målgrupp håller du pekaren över den önskade målgruppen i listan Publiker och klickar sedan på ikonen Kopiera. Sedan kan ni redigera målgruppen för att skapa en liknande målgrupp.

1. Skriv ett beskrivande målgruppsnamn.
1. Klicka på **[!UICONTROL + Add Rule]** > **[!UICONTROL Visitor Profile]**.
1. I listrutan **[!UICONTROL Visitor Profile]** väljer du **[!UICONTROL Category Affinity]**.

   ![Besöksprofil > Kategoritillhörighet](assets/affinity.png)

1. Välj önskad kategori:

   ![Kategoritillhörighet > Kategori](assets/affinity-category.png)

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

### Använd kategoritillhörighetspubliken i en aktivitet {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

Du kan använda målgrupper med kategoritillhörighet i alla aktiviteter. Under det guidade arbetsflödet i tre steg, på [!UICONTROL Target] väljer du önskad målgrupp.
