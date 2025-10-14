---
keywords: Visual experience disposition;vec;default url;enhanced experience disposition;eec;mixcontent;experience snapshots;mobile view port;css;css selections
description: Lär dig hur du konfigurerar Adobe [!DNL Target] Visual Experience Composer (VEC) genom att ange dess allmänna inställningar, konfiguration för mobilvisningsruta och CSS-väljare.
title: Hur konfigurerar jag Visual Experience Composer (VEC)?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Konfigurera [!UICONTROL Visual Experience Composer]

Konfigurera [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) genom att ange dess allmänna inställningar, konfiguration för mobilvisningsruta och CSS-väljare.

Du öppnar konfigurationssidan för [!UICONTROL Visual Experience Composer] genom att klicka på **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer].**

{{permissions-update}}

>[!NOTE]
>
>Observera att inställningarna på den här sidan gäller för hela [!DNL Target]-kontot.

## Allmänna inställningar

Du kan ange allmänna inställningar för [!UICONTROL Visual Experience Composer].

![Avsnittet Allmänna inställningar](/help/main/administrating-target/assets/general-settings.png)

Följande inställningar är tillgängliga:

### Standard-URL

Ange standardwebbadressen som används av [!UICONTROL Visual Experience Composer]. Det här är standardsidan, till exempel hemsidan, som används när du skapar en upplevelse för varje ny aktivitet. Om du inte anger någon standardwebbadress (URL) måste du ange en webbadress (URL) för varje aktivitet när du skapar den.

### Aktivera Förbättrad Experience Composer {#eec}

Möjliggör redigering på iFrame-busting-webbplatser med blandat innehåll. Vissa webbplatser kanske inte är kompatibla med den förbättrade versionen. Avmarkera det här alternativet om du vill återgå till det ursprungliga [!UICONTROL Visual Experience Composer]. Aktivitetsleverans på webbplatser påverkas inte av det här valet.

Mer information finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

Du kan även aktivera [!UICONTROL Enhanced Experience Composer] på aktivitetsnivå.

### Läs in blandat innehåll

Aktivera blandat innehåll när du öppnar en webbplats med [!UICONTROL Enhanced Experience Composer] (EEC). Om du aktiverar det här alternativet undviker du den extra kostnaden för att läsa in statiska resurser via [!DNL Target] proxyservrar.

Det här alternativet är användbart om du till exempel:

* Dina CSP-rubriker (Content Security Policy) tillåter inläsning av blandat innehåll utan användning av proxyservrar med EEG aktiverat.
* Dina HTTP-webbplatser har fått en ökad laddningstid i EES, där JavaScript, bilder och så vidare tar längre tid att läsa in via proxy.

### Generera ögonblicksbilder av upplevelser i aktivitetsflödesdiagrammet

När du aktiverar ögonblicksbilder av upplevelser genereras miniatyrer för dina upplevelser i aktivitetsarbetsflödesdiagrammet. Om du inaktiverar ögonblicksbilder kan vissa användare få bättre prestanda.

## Konfiguration av mobilvisningsruta

>[!NOTE]
>
>[!UICONTROL Mobile Viewport Configuration]-inställningarna är en [Target Premium](/help/main/c-intro/intro.md#premium)-funktion.


Du kan lägga till enheter som ska användas när du förhandsgranskar upplevelser. Varje enhet har en associerad målgrupp.

![Konfigurationsavsnittet Mobile Viewport](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

Klicka på **[!UICONTROL Add]**, ange ett beskrivande namn för mobilvisningsrutan, ange bredd och höjd, markera önskat operativsystem och klicka sedan på [!UICONTROL Save].

Mer information om hur du lägger till en mobilvisningsruta finns i [Konfiguration av mobilvisningsruta](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## CSS-väljare {#css}

Ange hur [!DNL Target] genererar CSS-väljare.

![Avsnittet CSS-väljare](/help/main/administrating-target/assets/css-selectors.png)

Dessa alternativ hjälper [!DNL Target] att förstå webbplatsens struktur för att skapa bättre CSS-väljare för innehållsleverans. Som standard genererar [!DNL Target] väljare baserat på element-ID på sidan. Om bara ett fåtal ID eller ID:n på samma sida används på platsen kan det vara bättre att använda klasser.

Du kan välja ett eller båda av följande alternativ:

### Använd element-ID:n

Avmarkera det här alternativet om samma ID används för flera element eller om element-ID kan ändras vid sidinläsning.

### Använd elementklasser

Som standard använder [!DNL Target] bara element-ID:n. Om sidan är utformad för att använda klasser för att identifiera element, till exempel en sida som skapats med [!DNL Adobe Experience Manager], bör du även välja [!UICONTROL Use element classes].

>[!NOTE]
>
>Även om allt har gjorts för att säkerställa noggrannheten bör du vara medveten om att användning av klasser kan orsaka fel. Om du inte väljer något av alternativen påverkas även noggrannheten. Precisionsordningen är ID:n > klasser > inget av alternativen. Se alltid till att du testar sidan för att kontrollera att väljarna är korrekta.

Du kan åsidosätta den här inställningen per aktivitet (klicka på kugghjulsikonen [!UICONTROL Settings] och välj sedan [!UICONTROL CSS Selectors]). Detta är särskilt användbart om du har flera platser som har konfigurerats på olika sätt.

>[!NOTE]
>
>Det går inte att åsidosätta inställningen per aktivitet i [!UICONTROL Automated Personalization]- och [!UICONTROL Multivariate Testing]-aktiviteter.  Mer information om väljare finns i [Elementväljare som används i Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md).

## Utbildningsvideo: Kontoinställningar (7:33) ![Översikt &#x200B;](/help/main/assets/overview.png)

Den här videon innehåller information om kontoinställningar.

* Beskriv de kontoinställningar som är tillgängliga i [!DNL Target Standard]

>[!NOTE]
>
>Gränssnittet för [!DNL Target] [!UICONTROL Administration]-menyn (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är i allmänhet korrekt, men alternativen kan finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
