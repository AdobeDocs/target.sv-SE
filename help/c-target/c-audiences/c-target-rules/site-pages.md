---
keywords: site pages;target site pages;targeting;current page;target current page;previous page;target previous page;landing page;target landing page;http header
description: Du kan rikta in dig på besökare som finns på en viss sida på webbplatsen.
title: Alternativ för webbsidor i Adobe Target
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 0%

---


# Platssidor{#site-pages}

Du kan rikta in dig på besökare som finns på en viss sida på webbplatsen.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Site Pages]**.

   ![Målgrupper på webbplatssidor](assets/target_site_pages.png)

1. Klicka på listrutan **[!UICONTROL Select]**, välj något av följande alternativ och konfigurera sedan regeln efter behov.

   Vilka alternativ och utvärderare som är tillgängliga i de efterföljande listrutorna i regeln varierar beroende på vilket alternativ du väljer. Följande bild visar de tillgängliga alternativen om du väljer [!UICONTROL Current Page]:

   ![Aktuell sida](/help/c-target/c-audiences/c-target-rules/assets/current-page.png)

   Följande alternativ är tillgängliga i den inledande listrutan när du väljer [!UICONTROL Select].

   * **Aktuell sida:** Den sida som användaren är på just nu.

      Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * URL (Mer information om hur Target utvärderar URL:er finns i [Vanliga frågor om mål och målgrupper](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * Domän
      * Fråga
      * Underdomän
      * Domän på översta nivån
      * Bana
      * Hash-fragment (#)
   * **Föregående sida:** Den sida som användaren var på innan användaren klickade på den aktuella sidan. (Användaren måste klicka från föregående sida till den aktuella sidan för att sidan ska kunna spåras. Föregående sida spåras inte om användaren skriver en ny URL i webbläsaren.) Det faktiska innehållet på den här sidan beror på webbplatsens design. Om den aktuella sidan t.ex. visar information om en viss produkt, kan föregående sida vara en kategorisida där besökaren väljer det specifika objektet (t.ex. en sida som visar flera kameror av en viss typ), eller det kan vara hemsidan som leder till den sista sidan.

      Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * URL (Mer information om hur Target utvärderar URL:er finns i [Vanliga frågor om mål och målgrupper](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * Domän
      * Fråga
      * Underdomän
      * Domän på översta nivån
      * Bana
   * **Landningssida:** Landningssidan är den första sida besökaren ser när han/hon besöker din plats. Om besökaren till exempel klickar på en länk på Google som leder till en kategorisida är kategorisidan landningssidan. Om länken leder till din hemsida är startsidan landningssidan. Landningssidan sparas för besökarens session. Du kan rikta dig djupare på webbplatsen baserat på vad besökarens landningssida var i den här sessionen.

      Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * URL (Mer information om hur Target utvärderar URL:er finns i [Vanliga frågor om mål och målgrupper](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * Domän
      * Fråga
      * Underdomän
      * Domän på översta nivån
      * Bana
      * Hash-fragment (#)

      >[!NOTE]
      >
      >Objektet `landing.url` återställs för en underdomänsändring eller direkt URL-ersättning.

   * **HTTP-huvud:** Det här alternativet utvärderar informationen i HTTP-huvudet i Target-begäran. Om HTTP-huvudet till exempel innehåller språkinformation kan du skapa en regel som innehåller villkoret `Accept-Language: es` för att rikta till besökare som kommer åt sidan på spanska.

      Följande alternativ är tillgängliga i den andra listrutan om du väljer det här alternativet:

      * Acceptera
      * Accept-Charset
      * Acceptera-kodning
      * Acceptera språk
      * Behörighet
      * Cache-Control
      * Anslutning
      * Content-Length
      * Content-MDS
      * Content-Type
      * Datum
      * Förvänta
      * Från
      * Värd
      * If-Match
      * If-Modified-Since
      * If-None-Match
      * Om-Intervall
      * If-Unmodified-Since
      * Max-Forwards
      * Pragma
      * Proxy-Authorization
      * Intervall
      * Referent
      * TE
      * Uppgradera
      * Användaragent
      * Via
      * Varning

   Om du väljer [!UICONTROL Current Page], [!UICONTROL Previous Page] eller [!UICONTROL Landing Page] är alternativen [!UICONTROL Domain] och [!UICONTROL Query] tillgängliga. Tänk på följande när du väljer dessa alternativ:

   * **Domän:** Sidans fullständiga domän. När du anger en domän bör du använda &quot;contains&quot;. &quot;Domänen är lika med facebook.com&quot; accepterar till exempel inte `m.facebook.com` eller `www.facebook.com`. &quot;Domänen innehåller facebook.com&quot; accepterar alla varianter av facebook.com.
   * **Fråga:** Innehållet i URL:en efter det första frågetecknet (?).

      `foo.html?e0a72cb2a2c7`





1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** och ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Save]**.

Du kan också skapa målgrupper för webbplatssidor med hjälp av en egen&quot;användardefinierad frågeparameter&quot; eller&quot;användardefinierad rubrik&quot;.

Använd en:

* Frågeparameter om regeln som användaren väljer är Aktuell sida, Landningssida eller Föregående sida.
* Header om regeln som valts av användaren är en HTTP-rubrik.

enligt nedan:

![](assets/site_pages.png)

## Felsökning {#ts}

* För att en målgrupp på en landningssida ska fungera på rätt sätt måste förfrågningar ha parametern `mboxReferrer` inställd (för leverans-API:t är parametern `context.address.referringUrl`) som JavaScript-biblioteket at at.js tar från sidan med attributet `document.referrer`. Det här `HTMLDocument`-attributet returnerar URI:n för sidan som användaren har navigerat från. Attributets värde är en tom sträng när användaren navigerar direkt till sidan (inte via en länk, utan till exempel via ett bokmärke).

   Om det här beteendet inte matchar dina krav kan du utföra någon av följande åtgärder:

   * Skicka [mbox-parametrar](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) till [!DNL Target] som ska användas för målinriktningsändamål.
   * Använd en [A/B-testaktivitet](/help/c-activities/t-test-ab/test-ab.md) i stället för en landningssidaktivitet. A/B-testaktiviteter byter inte upplevelser för samma besökare.
   * Använd en [besökarprofil](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) i stället.

* När du använder &quot;börjar/slutar med&quot;-utvärderare för strängar som innehåller kommatecken ska du tänka på att dessa
utvärderas som en array med värden där varje värde som avgränsas med kommatecken utvärderas. Om vi till exempel har värdet för en rubrik: `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` uppfyller villkoren:
   * börjar med zh,
   * börjar med en,
   * slutar med 0,7,
   * slutar med 0,8.

## Utbildningsvideo: Skapa målgrupper

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
