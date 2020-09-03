---
keywords: visual experience composer;vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css selectors
description: Konfigurera Adobe Target Visual Experience Composer (VEC) genom att ange dess allmänna inställningar, konfiguration av mobilvisningsruta och CSS-väljare.
title: Konfigurera Adobe Target Visual Experience Composer
feature: administration general
topic: Standard
translation-type: tm+mt
source-git-commit: ee618961faa12a7352aaf9ed1d869f9e5ab39cdd
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---


# Konfigurera Visual Experience Composer

Konfigurera [!DNL Adobe Target] VEC ( [!UICONTROL Visual Experience Composer] Mobile Viport configuration) genom att ange dess allmänna inställningar, konfiguration för mobilvisningsruta och CSS-väljare.

Du öppnar konfigurationssidan genom att klicka [!UICONTROL Visual Experience Composer] > **[!UICONTROL Administration]** **[!UICONTROL Visual Experience Composer].**

>[!NOTE]
>
>Tänk på att inställningarna på den här sidan gäller för hela [!DNL Target] kontot.

![Konfigurationssida för Visual Experience Composer](/help/administrating-target/assets/vec.png)

## Allmänna inställningar

Du kan ange allmänna inställningar för Visual Experience Composer.

![Avsnittet Allmänna inställningar](/help/administrating-target/assets/general-settings.png)

Följande inställningar är tillgängliga:

### Standard-URL

Ange den standardwebbadress som används av [!UICONTROL Visual Experience Composer]. Det här är standardsidan, till exempel hemsidan, som används när du skapar en upplevelse för varje ny aktivitet. Om du inte anger någon standardwebbadress (URL) måste du ange en webbadress (URL) för varje aktivitet när du skapar den.

### Aktivera Förbättrad Experience Composer {#eec}

Möjliggör redigering på iFrame-busting-webbplatser med blandat innehåll. Vissa webbplatser kanske inte är kompatibla med den förbättrade versionen. Avmarkera det här alternativet om du vill återgå till originalet [!UICONTROL Visual Experience Composer]. Aktivitetsleverans på webbplatser påverkas inte av det här valet.

Mer information finns i [Felsöka Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

Du kan även aktivera [!UICONTROL Enhanced Experience Composer] på aktivitetsnivå.

### Läs in blandat innehåll

Aktivera blandat innehåll när du öppnar en webbplats med [!UICONTROL Enhanced Experience Composer] (EEC). Om du aktiverar det här alternativet undviker du den extra kostnaden för att läsa in statiska resurser via [!DNL Target] proxyservrar.

Det här alternativet är användbart om du till exempel:

* Dina CSP-rubriker (Content Security Policy) tillåter inläsning av blandat innehåll utan användning av proxyservrar med EEG aktiverat.
* HTTP-webbplatsens ansikten har ökat inläsningstiden i EES, där JavaScript, bilder o.s.v. tar längre tid att läsa in via proxy.

### Generera ögonblicksbilder av upplevelser i aktivitetsflödesdiagrammet

När du aktiverar ögonblicksbilder av upplevelser genereras miniatyrer för dina upplevelser i aktivitetsarbetsflödesdiagrammet. Om du inaktiverar ögonblicksbilder kan vissa användare få bättre prestanda.

## ![Konfiguration av Premium badge](/help/assets/premium.png) Mobile Viewport

Du kan lägga till enheter som ska användas när du förhandsgranskar upplevelser. Varje enhet har en associerad målgrupp.

![Konfigurationsavsnitt för mobilvisningsport](/help/administrating-target/assets/mobile-viewport-configuration.png)

Klicka **[!UICONTROL Add]**, ange ett beskrivande namn för mobilvisningsrutan, ange bredd och höjd, markera önskat operativsystem och klicka sedan på [!UICONTROL Save].

Mer information om hur du lägger till en mobil visningsruta finns i Konfigurera [för](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)mobilvisningsruta.

## CSS-väljare {#css}

Ange hur CSS-väljare ska [!DNL Target] genereras.

![Avsnittet CSS-väljare](/help/administrating-target/assets/css-selectors.png)

Dessa alternativ hjälper till att [!DNL Target] förstå webbplatsens struktur och generera bättre CSS-väljare för innehållsleverans. Som standard [!DNL Target] genererar väljare baserat på element-ID på sidan. Om bara ett fåtal ID eller ID:n på samma sida används på platsen kan det vara bättre att använda klasser.

Du kan välja ett eller båda av följande alternativ:

### Använd element-ID:n

Avmarkera det här alternativet om samma ID används för flera element eller om element-ID kan ändras vid sidinläsning.

### Använd elementklasser

Som standard använder [!DNL Target] endast element-ID:n. Om sidan är utformad för att använda klasser för att identifiera element, t.ex. en sida som skapats med, [!DNL Adobe Experience Manager]bör du även välja [!UICONTROL Use element classes].

>[!NOTE]
>
>Även om allt har gjorts för att säkerställa noggrannheten bör du vara medveten om att användning av klasser kan orsaka fel. Om du inte väljer något av alternativen påverkas även noggrannheten. Precisionsordningen är ID:n > klasser > inget av alternativen. Se alltid till att du testar sidan för att kontrollera att väljarna är korrekta.

Du kan åsidosätta den här inställningen per aktivitet (klicka på [!UICONTROL Settings] kugghjulsikonen och välj sedan [!UICONTROL CSS Selectors]). Detta är särskilt användbart om du har flera platser som har konfigurerats på olika sätt.

>[!NOTE]
>
>Det går inte att åsidosätta inställningen per aktivitet i [!UICONTROL Automated Personalization] och [!UICONTROL Multivariate Testing] aktiviteter.  Mer information om väljare finns i [Elementväljare som används i Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) .

## Utbildningsvideo: Kontoinställningar (7:33) ![Översikt, märke](/help/assets/overview.png)

Den här videon innehåller information om kontoinställningar.

* Beskriv de kontoinställningar som är tillgängliga i [!DNL Target Standard]

>[!NOTE]
>
>Gränssnittet för [!DNL Target][!UICONTROL Administration] menyer (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är i allmänhet korrekt: alternativen kan dock finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
