---
keywords: Översikt och referens
description: Lär dig hur du använder Adobe [!DNL Target]  med Adobe Campaign för att optimera e-postinnehåll.
title: Hur integrerar jag [!DNL Target] med Adobe Campaign?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# Integrera [!DNL Target] med Adobe Campaign

Använd [!DNL Target] med [!DNL Adobe Campaign] för att optimera e-postinnehåll.

Om du vill optimera ditt e-postinnehåll kan du skapa ett omdirigeringserbjudande i [!DNL Target] och sedan använda [!DNL Adobe Campaign] för att hantera e-posterbjudandena. Du kan t.ex. visa olika erbjudanden för män och kvinnor.

Integrationen äger rum när e-postmeddelandet öppnas. När kunden öppnar e-postmeddelandet görs ett anrop till [!DNL Target] och en dynamisk version av innehållet visas. Innehållet består av en statisk bild som stöds av alla webbläsare. [!DNL Target] spårar svaret på erbjudandet på målgrupps- eller sessionsnivå och att data är tillgängliga i [!DNL Target] rapporter.

[!DNL Target] kan spåra följande data:

* Användaragent
* IP-adress
* Geografisk plats
* Segmentet som är associerat med besökarens ID i [!DNL Target] (kräver juridiskt godkännande)
* Data från [!DNL Campaign] Datamart

Det finns flera begränsningar:

* Eftersom bara en bild kan användas kan innehållet inte personaliseras.
* Spårning är inte konsoliderad i [!DNL Adobe Campaign].
* Ingen enhetlig användarupplevelse.

Använd både [!DNL Target] och [!DNL Campaign] för att konfigurera olika delar av integreringen:

* Rita-rutan och upplevelsen i [!DNL Target]

>[!NOTE]
>
>När du använder en radruta och [!DNL Target] ska du läsa det viktiga säkerhetsmeddelandet under [Skapa tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till Target](/help/main/administrating-target/hosts.md#allowlist).

* Leveransen i [!DNL Campaign]

## Innan du börjar {#section_FF19BF1BCA064260930BF6C141313B0E}

Innan du använder [!DNL Adobe Campaign] för att konfigurera dina riktade e-posterbjudanden ska du konfigurera följande i [!DNL Target]:

* Två eller flera omdirigeringserbjudanden för [!DNL Target]

  Se [Skapa omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* En [!DNL Target]-aktivitet med en upplevelse för varje erbjudande och önskat [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md).

  Se [Omdirigera till en URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

Starta aktiviteten i [!DNL Target] innan du konfigurerar [!DNL Campaign]-delen av integreringen.

## Inkludera ett [!DNL Target]-erbjudande i ett [!DNL Adobe Campaign]-e-postmeddelande {#section_B201BBE27A704E18AF0D553F35695837}

1. Skapa ett e-postmeddelande i [!DNL Adobe Campaign].
1. Klicka på **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]** i e-postegenskaperna.
1. Välj standardbilden från de delade resurserna.
1. Ange platsen (rawbox).
1. Lägg till andra beslutsparametrar, t.ex. mottagarens kön.
1. Förhandsgranska e-postmeddelandet och välj minst en mottagare för varje erbjudande (i det här fallet en man och en kvinna).
1. I [!DNL Campaign] definierar du den [!DNL Target] Edge-server som du använder för att styra aktiviteten och namnet på klienten.
1. Ange det externa konto som används för [!DNL Adobe Experience Cloud] så att du kan komma åt resurserna i [!DNL Experience Cloud].

Mer information finns i dokumentationen för [!DNL Adobe Campaign].

## Video: Integrera [!DNL Target] med [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
