---
keywords: Riktad;Visual experience comser;vec;troubleshooting visual experience comser;troubleshooting;tls;tls 1.2
description: Lär dig hur du felsöker problem i [!UICONTROL Visual Experience Composer] (VEC).
title: Hur felsöker jag problem relaterade till [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 0%

---

# Felsökning av problem relaterade till [!UICONTROL Visual Experience Composer]

Visningsproblem kan ibland uppstå i [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) under vissa villkor.

## När jag öppnar min webbplats i [!UICONTROL Visual Experience Composer] läses inte [!DNL Target]-biblioteken in. (endast VEC) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

+++Information
[!DNL Target] lägger till två parametrar (`mboxEdit=1` och `mboxDisable=1`) när webbplatsen öppnas i [!UICONTROL Visual Experience Composer].

Om din webbplats (särskilt Single Page Apps) trimmar parametrar eller tar bort dem när du navigerar från en sida till en annan (utan att behöva läsa in en sida på nytt), bryts [!DNL Target]-funktionen och [!DNL Target]-biblioteken läses inte in.

Undvik problemet genom att se till att du inte trimmar eller tar bort de här två parametrarna.

+++

## Min sida öppnas inte i EEG eller laddas långsamt. Aktiviteter och upplevelser läses in långsamt i VEC. (endast VEC) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

+++Information
Flera problem kan påverka sidprestanda i [!UICONTROL Target]-funktionsdispositioner. Några vanliga problem är:

* Det finns ingen mbox på sidan.
* Din webbplats använder proxyblockering, vilket innebär att sidan inte kan öppnas i någon av upplevelsedispositionerna.
* Din webbplats tillåter inte att den öppnas i en iFrame.

Om det uppstår problem i [!UICONTROL Enhanced Experience Composer] kan du prova att inaktivera [!UICONTROL Enhanced Experience Composer] och använda [!UICONTROL Visual Experience Composer] i stället.

Om du vill inaktivera [!UICONTROL Enhanced Experience Composer] går du till **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** och inaktiverar alternativet **[!UICONTROL Enable Enhanced Experience Composer]**.

Följande felmeddelande visas för vissa användare i konsolen:

![Konsolens felmeddelande](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Om varken [!UICONTROL Visual Experience Composer] eller [!UICONTROL Enhanced Experience Composer] fungerar kan du använda ett webbläsartillägg som [!DNL Requestly] ([!DNL Chrome] eller [!DNL Firefox]) eller Ändra svarshuvuden (Firefox) som kan skriva över X-bildrutealternativen för platsen och tillåta att de läses in iFrames, vilket aktiverar VEC. Om du inte kan använda webbläsartillägg använder du den [formulärbaserade Experience Composer](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Utöver följande information kan du använda [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper]-tillägget &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) för [!DNL Google Chrome].

>[!NOTE]
>
>Dessa plugin-program bör endast användas i samband med VEC-redigering.
>
>Om du behöver ta bort rubriker för tillägget [!DNL Requestly] bör du göra något av följande:
>
>* Lägg till URL-regler för den URL-adress som du vill öppna i VEC så att rubriker bara tas bort för dessa URL-adresser.
>
>* Aktivera regeln när du redigerar i VEC och inaktivera regeln när du inte använder VEC.
>
>För tillägget [!UICONTROL Modify Response Header] ([!DNL Firefox]) måste du göra följande eftersom du inte kan lägga till en URL-regel:
>
>* Aktivera regeln när du redigerar i VEC och inaktivera regeln när du inte använder VEC.

**Om du vill använda tillägget [!DNL Requestly] på [!DNL Chrome] eller [!DNL Firefox]:**

1. Stäng av [!UICONTROL Enhanced Experienced Composer].
1. Installera webbläsartillägget [!DNL Requestly] på [!DNL Chrome] eller [!DNL Firefox].
1. Öppna tillägget och konfigurera det med följande:
1. Välj **[!UICONTROL Modify headers]**.
1. Ange följande:

   * Regelnamn
   * Ändringsregler

      * Växla **[!UICONTROL Add]** till **[!UICONTROL Remove]**.
      * Växla **[!UICONTROL Request]** till **[!UICONTROL Response]**.
      * Ange&quot;X-Frame-Options&quot; som rubriknamn.
      * Upprepa föregående steg och ange&quot;x-frame-options&quot; som rubriknamn.

        >[!NOTE]
        >
        >Huvuden som manipuleras via [!DNL Requestly] är skiftlägeskänsliga.

      * Ändra **[!UICONTROL Equals]** till **[!UICONTROL Contains]** som villkor för käll-URL:en och ange URL:en för aktiviteten som du försöker läsa in i VEC.

     ![chrome_extension, bild](assets/chrome_extension.png)

1. Klicka på **[!UICONTROL Save]**.

   ![begärd bild](assets/requestly.png)

   Du bör nu kunna läsa in sidan snabbt med [!UICONTROL Visual Experience Composer].

**Så här använder du tillägget [!DNL Modify Response Headers] på [!UICONTROL Firefox]:**

1. Installera [!UICONTROL Modify Response Headers] på [!DNL Firefox] och starta om webbläsaren.
1. Välj tillägget Ändra svarshuvuden i dina [!DNL Firefox] tillägg.
1. Klicka på **[!UICONTROL Preferences]**.
1. Välj **[!UICONTROL Filter]** i listrutan [!UICONTROL Action].
1. Ange [!UICONTROL Header Name] i fältet **[!UICONTROL X-Frame-Options]**.
1. Upprepa steg 4 och 5 om du vill lägga till ett filter med **[!UICONTROL x-frame-options]**.
1. Klicka på **[!UICONTROL Add]**.
1. Klicka på **[!UICONTROL Start]**.

![Firefox-tillägg](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

Öppna [!DNL Target] när du har konfigurerat ett tillägg. Dina sidor ska nu läsas in i [!UICONTROL Visual Experience Composer], även om [!UICONTROL Enhanced Experience Composer] är inaktiverad.

+++

## Min sida visas inte i VEC (endast VEC) {#does-not-load}

+++Information
* Bästa kompatibilitet med VEC säkerställs av den senaste versionen av tillägget: [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  Verifiera om du använder den senaste versionen genom att gå till [!UICONTROL Extensions] > [!UICONTROL Manage Extensions] och sedan klicka på [!UICONTROL Details].

* [!UICONTROL Visual Experience Composer] kräver redigeringsbibliotek för att kunna utföra ändringar på webbsidan. Dessa bibliotek är inbäddade i at.js-biblioteket och hämtas av tillägget från [!DNL Adobe] servrar varje gång VEC används.

  Tillägget hämtar at.js-biblioteket oavsett om at.js eller [!DNL Adobe Experience Platform Web SDK] redan ingår på sidan.

  Kontrollera att inga ogiltiga ändringar har lagts till i de at.js-huvuden som konfigurerats i avsnittet [!UICONTROL Administration] > [!UICONTROL Implementation].

* Kontrollera att webbsidan inte blockerar begäranden som är obligatoriska för inläsning när de är inbäddade i en iFrame. Detta inkluderar användning av CSP-direktiv för ramöverordnade eller anpassad JS-kod som är inbäddad på kundens webbplats, HTML-metataggar eller rubriken för x-frame-options.

* Kontrollera att webbsidans JavaScript inte stör författarbiblioteken. Använd inte eller inkludera filer med följande reserverade namn:

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     Dessutom kan oavsiktlig åsidosättning av variabler eller händelser som definieras i dessa filer leda till problem med VEC.

* Webbläsaren blockerar en osäker sida på en säker webbplats.

  Klicka på ikonen till vänster om URL-adressen i webbläsarens adressfält och klicka på **[!UICONTROL Disable protection on this page]**

* Du angav en ogiltig URL.
* Om webbplatsen inte kan läsas in i VEC, eller om den fungerar oväntat, är en möjlig åtgärd att acceptera cookies på webbplatsen i webbläsaren innan du försöker läsa in webbplatsen i [!DNL Target].

+++

## VEC visas som brutet när jag använder läget [!UICONTROL Browse]. (endast VEC) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

+++Information
Om du använder läget [!UICONTROL Browse] och har åtkomst till en URL som inte har [!DNL Target] bibliotek implementerat ([&#x200B; at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} eller [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}) eller som innehåller ett bildrutebusterhuvud, visas VEC-uttrycket som brutet. På grund av säkerhetsproblem i webbläsaren kan [!DNL Target] inte komma åt den URL som du navigerade till eller så uppdateras inte VEC-URL:en korrekt om sidan läses in.

Problemet inträffar eftersom VEC läser in webbsidan i en `<iframe>`. De aktuella säkerhetsmekanismerna i webbläsare förhindrar att användargränssnittet i [!DNL Target] kommer åt elementen i den angivna bildrutan på grund av principen för samma ursprung. Webbläsare blockerar skript som försöker komma åt en bildruta med en annan ursprung och som innehåller information som `location.href`.

Du måste använda det nya tillägget [Hjälp för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) för att kunna mata in biblioteket [!DNL Target] på sidorna för att kunna bläddra optimalt.

+++

## Problem orsakade av CSS-konflikter i [!UICONTROL Visual Experience Composer]

+++Information
Kontrollera om det finns några CSS-filer som kan påverka synligheten när webbsidan läses in i redigeraren. Om du till exempel använder egenskapen `overflow: hidden` i sidbrödtexten kan det leda till rullningsproblem eller utlösa klickhändelser som kan störa menyn för redigering.

+++
