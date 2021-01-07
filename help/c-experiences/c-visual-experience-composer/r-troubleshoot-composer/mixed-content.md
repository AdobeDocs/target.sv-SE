---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure;http;https;firefox;internet explorer
description: I vissa webbläsare blockeras visningen av en sida om säkert innehåll blandas med osäkert innehåll.
title: Aktivera blandat innehåll i webbläsaren
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---


# Aktivera blandat innehåll i webbläsaren

Blandat innehåll uppstår om både HTTPS-innehåll (säkert) *och* HTTP-innehåll (osäkert) läses in för att visa samma webbsida och den ursprungliga begäran var säker över HTTPS.

Nya webbläsare kan blockera visningen av en sida eller visa varningsmeddelanden om säkert innehåll blandas med osäkert innehåll.

Om [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Target] försöker öppna en sida som innehåller blandat innehåll visas ett meddelande om hur du inaktiverar blockering i webbläsaren så att du kan öppna en HTTP-webbplats eller en plats med blandade anrop (HTTPS och HTTP).

![varning om blandat innehåll](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Tidigare kunde du utföra några åtgärder i steg 1 i det guidade arbetsflödet i tre steg när du skapade aktiviteter när blandat innehåll inte tilläts. [!DNL Target] blockerar nu åtgärder i steg 1. När det här meddelandet visas måste du aktivera blandat innehåll innan du kan fortsätta skapa aktiviteten.

Webbläsarens säkerhetsinställningar kan blockera blandat innehåll eller osäkert (HTTP) innehåll som läses in till en säker (HTTPS) sida eller ram (t.ex. VEC). Om du inte vill inaktivera säkerhetsinställningarna i webbläsaren måste du ha en HTTPS-webbplats.

Om webbplatsen körs på en osäker domän (HTTP) måste du tillåta VEC att läsa in aktivt blandat innehåll.

>[!NOTE]
>
>Om du tillåter blandat innehåll påverkas endast VEC och inte den aktiva webbplatsen.

Mer information finns i [Blandat innehåll](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) på webbplatsen *Mozilla Developer Network* (MDN).

## Aktivera blandat innehåll i Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Om du besöker en webbplats via en säker anslutning verifierar Chrome att innehållet på webbsidan har överförts på ett säkert sätt.

Se [Den här sidan har osäkert innehåll](https://support.google.com/chrome/answer/1342714?hl=en) i hjälpen för Google Chrome.

Om du använder VEC med den senaste versionen av Chrome (version 79.0.3945.117 eller senare) måste du uppdatera platsinställningarna. Besökare på webbplatsen behöver inte utföra dessa steg.

1. Klicka på låsikonen eller varningsikonen och klicka sedan på **[!UICONTROL Site settings]**.

   ![Webbplatsinställningar](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Bläddra till **[!UICONTROL Insecure content]** och använd sedan listrutan för att ändra &quot;Block (standard)&quot; till &quot;Allow&quot;.

   ![Osäkert innehåll](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Läs in VEC-sidan igen.

## Aktivera blandat innehåll i Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Som standard blockerar Firebox sidor som blandar säkert och osäkert innehåll. Du bör ändra den här inställningen permanent så att den använder [!DNL Target]. Besökare på webbplatsen behöver inte utföra dessa steg.

1. I Firefox anger du `about:config` i adressfältet.
1. Bekräfta varningsmeddelandet som visas av Firefox.

   ![Firefox-varning](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Skriv `block_active` i sökfältet.

   ![Aktiv inställning för Firefox-block](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Dubbelklicka på ` **[!UICONTROL security.mixed_content.block_active_content]**` .

   Värdet ändras från &quot;Sant&quot; till &quot;Falskt&quot;. När värdet visar &quot;Falskt&quot; är du klar.

   ![Firefox-säkerhet](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Vi rekommenderar att du startar om datorn när du har ändrat den här inställningen.

## Aktivera blandat innehåll i Microsoft Edge

Om du besöker en webbplats via en säker anslutning verifierar Edge att innehållet på webbsidan har överförts på ett säkert sätt.

Om du använder VEC med den senaste versionen av Edge måste du uppdatera platsinställningarna. Besökare på webbplatsen behöver inte utföra dessa steg.

1. Klicka på låsikonen eller varningsikonen och klicka sedan på **[!UICONTROL Site Permissions]**.

   ![Webbplatsbehörigheter i Microsoft Edge](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Bläddra till **[!UICONTROL Insecure content]** och använd sedan listrutan för att ändra &quot;Block (standard)&quot; till &quot;Allow&quot;.

   ![Osäkert innehåll](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Läs in VEC-sidan igen.