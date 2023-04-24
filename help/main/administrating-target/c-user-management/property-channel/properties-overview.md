---
keywords: lägg till användare;projekt;användargrupp;egenskaper;arbetsyta;hantera egenskap;at_egenskap;roller;permissions
description: Lär dig hur du lägger till användare i Adobe Target. skapa arbetsytor, användargrupper och egenskaper, uppdatera implementeringen, och ange roller och behörigheter.
title: Hur konfigurerar jag Enterprise-behörigheter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1415'
ht-degree: 0%

---

# Konfigurera företagsbehörigheter

Information om de uppgifter som krävs för att lägga till användare i [!DNL Target] genomförande, skapa arbetsytor, användargrupper och egenskaper, uppdatera [!DNL Target] implementering som innefattar `at_property` parameter; och ange roller och behörigheter.

>[!NOTE]
>
>Egenskaper och behörigheter är tillgängliga som en del av [Mål Premium](/help/main/c-intro/intro.md#premium) lösning. De är inte tillgängliga i [!DNL Target Standard] utan [!DNL Target Premium] licens.

I följande tabell visas de uppgifter du bör utföra för att skapa egenskaper och tilldela användarroller och behörigheter. Se avsnitten nedan för mer information om varje uppgift.

| Uppgift | Utfört i |
|--- |--- |
| 1. Lägg till användare (valfritt) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Skapa en arbetsyta (produktprofil) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Skapa användargrupper (valfritt) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Skapa egenskaper | [!DNL Target] UI |
| 5: Uppdatera implementeringen så att den innehåller `at_property` parameter | [!DNL Target] UI, at.js-funktioner eller taggar i [!DNL Adobe Experience Platform] |
| 6: Ange roller och behörigheter | [!DNL Adobe Admin Console for Enterprise] |

För de uppgifter som utförs i [!DNL Adobe Admin Console for Enterprise]öppnar du konsolen genom att följa dessa steg:

1. I Adobe Target klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Properties]** > **[!UICONTROL Assign Properties to Workspaces]**.

   eller

   Gå till [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > logga in med din Adobe ID, om du inte redan har loggat in.


1. (Villkorligt) Om du har tillgång till [!DNL Admin Console for Enterprise] för mer än en organisation klickar du på användarens avatar i det högra hörnet eller i det övre navigeringsfältet och väljer önskad organisation.

## Steg 1. Lägg till användare (valfritt) {#section_A92AF0F921B743FEB9E9033433BD816A}

När du börjar använda den nya [!UICONTROL Properties] måste all användarhantering utföras i [!DNL Adobe Admin Console for Enterprise]. Alla dina befintliga användare i [!DNL Target] migreras från [!DNL Target] till [!DNL Admin Console for Enterprise].

1. [I Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)klickar du på **[!UICONTROL Users]** överst på sidan > **[!UICONTROL Add Users]** för att skapa nya användare eller redigera befintliga användare.
1. Följ instruktionerna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i *Enterprise User Guide*.

## Steg 2. Skapa en arbetsyta (produktprofil) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Med en arbetsyta (produktprofil) kan en organisation tilldela en viss uppsättning användare till en viss uppsättning egenskaper. På många sätt liknar en arbetsyta en rapportserie i [!DNL Analytics].

Organisationer kan börja dra nytta av funktionerna för Enterprise-behörigheter genom att skapa nya arbetsytor i [!DNL Admin Console], tilldela [!DNL Target] till dessa arbetsytor och flytta användare från standardarbetsytan till dessa nyare, begränsade arbetsytor.

Kunderna kan använda dessa arbetsytor för att åtskilja olika team per region, affärsenhet, per platsavsnitt eller via någon annan metod de väljer.

Användare kan ingå i flera arbetsytor och kan till och med ha olika roller inom varje arbetsyta.

1. I [!DNL Admin Console], klicka **[!UICONTROL Products]** väljer du namnet på önskad produkt.

   ![arbetsyta](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Skapa önskad arbetsyta (produktprofil):

   * **Standardåtkomst:** Alla befintliga aktiviteter sammanfogas till ett enda projekt med namnet&quot;Standardåtkomst&quot;. Detta kommer inte att påverka kunderna. Alla användarroller och -funktioner är desamma som de är före den här ändringen.

      Alla aktiviteter skapade via [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services]och [!DNL Target Classic] kommer också att ingå i arbetsytan &quot;Standardåtkomst&quot;. Du kan för närvarande inte flytta projekt från standardåtkomst till ett annat projekt.

   * **Nya arbetsytor (produktprofiler):** Du kan börja använda de nya behörighetskontrollfunktionerna genom att göra följande:

      * Skapa nya arbetsytor i [!DNL Admin Console for Enterprise].
      * Tilldela målegenskaper till arbetsytorna.

   Du kan använda dessa arbetsytor för att dela upp åtkomsten till olika team efter region, affärsenhet, webbplatsavsnitt eller via någon annan metod som du väljer. Användare kan ingå i flera arbetsytor och ha olika roller inom varje arbetsyta.

1. Följ instruktionerna i [Skapa och hantera produktkonfigurationer](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) i *Enterprise User Guide*.

>[!NOTE]
>Se utbildningsvideon nedan för mer information om hur du konfigurerar arbetsytor.

### Hämta arbetsytans ID {#workspace-id}

Du måste skicka arbetsytans ID för att kunna utnyttja Enterprise Permissions i [Mål-API:er](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html){target=_blank}.

1. I [Adobe Admin Console](https://adminconsole.adobe.com)klickar du på [!UICONTROL Products] klickar du på produkten i den vänstra menyn för att visa PLC-listan (arbetsyta).
1. Klicka på önskad PLC(arbetsyta) och leta sedan reda på &quot;profiler&quot;-ID:t i URL:en enligt nedan.

   ![workspaceID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Steg 3. Skapa användargrupper (valfritt) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Du kan skapa användargrupper som utvecklare, analytiker, marknadsförare, chefer osv. och sedan tilldela behörigheter för flera Adobe-produkter och arbetsytor. Att utse en ny teammedlem kan vara lika enkelt som att lägga till dem i en viss användargrupp.

1. Klicka på Admin Console **[!UICONTROL Users]** överst på sidan > **[!UICONTROL User Groups]** för att skapa nya användargrupper eller redigera befintliga grupper.
1. Följ instruktionerna i [Hantera användare och grupper för en produktkonfiguration](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) i *Enterprise User Guide*.

## Steg 4. Skapa egenskaper {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Egenskaper aktiveras genom att ett specifikt namn/värde-par läggs till som en parameter med ett anrop (Target call, api call, etc.) till Target.

Egenskaperna tillhör specifika kanaler (webb, mobil, e-post och API/annan).

**Tips**: Se utbildningsvideon nedan för mer information om hur du skapar egenskaper.

1. I [!DNL Target], klicka **[!UICONTROL Administration]** > **[!UICONTROL Properties]** för att visa [!UICONTROL Properties] lista.
1. Klicka **Skapa egenskap**.

   Fyll i fälten:

   * **Egenskapsnamn (obligatoriskt):** Ange ett beskrivande namn för egenskapen.
   * **Beskrivning:** Ange en valfri beskrivning för egenskapen.
   * **Kanal:** Välj önskad kanal för egenskapen: Webb, Mobilapp, E-post eller Annat/API (t.ex. en digitalbox eller PlayStation-konsol).

1. Klicka **[!UICONTROL Copy]** för att kopiera koden till Urklipp som du använder när du utför stegen i [5: Uppdatera implementeringen så att parametern at_property inkluderas](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Klicka **[!UICONTROL Save]** när det är klart.

>[!NOTE]
>Se utbildningsvideon nedan för mer information om hur du skapar egenskaper.

## Steg 5: Uppdatera implementeringen så att den inkluderar parametern at_property {#section_9B17A59807A94712BE642942442EBBC8}

Så här använder du [!DNL Target] användarbehörigheter måste du lägga till `at_property` parameter till alla anrop som träffar [!DNL Target] (Målsamtal, api-samtal osv.).

**För att få `at_property` parameterkod:**

1. (Villkorligt) Använd implementeringskoden som du skapade och sparade i Urklipp när du utför stegen i [4. Skapa egenskaper](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) och fortsätta till steg 2.

   eller

   I [!DNL Target], klicka **[!UICONTROL Administration]** > **[!UICONTROL Properties]** för att visa [!UICONTROL Properties] lista.

   1. Håll muspekaren över [!UICONTROL Last Updated] kolumn för den önskade egenskapen som ska visas och klicka på [!UICONTROL Code] ikon.

      ![Kod för hovring av egenskaper](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Högerklicka på den markerade implementeringskoden för att kopiera den till Urklipp.

1. Uppdatera dina [!DNL Target] implementering med den implementeringskod som erhölls i föregående steg.

   Det finns flera sätt att uppdatera [!DNL Target] implementering. Följande metoder kan till exempel användas för webbsidor:

   * **Via en anpassad parameter i taggar i [!DNL Adobe Experience Platform]:**

      Mer information finns i [Lägg till mbox-parametrar](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=en#add-mbox-params) i *Översikt över taggar* dokumentation.

   * **Via funktionen targetPageParamsAll():** Placera följande kod i `<head>` -taggar, ovanför referensen at.js.

      ```javascript
      <script>
       function targetPageParamsAll() {
        return {
         "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
        };
       }
      </script>
      ```

      Mer information om hur du gör detta med at.js finns i [targetPageParamsAll](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparamsall.html?lang=en){target=_blank}.

## Steg 6: Ange roller och behörigheter {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Klicka på Admin Console **[!UICONTROL Products]** väljer du namnet på önskad produkt.

   ![Arbetsyta](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Klicka på namnet på den önskade profilen (till exempel Standardarbetsyta).

   ![Standardarbetsyta](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Klicka på **[!UICONTROL Users]**.

   The [!UICONTROL Users] visas alla användare på den arbetsytan.

   ![konfigurationsanvändare](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Välj önskad behörighetsroll (Godkännare, Redigerare, observatör eller Utgivare) genom att använda listrutan för varje användare i dialogrutan [!UICONTROL Product Role] kolumn.

   ![Listruta för produktroll](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Roll | Beskrivning |
   |--- |--- |
   | Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | Utgivare | Liknar observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |

   Mer information finns i [Hantera produktbehörigheter och roller i Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) i *Enterprise User Guide*.

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

>[!NOTE]
>
>The [!DNL Target] [!UICONTROL Administration] menygränssnitt (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande videofilmer är i allmänhet korrekt: alternativen kan dock finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

### Konfigurera Adobe Target Workspaces (6:55) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon förklaras hur du skapar arbetsytor.

* Få åtkomst till Adobe Admin Console från Adobe Target gränssnitt (3 sätt)
* Konfigurera en arbetsyta i Adobe Admin Console

   * Lägga till användare i arbetsytor
   * Lägga till egenskaper i arbetsytor

* Förstå standardarbetsytor

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### Så här skapar du egenskaper i Adobe Target (3:05) ![Självstudiemärke](/help/main/assets/tutorial.png)

* Så här skapar du en egenskap i [!DNL Adobe Target] gränssnitt
* Generera en egenskapstoken som ska ingå i egenskapsimplementeringen
* Bekanta dig med de tre implementeringsmetoderna:

   * Webb
   * Mobilapp
   * E-post, ange den övre rutan eller API-anrop

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
