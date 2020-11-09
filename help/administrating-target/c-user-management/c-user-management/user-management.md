---
keywords: add user;manage user;user permissions
description: Du kan lägga till användare och hantera deras behörigheter i Adobe Admin Console.
title: Användare
feature: user management
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---


# Användare{#users}

Du kan lägga till användare och hantera deras behörigheter i [!DNL Adobe Admin Console].

>[!NOTE]
>
>[!UICONTROL Properties] och [!UICONTROL Permissions] funktionaliteten finns som en del av [!DNL Target] Premium-lösningen. De finns inte i [!DNL Target] Standard utan en [!DNL Target] Premium-licens.
>Du kan se om din organisation har en Standard- eller Premium-licens genom att klicka på [!UICONTROL Administration] länken överst i [!DNL Target] användargränssnittet.
>
>* **[!DNL Target]Standardkunder**: Om du ser [!UICONTROL Users] fliken ([!UICONTROL Administration > Users]) (och inte **[!UICONTROL Properties]** fliken) har din organisation en [!DNL Target] standardlicens. [!DNL Target] Standardkunder bör följa instruktionerna i den här artikeln för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Premiumkunder**: Om du ser [!UICONTROL Users] fliken och [!UICONTROL Properties] fliken ([!UICONTROL Administration > Properties]) har din organisation en [!DNL Target] Premium-licens. [!DNL Target] Premium-kunder bör följa instruktionerna i [Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md) och [Konfigurera Enterprise-behörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md) för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
>
>
Mer information om hur du hanterar användare och behörigheter finns i [Hantera produkter och profiler](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) i användarhandboken *för* Enterprise &amp; Teams.

När du börjar med [!DNL Adobe Target]hittar du ID:n (som slutar på Adobe.com) som är förifyllda i ditt [!DNL Adobe Experience Cloud] konto. Dessa ID:n är till för medlemmar i [!DNL Adobe] team så att de kan hjälpa dig med ditt nya konto och använda det [!DNL Adobe Target]om du behöver hjälp. Kontakta era Adobe-team på vanligt sätt för att få hjälp.

Du kommer inte att se den nya användaren på [!UICONTROL Users] sidan förrän användaren loggar in med sitt [!DNL Adobe Experience Cloud] konto och sedan loggar in på [!DNL Target Standard/Premium].

Som standard får alla [!DNL Target] användare observatörsbehörigheter.

Administratörsanvändare identifieras i [!UICONTROL Users] listan. Kontakta en av systemadministratörsanvändarna om du behöver ändra åtkomstnivån.

## Visa användarinformation inifrån Target

Du kan visa en lista över dina nuvarande användare i målmiljön, inklusive deras roller per arbetsyta och e-postadresser direkt inifrån Target.

Om du vill visa sidan Användare klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Users]**.

![Användarlista från mål](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Om du vill hantera en befintlig användare eller lägga till nya användare måste du använda [!UICONTROL Adobe Admin Console]enligt anvisningarna nedan.

## Få tillgång till Adobe Admin Console {#access}

För uppgifter som utförs i Adobe Admin Console går du till konsolen genom att följa dessa steg:

1. From within [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**.

   eller

   Gå till [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)och logga sedan in med din Adobe ID om du inte redan har loggat in.

1. (Villkorligt) Om du har åtkomst till [!DNL Admin Console for Enterprise] för mer än en organisation klickar du på användaravataren i det högra hörnet eller det övre navigeringsfältet och väljer önskad organisation.

## Lägg till användare {#add-users}

All användarhantering måste utföras i [!DNL Adobe Admin Console for Enterprise]. Alla dina befintliga användare i [!DNL Target] migreras dock från [!DNL Target] till [!DNL Admin Console for Enterprise].

1. [I Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)klickar du på **[!UICONTROL Users]** > **[!UICONTROL Users]** för att skapa nya användare eller för att redigera befintliga användare.
1. Följ instruktionerna i [Hantera användare och grupper på Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i användarhandboken för *Enterprise*.

## Skapa användargrupper {#user-groups}

Du kan skapa användargrupper som utvecklare, analytiker, marknadsförare, chefer osv. och sedan tilldela behörigheter för flera Adobe-produkter och arbetsytor. Att utse en ny teammedlem kan vara lika enkelt som att lägga till dem i en viss användargrupp.

1. [I Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)klickar du på **[!UICONTROL Users]** > **[!UICONTROL User Groups]** för att skapa nya användargrupper eller för att redigera befintliga grupper.
1. Följ instruktionerna i [Hantera användare och grupper på Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i användarhandboken för *Enterprise*.

## Ange roller och behörigheter {#roles-permissions}

Endast systemadministratörer kan ange användarroller i [!DNL Target]. En standardgodkännare kan till exempel inte ändra en observatör till en godkännare utan att ha [!DNL Experience Cloud] administratörsbehörighet.

Systemadministratörsanvändare måste lägga till användare i systemet. Användare läggs inte till automatiskt. De bjuds in via e-post från [!DNL Experience Cloud] och måste bekräfta sina e-postadresser innan deras konton registreras.

1. [Klicka på Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)**[!UICONTROL Products]** och välj sedan önskat produktnamn.

   ![Fliken Produkter](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Klicka på önskad arbetsyta (till exempel Standardarbetsyta).

   ![Standardarbetsyta](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   På [!UICONTROL Users] fliken visas alla användare på arbetsytan.

   ![konfigurationsanvändare](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Välj önskad behörighetsroll (Godkännare, Redigerare eller observatör) med hjälp av listrutan för varje användare i [!UICONTROL Product Role] kolumnen.

   ![Listruta för produktroll](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Roll | Beskrivning |
   |--- |--- |
   | Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | Utgivare | Liknar observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |

Mer information finns i [Hantera produktbehörigheter och roller i Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) i användarhandboken *för* Enterprise.

## Utbildningsvideo: Hur du konfigurerar ![självstudiekursen för målarbetsytor](/help/assets/tutorial.png)

Utbildningsmål:

* Få åtkomst till Adobe Admin Console från Adobe Target gränssnitt (tre sätt)
* Konfigurera en arbetsyta i Adobe Admin Console
   * Lägga till användare i arbetsytor
   * Lägga till egenskaper i arbetsytor
* Förstå standardarbetsytor

>[!NOTE]
>
>Gränssnittet för [!DNL Target][!UICONTROL Administration] menyer (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är i allmänhet korrekt: alternativen kan dock finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
