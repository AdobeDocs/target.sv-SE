---
keywords: lägg till användare;hantera användare;användarbehörigheter
description: Lär dig hur du använder Adobe Admin Console för att hantera användare och deras behörigheter och behörigheter i Adobe Target.
title: Hur lägger jag till användare och hanterar behörigheter?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 4251832a5983ea8950e54d52df5d27bf395894e0
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# Användare

Lägg till användare och hantera deras behörigheter i [!DNL Adobe Admin Console].

>[!NOTE]
>
>[!UICONTROL Properties] och [!UICONTROL Permissions] finns som en del av [!DNL Target] Premiumlösning. De är inte tillgängliga i [!DNL Target] Standard utan [!DNL Target] Premiumlicens.
>Du kan se om din organisation har en Standard- eller Premium-licens genom att klicka på [!UICONTROL Administration] länk högst upp i [!DNL Target] Gränssnitt.
>
>* **[!DNL Target]Standardkunder**: Om du ser [!UICONTROL Users] tab ([!UICONTROL Administration > Users]) (och inte **[!UICONTROL Properties]** -fliken) har din organisation en [!DNL Target] Standardlicens. [!DNL Target] Standardkunder bör följa instruktionerna i den här artikeln för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
>
>* **[!DNL Target]Premiumkunder**: Om du ser [!UICONTROL Users] -fliken och [!UICONTROL Properties] tab ([!UICONTROL Administration > Properties]) har din organisation en [!DNL Target] Premiumlicens. [!DNL Target] Premium-kunder bör följa instruktionerna i [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) och [Konfigurera företagsbehörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
>
>Detaljerad information om hur du hanterar användare och behörigheter finns i [Hantera produkter och profiler](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) i *Användarhandbok för Enterprise &amp; Teams*.

När du börjar med [!DNL Adobe Target]hittar du ID:n (som slutar på Adobe.com) som är förifyllda i dina [!DNL Adobe Experience Cloud] konto. Dessa ID:n är för medlemmar i [!DNL Adobe] så att de kan hjälpa dig med ditt nya konto och med din användning av [!DNL Adobe Target], om du behöver hjälp. Kontakta era Adobe-team på vanligt sätt för att få hjälp.

Den nya användaren visas inte på [!UICONTROL Users] sidan tills användaren loggar in med hjälp av sin [!DNL Adobe Experience Cloud] konto och loggar sedan in på [!DNL Target Standard/Premium].

Som standard är alla [!DNL Target] -användare börjar med observatörsbehörigheter.

Administratörsanvändare identifieras i [!UICONTROL Users] lista. Kontakta en av systemadministratörsanvändarna om du behöver ändra åtkomstnivån.

## Visa användarinformation inifrån Target

Du kan visa en lista över dina nuvarande användare i målmiljön, inklusive deras roller per arbetsyta och e-postadresser direkt inifrån Target.

Om du vill visa sidan Användare klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Users]**.

![Användarlista från mål](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Om du vill hantera en befintlig användare eller lägga till nya användare måste du använda [!UICONTROL Adobe Admin Console], enligt nedan.

## Få tillgång till Adobe Admin Console {#access}

För uppgifter som utförs i Adobe Admin Console går du till konsolen genom att följa dessa steg:

1. Från [!DNL Target], klicka **[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**.

   eller

   Gå till [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)loggar du sedan in med din Adobe ID, om du inte redan har loggat in.

1. (Villkorligt) Om du har tillgång till [!DNL Admin Console for Enterprise] för mer än en organisation klickar du på användarens avatar i det högra hörnet eller i det övre navigeringsfältet och väljer önskad organisation.

## Lägg till användare {#add-users}

All användarhantering måste utföras i [!DNL Adobe Admin Console for Enterprise]. Alla dina befintliga användare i [!DNL Target] migreras från [!DNL Target] till [!DNL Admin Console for Enterprise].

1. [I Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), klicka **[!UICONTROL Users]** > **[!UICONTROL Users]** för att skapa nya användare eller redigera befintliga användare.
1. Följ instruktionerna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i *Enterprise User Guide*.

## Skapa användargrupper {#user-groups}

Du kan skapa användargrupper som utvecklare, analytiker, marknadsförare, chefer osv. och sedan tilldela behörigheter för flera Adobe-produkter och arbetsytor. Att utse en ny teammedlem kan vara lika enkelt som att lägga till dem i en viss användargrupp.

1. [I Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), klicka **[!UICONTROL Users]** > **[!UICONTROL User Groups]** för att skapa nya användargrupper eller redigera befintliga grupper.
1. Följ instruktionerna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i *Enterprise User Guide*.

## Ange roller och behörigheter {#roles-permissions}

Endast systemadministratörer kan ange användarroller i [!DNL Target]. En standardgodkännare kan till exempel inte ändra en observatör till en godkännare utan att också ha [!DNL Experience Cloud] Administratörsrättigheter.

Systemadministratörsanvändare måste lägga till användare i systemet. Användare läggs inte till automatiskt. De bjuds in via e-post från [!DNL Experience Cloud] och måste bekräfta sina e-postadresser innan deras konton registreras.

1. [I Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), klicka **[!UICONTROL Products]** väljer du namnet på önskad produkt.

   ![Fliken Produkter](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Klicka på önskad arbetsyta (till exempel Standardarbetsyta).

   ![Standardarbetsyta](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   The [!UICONTROL Users] visas alla användare på den arbetsytan.

   ![konfigurationsanvändare](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Välj önskad behörighetsroll (Godkännare, Redigerare eller observatör) med hjälp av listrutan för varje användare i dialogrutan [!UICONTROL Product Role] kolumn.

   ![Listruta för produktroll](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Roll | Beskrivning |
   |--- |--- |
   | Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | Utgivare | Liknar observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |

Mer information finns i [Hantera produktbehörigheter och roller i Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) i *Enterprise User Guide*.

## Utbildningsvideo: Konfigurera Adobe Target Workspaces ![Självstudiemärke](/help/main/assets/tutorial.png)

Utbildningsmål:

* Få åtkomst till Adobe Admin Console från Adobe Target gränssnitt (tre sätt)
* Konfigurera en arbetsyta i Adobe Admin Console
   * Lägga till användare i arbetsytor
   * Lägga till egenskaper i arbetsytor
* Förstå standardarbetsytor

>[!NOTE]
>
>The [!DNL Target] [!UICONTROL Administration] menygränssnitt (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är i allmänhet korrekt: alternativen kan dock finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
