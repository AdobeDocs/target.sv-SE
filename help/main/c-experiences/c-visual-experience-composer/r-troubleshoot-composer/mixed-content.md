---
keywords: blandat innehåll;säkert;osäkert;krom;felsökning;vec;visual experience comser;unsecure;http;https;firefox;internet explorer
description: Lär dig hur du aktiverar blandat innehåll i  [!DNL Chrome], [!DNL Firefox] och [!DNL Edge].
title: Aktivera blandat innehåll i webbläsaren
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: c5b43faa2fc55c2c8737e586cfdfaa1444a05880
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Aktivera blandat innehåll i webbläsaren

Blandat innehåll inträffar om den ursprungliga begäran är säker över HTTPS, men HTTPS *och* HTTP-innehåll läses in för att visa webbsidan. HTTPS-innehåll är säkert. HTTP-innehållet är osäkert.

Nya webbläsare kan blockera visningen av en sida eller visa varningsmeddelanden om säkert innehåll blandas med osäkert innehåll.

Ett varningsmeddelande visas om [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] försöker öppna en sida med blandat innehåll. Det här meddelandet informerar dig om hur du inaktiverar blockering i webbläsaren. Om du inaktiverar blockering kan du öppna en HTTP-webbplats eller en plats med blandat innehåll (HTTPS och HTTP).

![Varning om blandat innehåll](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Tidigare kunde du utföra några åtgärder i steg 1 i det guidade arbetsflödet i tre steg när du skapade aktiviteter när blandat innehåll inte tilläts. [!DNL Target] blockerar nu åtgärder i steg 1. När det här meddelandet visas måste du aktivera blandat innehåll innan du kan fortsätta skapa aktiviteten.

Webbläsarens säkerhetsinställningar kan blockera blandat innehåll eller osäkert (HTTP) innehåll som läses in till en säker (HTTPS) sida eller ram (till exempel VEC). Om du inte vill inaktivera säkerhetsinställningarna i webbläsaren måste du ha en HTTPS-webbplats.

Om webbplatsen körs på en osäker domän (HTTP) måste du tillåta VEC att läsa in aktivt blandat innehåll.

>[!IMPORTANT]
>
>Om du tillåter blandat innehåll påverkas endast VEC och inte den aktiva webbplatsen.

Mer information finns i [Blandat innehåll](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) på webbplatsen *Mozilla Developer Network* (MDN).

## Aktivera blandat innehåll i [!DNL Google Chrome] {#task_FF297A08F66E47A588C14FD67C037B3A}

Om du besöker en webbplats via en säker anslutning verifierar [!DNL Chrome] att innehållet på webbsidan har överförts på ett säkert sätt.

Se [Hantera varningar om osäkra webbplatser](https://support.google.com/chrome/answer/99020?hl=en) i hjälpen för Google Chrome.

Om du använder VEC med den senaste versionen av [!DNL Chrome] (version 79.0.3945.117 eller senare) måste du uppdatera platsinställningarna. Besökare på webbplatsen behöver inte utföra dessa steg.

1. Klicka på låsikonen (försiktighet) och klicka sedan på **[!UICONTROL Site settings]**.

   ![Webbplatsinställningar](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Bläddra till **[!UICONTROL Insecure content]** och använd sedan listrutan för att ändra &quot;Blockera (standard)&quot; till &quot;Tillåt&quot;.

   ![Osäkert innehåll](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Läs in VEC-sidan igen.

## Aktivera blandat innehåll i [!DNL Mozilla Firefox] {#task_5448763B8DC941FD80F84041AEF0A14D}

Som standard blockerar [!DNL Firebox] sidor som blandar säkert och osäkert innehåll. Du bör ändra den här inställningen permanent så att den använder [!DNL Target]. Besökare på webbplatsen behöver inte utföra dessa steg.

1. I Firefox anger du `about:config` i adressfältet.
1. Bekräfta varningsmeddelandet som visas av [!DNL Firefox].

   ![Firefox-varning](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Skriv `block_active` i sökfältet.

   ![Firefox-blockaktiv inställning](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Dubbelklicka på ` **[!UICONTROL security.mixed_content.block_active_content]**` .

   Värdet ändras från &quot;Sant&quot; till &quot;Falskt&quot;. När värdet visar &quot;Falskt&quot; är du klar.

   ![Firefox-säkerhet](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. Starta om datorn när du har ändrat den här inställningen.

## Aktivera blandat innehåll i [!DNL Microsoft Edge]

Om du besöker en webbplats via en säker anslutning verifierar [!DNL Edge] att innehållet på webbsidan har överförts på ett säkert sätt.

Om du använder VEC med den senaste versionen av [!DNL Edge] måste du uppdatera platsinställningarna. Besökare på webbplatsen behöver inte utföra dessa steg.

1. I [!DNL Edge] klickar du på **[!DNL Microsoft Edge]** i menyraden, **[!UICONTROL Settings]**, sedan på **Cookies och Site Permissions** .

1. Bläddra till **[!UICONTROL Insecure content]**.

1. Klicka på **[!UICONTROL Insecure content]**, klicka sedan på **[!UICONTROL Add]** bredvid **[!UICONTROL Allow]**, lägg till platsen där osäkert innehåll ska tillåtas och klicka sedan på **[!UICONTROL Add]**.

1. Läs in VEC-sidan igen.
