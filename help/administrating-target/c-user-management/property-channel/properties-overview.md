---
keywords: lägg till användare;projekt;användargrupp;egenskaper;arbetsyta;hantera egenskap;at_egenskap;roller;permissions
description: Lär dig hur du lägger till användare i Adobe Target. skapa arbetsytor, användargrupper och egenskaper, uppdatera implementeringen, och ange roller och behörigheter.
title: Hur konfigurerar jag Enterprise-behörigheter?
feature: Administration och konfiguration
role: Administrator
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 0%

---

# ![](/help/assets/premium.png) PREMIUMConfigurera företagsbehörigheter

Information om de uppgifter som krävs för att lägga till användare i din [!DNL Target]-implementering; skapa arbetsytor, användargrupper och egenskaper, uppdatera din [!DNL Target]-implementering så att den innehåller parametern `at_property`; och ange roller och behörigheter.

>[!NOTE]
>
>Egenskaper och behörigheter är tillgängliga som en del av [Target Premium](/help/c-intro/intro.md#premium)-lösningen. De är inte tillgängliga i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.

I följande tabell visas de uppgifter du bör utföra för att skapa egenskaper och tilldela användarroller och behörigheter. Se avsnitten nedan för mer information om varje uppgift.

| Uppgift | Utfört i |
|--- |--- |
| 1. Lägg till användare (valfritt) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Skapa en arbetsyta (produktprofil) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Skapa användargrupper (valfritt) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Skapa egenskaper | [!DNL Target] UI |
| 5: Uppdatera implementeringen så att den inkluderar parametern `at_property` | [!DNL Target] UI, at.js-funktioner eller  [!DNL Adobe Experience Platform Launch] |
| 6: Ange roller och behörigheter | [!DNL Adobe Admin Console for Enterprise] |

För de uppgifter som utförs i [!DNL Adobe Admin Console for Enterprise] går du till konsolen genom att följa dessa steg:

1. I Adobe Target klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Properties]** > **[!UICONTROL Assign Properties to Workspaces]**.

   eller

   Gå till [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > logga in med din Adobe ID, om du inte redan har loggat in.


1. (Villkorligt) Om du har åtkomst till [!DNL Admin Console for Enterprise] för mer än en organisation klickar du på användarens avatar i det högra hörnet eller i det övre navigeringsfältet och väljer önskad organisation.

## Steg 1. Lägg till användare (valfritt) {#section_A92AF0F921B743FEB9E9033433BD816A}

När du börjar använda den nya [!UICONTROL Properties]-funktionen måste all användarhantering utföras i [!DNL Adobe Admin Console for Enterprise]. Alla dina befintliga användare i [!DNL Target] migreras från [!DNL Target] till [!DNL Admin Console for Enterprise].

1. [Klicka på ](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)fliken längst upp på Admin Console **[!UICONTROL Users]**  för  **[!UICONTROL Add Users]** att skapa nya användare eller redigera befintliga användare.
1. Följ instruktionerna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i *företagsanvändarhandboken*.

## Steg 2. Skapa en arbetsyta (produktprofil) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Med en arbetsyta (produktprofil) kan en organisation tilldela en viss uppsättning användare till en viss uppsättning egenskaper. På många sätt liknar en arbetsyta en rapportserie i [!DNL Analytics].

Organisationer kan börja dra nytta av funktionerna för Enterprise-behörigheter genom att skapa nya arbetsytor i [!DNL Admin Console], tilldela [!DNL Target]-egenskaper till dessa arbetsytor och flytta användare från konfigurationen för standardarbetsytan till dessa nyare, begränsade arbetsytor.

Kunderna kan använda dessa arbetsytor för att åtskilja olika team per region, affärsenhet, per platsavsnitt eller via någon annan metod de väljer.

Användare kan ingå i flera arbetsytor och kan till och med ha olika roller inom varje arbetsyta.

1. Klicka på **[!UICONTROL Products]** i [!DNL Admin Console] och välj sedan namnet på önskad produkt.

   ![arbetsyta](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Skapa önskad arbetsyta (produktprofil):

   * **Standardåtkomst:** Alla befintliga aktiviteter sammanfogas till ett enda projekt med namnet&quot;Standardåtkomst&quot;. Detta kommer inte att påverka kunderna. Alla användarroller och -funktioner är desamma som de är före den här ändringen.

      Alla aktiviteter som skapas via [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] och [!DNL Target Classic] kommer också att ingå i arbetsytan Standardåtkomst. Du kan för närvarande inte flytta projekt från standardåtkomst till ett annat projekt.

   * **Nya arbetsytor (produktprofiler):** Du kan börja använda de nya behörigheterna genom att göra följande:

      * Skapa nya arbetsytor i [!DNL Admin Console for Enterprise].
      * Tilldela målegenskaper till arbetsytorna.

   Du kan använda dessa arbetsytor för att dela upp åtkomsten till olika team efter region, affärsenhet, webbplatsavsnitt eller via någon annan metod som du väljer. Användare kan ingå i flera arbetsytor och ha olika roller inom varje arbetsyta.

1. Följ instruktionerna i [Skapa och hantera produktkonfigurationer](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) i *företagsanvändarhandboken*.

>[!NOTE]
>Se utbildningsvideon nedan för mer information om hur du konfigurerar arbetsytor.

### Hämta arbetsytans ID {#workspace-id}

Du måste skicka arbetsytans ID för att kunna utnyttja företagsbehörigheter i [mål-API:er](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).

1. Klicka på fliken [!UICONTROL Products] i [Adobe Admin Console](https://adminconsole.adobe.com) och klicka sedan på produkten i den vänstra menyn för att visa PLC(arbetsyta)-listan.
1. Klicka på önskad PLC(arbetsyta) och leta sedan reda på &quot;profiler&quot;-ID:t i URL:en enligt nedan.

   ![workspaceID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Steg 3. Skapa användargrupper (valfritt) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Du kan skapa användargrupper som utvecklare, analytiker, marknadsförare, chefer osv. och sedan tilldela behörigheter för flera Adobe-produkter och arbetsytor. Att utse en ny teammedlem kan vara lika enkelt som att lägga till dem i en viss användargrupp.

1. Klicka på fliken **[!UICONTROL Users]** längst upp på Admin Console > **[!UICONTROL User Groups]** för att skapa nya användargrupper eller redigera befintliga grupper.
1. Följ instruktionerna i [Hantera användare och grupper för en produktkonfiguration](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) i *Enterprise User Guide*.

## Steg 4. Skapa egenskaper {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Egenskaper aktiveras genom att ett specifikt namn/värde-par läggs till som en parameter med ett anrop (Target call, api call, etc.) till Target.

Egenskaperna tillhör specifika kanaler (webb, mobil, e-post och API/annan).

**Tips**: Se utbildningsvideon nedan för mer information om hur du skapar egenskaper.

1. I [!DNL Target] klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Properties]** för att visa listan [!UICONTROL Properties].
1. Klicka på **Skapa egenskap**.

   ![Ny egenskap, dialogruta](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   Fyll i fälten:

   * **Egenskapsnamn (obligatoriskt):** Ange ett beskrivande namn för egenskapen.
   * **Beskrivning:** Ange en valfri beskrivning av egenskapen.
   * **Kanal:** Välj önskad kanal för egenskapen: Webb, Mobilapp, E-post eller Annat/API (t.ex. en digitalbox eller PlayStation-konsol).

1. Klicka på **[!UICONTROL Copy]** för att kopiera koden till Urklipp som du använder när du utför stegen i [5: Uppdatera implementeringen till att inkludera parametern at_property](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Klicka på **[!UICONTROL Save]** när du är klar.

>[!NOTE]
>Se utbildningsvideon nedan för mer information om hur du skapar egenskaper.

## Steg 5: Uppdatera implementeringen så att den inkluderar parametern at_property {#section_9B17A59807A94712BE642942442EBBC8}

Om du vill använda funktionen [!DNL Target] för användarbehörigheter måste du lägga till parametern `at_property` i alla anrop som träffar [!DNL Target] (Target call, api call, etc.).

**Så här hämtar du  `at_property` parameterkoden:**

1. (Villkorligt) Använd implementeringskoden som du skapade och sparade i Urklipp när du utför stegen i [4. Skapa egenskaper](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) och fortsätt till steg 2.

   eller

   I [!DNL Target] klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Properties]** för att visa listan [!UICONTROL Properties].

   1. Håll muspekaren över kolumnen [!UICONTROL Last Updated] för att visa den önskade egenskapen och klicka på ikonen [!UICONTROL Code].

      ![Kod för hovring av egenskaper](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Högerklicka på den markerade implementeringskoden för att kopiera den till Urklipp.

      ![Egenskapskod](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Uppdatera din [!DNL Target]-implementering med implementeringskoden som hämtades i föregående steg.

   Det finns flera sätt att uppdatera din [!DNL Target]-implementering. Följande metoder kan till exempel användas för webbsidor:

   * **Via en global parameter i  [!DNL Adobe Launch]:**

      Mer information finns i [Lägg till globala målparametrar](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) i dokumentationen för *Adobe Experience Platform Launch*.

   * **Via funktionen targetPageParams():** Placera följande kod i  `<head>` taggarna ovanför referensen at.js.

      ![](assets/property_token_1.png)

      Mer information om hur du gör detta med at.js finns i [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md).

   * **Via funktionen mboxCreate():**

      ![](assets/property_token_3.png)

      Mer information om hur du gör detta med at.js finns i [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) och [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md).

## Steg 6: Ange roller och behörigheter {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Klicka på **[!UICONTROL Products]** i Admin Console och välj sedan namnet på önskad produkt.

   ![Arbetsyta](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Klicka på namnet på den önskade profilen (till exempel Standardarbetsyta).

   ![Standardarbetsyta](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Klicka på **[!UICONTROL Users]**.

   Fliken [!UICONTROL Users] visar alla användare på den arbetsytan.

   ![konfigurationsanvändare](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Välj önskad behörighetsroll (Godkännare, Redigerare, observatör eller Utgivare) genom att använda listrutan för varje användare i kolumnen [!UICONTROL Product Role].

   ![Listruta för produktroll](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

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
>Menygränssnittet [!DNL Target] [!UICONTROL Administration] (tidigare [!UICONTROL Setup]) har omarbetats för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande videofilmer är i allmänhet korrekt: alternativen kan dock finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

### Konfigurera Adobe Target Workspaces (6:55) ![Självstudiekurs](/help/assets/tutorial.png)

I den här videon förklaras hur du skapar arbetsytor.

* Få åtkomst till Adobe Admin Console från Adobe Target gränssnitt (3 sätt)
* Konfigurera en arbetsyta i Adobe Admin Console

   * Lägga till användare i arbetsytor
   * Lägga till egenskaper i arbetsytor

* Förstå standardarbetsytor

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### Skapa egenskaper i Adobe Target (3:05) ![Självstudiemärke](/help/assets/tutorial.png)

* Så här skapar du en egenskap i [!DNL Adobe Target]-gränssnittet
* Generera en egenskapstoken som ska ingå i egenskapsimplementeringen
* Bekanta dig med de tre implementeringsmetoderna:

   * Webb
   * Mobilapp
   * E-post, ange den övre rutan eller API-anrop

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
