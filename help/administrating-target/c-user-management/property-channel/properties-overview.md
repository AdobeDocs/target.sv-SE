---
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
description: Information om de uppgifter som krävs för att lägga till användare i Adobe Target-implementeringen. skapa arbetsytor, användargrupper och egenskaper, uppdatera din Target-implementering så att den innehåller parametern at_property; och ange roller och behörigheter.
title: Konfigurera företagsbehörigheter
subtopic: Getting Started
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
translation-type: tm+mt
source-git-commit: dda60f13ee351428504fcebfbbfb1dd824319d65
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Konfigurera företagsbehörigheter{#configure-enterprise-permissions}

Information om de uppgifter som krävs för att lägga till användare i [!DNL Target] implementeringen. skapa arbetsytor, användargrupper och egenskaper, uppdatera din [!DNL Target] implementering så att den innehåller `at_property` parametern; och ange roller och behörigheter.

>[!NOTE]
>
>Informationen i det här avsnittet har uppdaterats för att ge dig en smygtopp vid de gränssnittsändringar som kommer i Target Standard-/Premium 20.6.1-versionen (juli 2020). Huvuddelen av den information som presenteras i detta avsnitt gäller det aktuella användargränssnittet. alternativen kan dock finnas på något olika platser.

>[!NOTE]
>
>Egenskaper och behörigheter ingår i [Target Premium](/help/c-intro/intro.md#premium) . De finns inte i [!DNL Target Standard] utan [!DNL Target Premium] licens.

I följande tabell visas de uppgifter du bör utföra för att skapa egenskaper och tilldela användarroller och behörigheter. Se avsnitten nedan för mer information om varje uppgift.

| Uppgift | Utfört i |
|--- |--- |
| 1. Lägg till användare (valfritt) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Skapa en arbetsyta (produktprofil) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Skapa användargrupper (valfritt) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Skapa egenskaper | [!DNL Target] UI |
| 5: Uppdatera implementeringen så att den inkluderar `at_property` parametern | [!DNL Target] UI, at.js-funktioner, [!DNL Adobe Launch]eller [!DNL Dynamic Tag Management] |
| 6: Ange roller och behörigheter | [!DNL Adobe Admin Console for Enterprise] |

För de uppgifter som utförs i [!DNL Adobe Admin Console for Enterprise]programmet får du åtkomst till konsolen genom att följa dessa steg:

1. I Adobe Target klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Properties]** > **[!UICONTROL Assign Properties to Workspaces]**.

   eller

   Gå till [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > Logga in med ditt Adobe ID, om du inte redan har loggat in.


1. (Villkorligt) Om du har åtkomst till [!DNL Admin Console for Enterprise] för mer än en organisation klickar du på användaravataren i det högra hörnet eller det övre navigeringsfältet och väljer önskad organisation.

## Steg 1. Lägg till användare (valfritt) {#section_A92AF0F921B743FEB9E9033433BD816A}

När du börjar använda den nya [!UICONTROL Properties] funktionen måste all användarhantering utföras i [!DNL Adobe Admin Console for Enterprise]. Alla dina befintliga användare i [!DNL Target] migreras dock från [!DNL Target] till [!DNL Admin Console for Enterprise].

1. [I Admin Console](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)klickar du på **[!UICONTROL Users]** fliken längst upp på sidan > **[!UICONTROL Add Users]** för att skapa nya användare eller redigera befintliga användare.
1. Följ instruktionerna i [Hantera användare och grupper på Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i användarhandboken för *Enterprise*.

## Steg 2. Skapa en arbetsyta (produktprofil) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Med en arbetsyta (produktprofil) kan en organisation tilldela en viss uppsättning användare till en viss uppsättning egenskaper. På många sätt liknar en arbetsyta en rapportserie i [!DNL Analytics].

Organisationer kan börja dra nytta av funktionerna för Enterprise-behörigheter genom att skapa nya arbetsytor i [!DNL Admin Console], tilldela [!DNL Target] egenskaper till dessa arbetsytor och flytta användare från konfigurationen Standardarbetsyta till dessa nyare, begränsade arbetsytor.

Kunderna kan använda dessa arbetsytor för att åtskilja olika team per region, affärsenhet, per platsavsnitt eller via någon annan metod de väljer.

Användare kan ingå i flera arbetsytor och kan till och med ha olika roller inom varje arbetsyta.

1. I [!DNL Admin Console]klickar du på **[!UICONTROL Products]** och väljer sedan namnet på önskad produkt.

   ![arbetsyta](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Skapa önskad arbetsyta (produktprofil):

   * **Standardåtkomst:** Alla befintliga aktiviteter sammanfogas till ett enda projekt med namnet&quot;Standardåtkomst&quot;. Detta kommer inte att påverka kunderna. Alla användarroller och -funktioner är desamma som de är före den här ändringen.

      Alla aktiviteter som skapas via [!DNL Adobe Experience Manager] (AEM) [!DNL Adobe Mobile Services]och [!DNL Target Classic] ingår även i arbetsytan Standardåtkomst. Du kan för närvarande inte flytta projekt från standardåtkomst till ett annat projekt.

   * **Nya arbetsytor (produktprofiler):** Du kan börja använda de nya behörighetskontrollfunktionerna genom att göra följande:

      * Skapa nya arbetsytor i [!DNL Admin Console for Enterprise].
      * Tilldela Target-egenskaper till arbetsytorna.
   Du kan använda dessa arbetsytor för att dela upp åtkomsten till olika team efter region, affärsenhet, webbplatsavsnitt eller via någon annan metod som du väljer. Användare kan ingå i flera arbetsytor och ha olika roller inom varje arbetsyta.

1. Följ instruktionerna i [Skapa och hantera produktkonfigurationer](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) i *Enterprise-användarhandboken*.

>[!NOTE]
>Se utbildningsvideon nedan för mer information om hur du konfigurerar arbetsytor.

### Hämta arbetsytans ID {#workspace-id}

Du måste skicka arbetsytans ID för att kunna utnyttja Enterprise Permissions i [Target API](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).

1. I [Adobe Admin Console](https://adminconsole.adobe.com)klickar du på [!UICONTROL Products] fliken och sedan på produkten i den vänstra menyn för att visa PLC-listan (arbetsyta).
1. Klicka på önskad PLC(arbetsyta) och leta sedan reda på &quot;profiler&quot;-ID:t i URL:en enligt nedan.

   ![workspaceID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Steg 3. Skapa användargrupper (valfritt) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Du kan skapa användargrupper som utvecklare, analytiker, marknadsförare, chefer osv. och sedan tilldela behörigheter för flera Adobe-produkter och arbetsytor. Att tilldela en ny teammedlem alla behörigheter som krävs för olika Adobe-produkter kan vara lika enkelt som att lägga till dem i en viss användargrupp.

1. I Admin Console klickar du på **[!UICONTROL Users]** fliken längst upp på sidan > **[!UICONTROL User Groups]** för att skapa nya användargrupper eller redigera befintliga grupper.
1. Följ instruktionerna i [Hantera användare och grupper för en produktkonfiguration](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) i *Enterprise-användarhandboken*.

## Steg 4. Skapa egenskaper {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Egenskaper aktiveras genom att ett specifikt namn/värde-par läggs till som en parameter med ett anrop (Target-samtal, api-anrop osv.) till Target.

Egenskaperna tillhör specifika kanaler (webb, mobil, e-post och API/annan).

**Tips**: Se utbildningsvideon nedan för mer information om hur du skapar egenskaper.

1. I [!DNL Target]klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Properties]** för att visa [!UICONTROL Properties] listan.
1. Klicka på **Skapa egenskap**.

   ![Ny egenskap, dialogruta](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   Fyll i fälten:

   * **Egenskapsnamn (obligatoriskt):** Ange ett beskrivande namn för egenskapen.
   * **Beskrivning:** Ange en valfri beskrivning för egenskapen.
   * **Kanal:** Välj önskad kanal för egenskapen: Webb, Mobilapp, E-post eller Annat/API (t.ex. en digitalbox eller PlayStation-konsol).

1. Klicka **[!UICONTROL Copy]** för att kopiera koden till Urklipp som du använder när du utför stegen i [5: Uppdatera implementeringen så att parametern](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)at_property inkluderas.
1. Klicka **[!UICONTROL Save]** när du är klar.

>[!NOTE]
>Se utbildningsvideon nedan för mer information om hur du skapar egenskaper.

## Steg 5: Uppdatera implementeringen så att den inkluderar parametern at_property {#section_9B17A59807A94712BE642942442EBBC8}

Om du vill använda funktionen för [!DNL Target] användarbehörigheter måste du lägga till `at_property` parametern till alla samtal som faller [!DNL Target] (Target-samtal, api-samtal osv.).

**Så här hämtar du`at_property`parameterkoden:**

1. (Villkorligt) Använd implementeringskoden som du skapade och sparade i Urklipp när du utför stegen i [4. Skapa egenskaper](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) och fortsätt till steg 2.

   eller

   I [!DNL Target]klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Properties]** för att visa [!UICONTROL Properties] listan.

   1. Håll muspekaren över [!UICONTROL Last Updated] kolumnen för den önskade egenskap som ska visas och klicka på [!UICONTROL Code] -ikonen.

      ![Kod för hovring av egenskaper](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Högerklicka på den markerade implementeringskoden för att kopiera den till Urklipp.

      ![Egenskapskod](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Uppdatera implementeringen [!DNL Target] med implementeringskoden som du fick i föregående steg.

   Det finns flera sätt att uppdatera din [!DNL Target] implementering. Följande metoder kan till exempel användas för webbsidor:

   * **Via en global parameter i[!DNL Adobe Launch]:**

      Mer information finns i [Lägg till globala Mbox-parametrar](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) i *Adobe Experience Platform Launch* -dokumentationen.

   * **Via en global parameter i[!DNL Dynamic Tag Management]:**

      ![](assets/property_token_2.png)

      Mer information finns i [Globala parametrar - Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target) i produktdokumentationen för *dynamisk tagghantering*.

   * **Via funktionen targetPageParams():** Placera följande kod i <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> -taggar, ovanför referensen at.js eller mbox.js.

      ![](assets/property_token_1.png)

      Mer information om hur du gör detta med at.js finns i [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md).

   * **Via funktionen mboxCreate():**

      ![](assets/property_token_3.png)

      Mer information om hur du gör detta med at.js finns i [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) och [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md).

## Steg 6: Ange roller och behörigheter {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. I Admin Console klickar du på **[!UICONTROL Products]** och väljer sedan önskat produktnamn.

   ![Arbetsyta](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Klicka på namnet på den önskade profilen (till exempel Standardarbetsyta).

   ![Standardarbetsyta](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Klicka på **[!UICONTROL Users]**.

   På [!UICONTROL Users] fliken visas alla användare på den arbetsytan.

   ![konfigurationsanvändare](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Välj önskad behörighetsroll (Godkännare, Redigerare, observatör eller Utgivare) genom att använda listrutan för varje användare i [!UICONTROL Product Role] kolumnen.

   ![Listruta för produktroll](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Roll | Beskrivning |
   |--- |--- |
   | Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | Utgivare | Liknar observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |

   Mer information finns i [Hantera produktbehörigheter och roller i Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) i användarhandboken *för* Enterprise.

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Hur du konfigurerar Target Workspaces (6:55) ![självstudiemärke](/help/assets/tutorial.png)

I den här videon förklaras hur du skapar arbetsytor.

* Få åtkomst till Adobe Admin Console från gränssnittet Adobe Target (3 sätt)
* Konfigurera en arbetsyta i Adobe Admin Console

   * Lägga till användare i arbetsytor
   * Lägga till egenskaper i arbetsytor

* Förstå standardarbetsytor

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### How to Create Properties in Adobe Target (3:05) ![Tutorial badge](/help/assets/tutorial.png)

* Så här skapar du en egenskap i [!DNL Adobe Target] gränssnittet
* Generera en egenskapstoken som ska ingå i egenskapsimplementeringen
* Bekanta dig med de tre implementeringsmetoderna:

   * Webb
   * Mobilapp
   * E-post, ange den övre rutan eller API-anrop

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
