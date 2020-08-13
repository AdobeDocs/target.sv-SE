---
keywords: Overview and Reference
description: Använd Target tillsammans med Adobe Campaign för att optimera e-postinnehåll.
title: Integrera Target med Adobe Campaign
feature: campaign
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---


# Integrera Target med Adobe Campaign{#integrate-target-with-adobe-campaign}

Använd [!DNL Target] med [!DNL Adobe Campaign] för att optimera e-postinnehåll.

Om du vill optimera e-postinnehållet, till exempel för att visa olika erbjudanden för manliga och kvinnliga mottagare, kan du skapa ett omdirigeringserbjudande i [!DNL Target]och sedan använda [!DNL Adobe Campaign] för att hantera e-posterbjudandena.

Integrationen äger rum när e-postmeddelandet öppnas. När kunden öppnar e-postmeddelandet görs ett anrop [!DNL Target] och en dynamisk version av innehållet visas. Innehållet består av en statisk bild som stöds av alla webbläsare. [!DNL Target] spårar reaktionen på erbjudandet på målgrupps- eller sessionsnivå och att data finns tillgängliga i [!DNL Target] rapporter.

Målet kan spåra följande data:

* Användaragent
* IP-adress
* Geografisk plats
* Segment som är associerat med besökarens ID i Target (med förbehåll för juridiskt godkännande)
* Data från [!DNL Campaign] Datamart

Det finns flera begränsningar:

* Eftersom bara en bild kan användas kan innehållet inte personaliseras.
* Spårning konsolideras inte i [!DNL Adobe Campaign].
* Ingen enhetlig användarupplevelse.

   Du måste använda både [!DNL Target] och [!DNL Campaign] för att konfigurera olika delar av integreringen:

   * The rawbox and the experience in [!DNL Target]
   >[!NOTE]
   >
   >När du använder en radruta och [!DNL Target]läser du det viktiga säkerhetsmeddelandet under [Skapa tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till Target](/help/administrating-target/hosts.md#allowlist).

   * Leveransen i [!DNL Campaign]



## Innan du börjar {#section_FF19BF1BCA064260930BF6C141313B0E}

Innan du använder [!DNL Adobe Campaign] för att konfigurera dina riktade e-posterbjudanden ska du göra följande i [!DNL Target]:

* Två eller fler [!DNL Target] omdirigeringserbjudanden

   Se [Skapa omdirigeringserbjudande](/help/c-experiences/c-manage-content/offer-redirect.md).
* En Target-aktivitet med en upplevelse för varje erbjudande och önskat [framgångsmått](/help/c-activities/r-success-metrics/success-metrics.md).

   Se [Omdirigera till en URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Starta aktiviteten i [!DNL Target] innan du ställer in [!DNL Campaign] delen av integreringen.

## Inkludera ett målerbjudande i ett Adobe Campaign-e-postmeddelande {#section_B201BBE27A704E18AF0D553F35695837}

1. Skapa ett e-postmeddelande i [!DNL Adobe Campaign].
1. Klicka på **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]** i e-postegenskaperna.
1. Välj standardbilden från de delade resurserna.
1. Ange platsen (rawbox).
1. Lägg till andra beslutsparametrar, t.ex. mottagarens kön.
1. Förhandsgranska e-postmeddelandet och välj minst en mottagare för varje erbjudande (i det här fallet en man och en kvinna).
1. I [!DNL Campaign]definierar du den [!DNL Target] Edge-server som du använder för att styra aktiviteten och namnet på klienten.
1. Ange det externa konto som används för [!DNL Adobe Experience Cloud] så att du kan komma åt resurserna i [!DNL Experience Cloud].

Mer information finns i [!DNL Adobe Campaign] dokumentationen.
