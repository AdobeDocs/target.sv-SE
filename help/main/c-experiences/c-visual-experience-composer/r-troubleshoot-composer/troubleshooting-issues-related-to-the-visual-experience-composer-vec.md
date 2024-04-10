---
keywords: Riktad;Visual experience comser;vec;troubleshooting visual experience comser;troubleshooting;tls;tls 1.2
description: Lär dig hur du felsöker problem i [!UICONTROL Visual Experience Composer] (VEC)
title: Hur felsöker jag problem relaterade till [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 7c0d0154b81fbd3f89a82b31cd18541a7f0ea1a7
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%

---

# Felsökning relaterade till [!UICONTROL Visual Experience Composer]

Visningsproblem kan ibland uppstå i [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) på vissa villkor.

## När jag öppnar min webbplats på [!UICONTROL Visual Experience Composer], [!DNL Target] biblioteken läses inte in. (endast VEC) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

[!DNL Target] lägger till två parametrar (`mboxEdit=1` och `mboxDisable=1`) när du öppnar webbplatsen i [!UICONTROL Visual Experience Composer].

Om din webbplats (särskilt Single Page Apps) trimmar parametrar eller tar bort dem när du navigerar från en sida till en annan (utan att behöva läsa in en sida på nytt) visas [!DNL Target] funktionsavbrott och [!DNL Target] biblioteken läses inte in.

Undvik problemet genom att se till att du inte trimmar eller tar bort de här två parametrarna.

## Min sida öppnas inte i EEG eller laddas långsamt. Aktiviteter och upplevelser läses in långsamt i VEC. (endast VEC) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Flera problem kan påverka sidprestanda i [!UICONTROL Target] upplevelsekompositioner. Några vanliga problem är:

* Det finns ingen mbox på sidan.
* Din webbplats använder proxyblockering, vilket innebär att sidan inte kan öppnas i någon av upplevelsedispositionerna.
* Din webbplats tillåter inte att den öppnas i en iFrame.

Om det uppstår problem i [!UICONTROL Enhanced Experience Composer], prova att stänga av [!UICONTROL Enhanced Experience Composer] och använder [!UICONTROL Visual Experience Composer] i stället.

Så här inaktiverar du [!UICONTROL Enhanced Experience Composer], gå till **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** och stänga av **[!UICONTROL Enable Enhanced Experience Composer]** alternativ.

Följande felmeddelande visas för vissa användare i konsolen:

![Felmeddelande för konsol](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Om varken [!UICONTROL Visual Experience Composer] eller [!UICONTROL Enhanced Experience Composer] fungerar, använder ett webbläsartillägg som [!DNL Requestly] ([!DNL Chrome] eller [!DNL Firefox]) eller Ändra svarshuvuden (Firefox) som kan skriva över X-Frames-rubrikalternativen för din plats och tillåta att de läses in iFrames, vilket aktiverar VEC. Om du inte kan använda webbläsartillägg använder du [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Förutom följande information kan du använda [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) for [!DNL Google Chrome].


>[!NOTE]
>
>Dessa plugin-program bör endast användas i samband med VEC-redigering.
>
>För [!DNL Requestly] om du behöver ta bort rubriker gör du något av följande:
>
>* Lägg till URL-regler för den URL-adress som du vill öppna i VEC så att rubriker bara tas bort för dessa URL-adresser.
>
>* Aktivera regeln när du redigerar i VEC och inaktivera regeln när du inte använder VEC.
>
>För [!UICONTROL Modify Response Header] filtillägg ([!DNL Firefox]), eftersom du inte kan lägga till en URL-regel, måste du göra följande:
>
>* Aktivera regeln när du redigerar i VEC och inaktivera regeln när du inte använder VEC.

**Använd [!DNL Requestly] tillägg på [!DNL Chrome] eller [!DNL Firefox]:**

1. Stäng av [!UICONTROL Enhanced Experienced Composer].
1. Installera [!DNL Requestly] webbläsartillägg på [!DNL Chrome] eller [!DNL Firefox].
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
        >Sidhuvuden som ändras via [!DNL Requestly] är versalkänsliga.

      * Ändra **[!UICONTROL Equals]** till **[!UICONTROL Contains]** som villkor för käll-URL:en och ange URL:en för aktiviteten som du försöker läsa in i VEC:n.

     ![chrome_extension, image](assets/chrome_extension.png)

1. Klicka på **[!UICONTROL Save]**.

   ![begärd bild](assets/requestly.png)

   Nu bör du kunna läsa in sidan snabbt med [!UICONTROL Visual Experience Composer].

**Använd [!DNL Modify Response Headers] tillägg på [!UICONTROL Firefox]:**

1. Installera [!UICONTROL Modify Response Headers] på [!DNL Firefox] och starta om webbläsaren.
1. Från [!DNL Firefox] väljer du tillägget Ändra svarshuvuden.
1. Klicka på **[!UICONTROL Preferences]**.
1. Välj **[!UICONTROL Filter]** från [!UICONTROL Action] nedrullningsbar meny.
1. I [!UICONTROL Header Name] fält, ange: **[!UICONTROL X-Frame-Options]**.
1. Upprepa steg 4 och 5 för att lägga till ett filter med **[!UICONTROL x-frame-options]**.
1. Klicka på **[!UICONTROL Add]**.
1. Klicka på **[!UICONTROL Start]**.

![Firefox-tillägg](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

Öppna efter att du har konfigurerat ett tillägg [!DNL Target]. Sidorna ska nu läsas in i [!UICONTROL Visual Experience Composer], även om [!UICONTROL Enhanced Experience Composer] är inaktiverat.

## Min sida visas inte i VEC (endast VEC) {#does-not-load}

* Den senaste versionen av tillägget säkerställer bästa kompatibilitet med VEC: [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  Verifiera om du använder den senaste versionen genom att gå till [!UICONTROL Extensions] > [!UICONTROL Manage Extensions] klicka sedan på [!UICONTROL Details].

* The [!UICONTROL Visual Experience Composer] kräver redigeringsbibliotek för att kunna utföra ändringar på webbsidan. Dessa bibliotek är inbäddade i at.js-biblioteket och hämtas av tillägget från [!DNL Adobe] servrar varje gång VEC används.

  Tillägget hämtar biblioteket at.js oavsett om det är at.js eller [!DNL Adobe Experience Platform Web SDK] finns redan på sidan.

  Kontrollera att inga ogiltiga ändringar har lagts till i de at.js-huvuden som konfigurerats i [!UICONTROL Administration] > [!UICONTROL Implementation] -avsnitt.

* Kontrollera att webbsidan inte blockerar begäranden som är obligatoriska för inläsning när de är inbäddade i en iFrame. Detta inkluderar användning av CSP-direktiv för ramöverordnade eller anpassad JS-kod som är inbäddad på kundens webbplats, meta HTML-taggar eller rubriken för x-frame-options.

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
* Om din webbplats inte kan läsas in i VEC, eller om den fungerar oväntat, är en möjlig åtgärd att acceptera cookies på din webbplats i webbläsaren innan du försöker läsa in webbplatsen i [!DNL Target].

## VEC-värdet visas som brutet när jag använder bläddringsläge. (endast VEC) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

Om du använder bläddringsläge och har åtkomst till en URL som inte har [!DNL Target] implementerade bibliotek ([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}) eller innehåller en bildrutebusterrubrik, visas VEC som brutet. På grund av säkerhetsproblem i webbläsaren [!DNL Target] kan inte komma åt den URL du navigerade till eller så uppdateras inte VEC-URL:en konsekvent om sidan läses in.

Problemet inträffar eftersom VEC läser in webbsidan i en `<iframe>`. De aktuella säkerhetsfunktionerna i webbläsarna förhindrar [!DNL Target] Gränssnittet kan inte komma åt elementen i den angivna bildrutan på grund av principen för samma ursprung. Webbläsare blockerar skript som försöker få åtkomst till en bildruta med en annan ursprung och som innehåller information som `location.href`.

Du måste använda den nya [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) (rekommenderas) eller [gammalt tillägg](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) för att injicera [!DNL Target] Bibliotek på sidorna för att kunna bläddra optimalt.

## Problem orsakade av CSS-konflikter i [!UICONTROL Visual Experience Composer]

Kontrollera om det finns några CSS-filer som kan påverka synligheten när webbsidan läses in i redigeraren. Använd till exempel `overflow: hidden` på sidans brödtext kan leda till rullningsproblem eller utlösa klickhändelser som kan störa menyn för redigering.
