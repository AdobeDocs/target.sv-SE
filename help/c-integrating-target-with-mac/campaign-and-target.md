---
keywords: Overview and Reference
description: Använd Target med Adobe Campaign för att optimera e-postinnehåll.
title: Integrera Target med Adobe Campaign
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Integrera Target med Adobe Campaign{#integrate-target-with-adobe-campaign}

Använd Target med Adobe Campaign för att optimera e-postinnehåll.

Om du vill optimera e-postinnehållet, till exempel för att visa olika erbjudanden för manliga och kvinnliga mottagare, kan du skapa ett omdirigeringserbjudande i Target och sedan använda Adobe Campaign för att hantera e-posterbjudandena.

Integrationen äger rum när e-postmeddelandet öppnas. När kunden öppnar e-postmeddelandet anropas Target och en dynamisk version av innehållet visas. Innehållet består av en statisk bild som stöds av alla webbläsare. Target spårar reaktionen på erbjudandet på målgrupps- eller sessionsnivå och att data finns tillgängliga i Target-rapporter.

Målet kan spåra följande data:

* Användaragent
* IP-adress
* Geografisk plats
* Segment som är associerat med besökarens ID i Target (med förbehåll för juridiskt godkännande)
* Data från kampanjdata

Det finns flera begränsningar:

* Eftersom bara en bild kan användas kan innehållet inte personaliseras.
* Spårning konsolideras inte i Adobe Campaign.
* Ingen enhetlig användarupplevelse.

   Du måste använda både Target och Campaign för att konfigurera olika delar av integreringen:

   * The rawbox and the experience in Target
   * Leveransen i Campaign

## Innan du börjar {#section_FF19BF1BCA064260930BF6C141313B0E}

Innan du använder Adobe Campaign för att konfigurera dina riktade e-posterbjudanden ska du konfigurera följande i Target:

* Två eller flera Target-omdirigeringserbjudanden

   Se [Skapa omdirigeringserbjudande](/help/c-experiences/c-manage-content/offer-redirect.md).
* En Target-aktivitet med en upplevelse för varje erbjudande och önskat [framgångsmått](/help/c-activities/r-success-metrics/success-metrics.md).

   Se [Omdirigera till en URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Starta aktiviteten i Target innan du ställer in Campaign-delen av integreringen.

## Inkludera ett målerbjudande i ett Adobe Campaign-e-postmeddelande {#section_B201BBE27A704E18AF0D553F35695837}

1. Skapa ett e-postmeddelande i Adobe Campaign.
1. Klicka på **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]** i e-postegenskaperna.
1. Välj standardbilden från de delade resurserna.
1. Ange platsen (rawbox).
1. Lägg till andra beslutsparametrar, t.ex. mottagarens kön.
1. Förhandsgranska e-postmeddelandet och välj minst en mottagare för varje erbjudande (i det här fallet en man och en kvinna).
1. I Campaign definierar du den måledge-server som du använder för att styra aktiviteten och namnet på klienten.
1. Ange det externa konto som används för Experience Cloud så att ni får tillgång till resurserna i Experience Cloud.

Mer information finns i dokumentationen för Adobe Campaign.
