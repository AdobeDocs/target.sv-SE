---
keywords: webbplatssidor;målwebbplatssidor;målsida;aktuell sida;målsida;föregående sida;målsida;startsida;målstartsida;målstartsida;http-rubrik
description: Lär dig att rikta in dig mot besökare som använder  [!DNL Adobe Target] som finns på en viss sida på din webbplats.
title: Kan jag rikta in besökarna baserat på webbplatssidor?
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 0%

---

# Webbplatssidor

Du kan rikta in dig på besökare med [!DNL Adobe Target] som har åtkomst till en viss sida på din webbplats.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Site Pages]** i rutan för målgruppsbyggaren.

   ![Målgrupp för webbplatssidor](assets/target_site_pages.png)

1. Klicka på listrutan **[!UICONTROL Select]**, välj något av följande alternativ och konfigurera sedan regeln efter behov.

   Vilka alternativ och utvärderare som är tillgängliga i de efterföljande listrutorna i regeln varierar beroende på vilket alternativ du väljer. Följande bild visar de tillgängliga alternativen om du väljer [!UICONTROL Current Page]:

   ![Aktuell sida](assets/current-page.png)

   Följande alternativ är tillgängliga i den inledande listrutan när du väljer [!UICONTROL Select].

   * **[!UICONTROL Current Page]:** Sidan som användaren visar.

     Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * [!UICONTROL URL] (Mer information om hur [!DNL Target] utvärderar URL:er finns i [Vanliga frågor om mål och målgrupper](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

   * **[!UICONTROL Previous Page]:** Sidan som användaren visade innan användaren klickade på den aktuella sidan. Användaren måste klicka från föregående sida till den aktuella sidan för att sidan ska kunna spåras. Föregående sida spåras inte om användaren skriver en ny URL i webbläsaren. Det faktiska innehållet på den här sidan beror på webbplatsens design. Om den aktuella sidan t.ex. visar information om en viss produkt, kan föregående sida vara en kategorisida där besökaren väljer det specifika objektet. En sida som t.ex. visar flera kameror av en viss typ, eller det kan vara hemsidan som leder till den sista sidan.

     Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * [!UICONTROL URL] (Mer information om hur Target utvärderar URL:er finns i [Vanliga frågor om mål och målgrupper](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]

   * **[!UICONTROL Landing Page]:** Landningssidan är den första sidan som besökaren ser när han/hon kommer åt din webbplats. Om besökaren till exempel klickar på en länk på Google som leder till en kategorisida är kategorisidan landningssidan. Om länken leder till din hemsida är startsidan landningssidan. Landningssidan sparas för besökarens session. Du kan rikta dig djupare på webbplatsen baserat på vad besökarens landningssida var i den här sessionen.

     Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * [!UICONTROL URL] (Mer information om hur Target utvärderar URL:er finns i [Vanliga frågor om mål och målgrupper](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

     >[!NOTE]
     >
     >Objektet `landing.url` återställs för en underdomänsändring eller direkt URL-ersättning.

   * **[!UICONTROL HTTP Header]:** Det här alternativet utvärderar informationen i HTTP-huvudet i [!DNL Target]-begäran. Om HTTP-huvudet till exempel innehåller språkinformation kan du skapa en regel som innehåller villkoret `Accept-Language: es` för att rikta till besökare som kommer åt sidan på spanska.

     Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Authorization]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL Connection]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Date]
      * [!UICONTROL Expect]
      * [!UICONTROL From]
      * [!UICONTROL Host]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Proxy-Authorization]
      * [!UICONTROL Range]
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL Upgrade]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL Warning]

   Om du väljer [!UICONTROL Current Page], [!UICONTROL Previous Page] eller [!UICONTROL Landing Page] är alternativen [!UICONTROL Domain] och [!UICONTROL Query] tillgängliga. Tänk på följande när du väljer dessa alternativ:

   * **Domän:** Sidans fullständiga domän. När du anger en domän bör du använda &quot;contains&quot;. &quot;Domänen är lika med facebook.com&quot; accepterar till exempel inte `m.facebook.com` eller `www.facebook.com`. &quot;Domänen innehåller facebook.com&quot; accepterar alla varianter av facebook.com.
   * **Fråga:** Innehållet i URL:en efter det första frågetecknet (?).

     `foo.html?e0a72cb2a2c7`

1. (Valfritt) Ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Done]**.

Du kan också skapa målgrupper för webbplatssidor med hjälp av en egen&quot;användardefinierad frågeparameter&quot; eller&quot;användardefinierad rubrik&quot;.

Använd en:

* Frågeparameter om regeln som valts av användaren är [!UICONTROL Current Page], [!UICONTROL Landing Page] eller [!UICONTROL Previous Page]
* Header om regeln som valts av användaren är en HTTP-rubrik

## Felsökning {#ts}

* För att målgrupper på landningssidor ska fungera på rätt sätt måste förfrågningar ha parametern `mboxReferrer` angiven (för leverans-API:t `context.address.referringUrl` -parametern) som JavaScript-biblioteket at.js tar från sidan med attributet `document.referrer`. Det här `HTMLDocument`-attributet returnerar URI:n för sidan som användaren har navigerat från. Attributets värde är en tom sträng när användaren navigerar direkt till sidan (inte via en länk, utan till exempel via ett bokmärke).

  Om det här beteendet inte matchar dina krav kan du utföra någon av följande åtgärder:

   * Skicka [mbox-parametrar](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=sv-SE){target=_blank} till [!DNL Target] som ska användas för målinriktningsändamål.
   * Använd en [A/B-testaktivitet](/help/main/c-activities/t-test-ab/test-ab.md) i stället för en landningssidaktivitet. A/B-testaktiviteter byter inte upplevelser för samma besökare.
   * Använd en [besökarprofil](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) i stället.

* När du använder &quot;begin/ends with&quot;-utvärderare för strängar som innehåller kommatecken utvärderas dessa strängar som en array med värden där varje värde som avgränsas med kommatecken utvärderas. Om du till exempel har värdet för en rubrik: `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` kvalificerar det för villkor som:
   * börjar med zh,
   * börjar med en,
   * slutar med 0,7,
   * slutar med 0,8.

## Utbildningsvideo: Skapa publiker

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
