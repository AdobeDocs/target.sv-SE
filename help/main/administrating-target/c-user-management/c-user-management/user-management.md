---
keywords: lägg till användare;hantera användare;användarbehörigheter
description: Lär dig använda [!DNL Adobe Admin Console] hantera användare och deras behörigheter och rättigheter i [!DNL Adobe Target Standard].
title: Hur lägger jag till användare och hanterar behörigheter för en [!DNL Target Standard] Konto?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 0%

---

# Användare

Lägg till användare och hantera deras behörigheter i [!DNL Adobe Admin Console] för [!DNL Target Standard] konto.

>[!NOTE]
>
>[!UICONTROL Properties] och [!UICONTROL Permissions] finns som en del av [!DNL Target Premium] lösning. De är inte tillgängliga i [!DNL Target] Standard utan [!DNL Target] Premiumlicens.
>
>Du kan se om din organisation har en [!UICONTROL Standard] eller [!UICONTROL Premium] genom att klicka på [!UICONTROL Administration] länk högst upp i [!DNL Target] Gränssnitt.
>
>* **[!DNL Target][!UICONTROL Standard] Kunder**: Om [!UICONTROL Users] tab ([!UICONTROL Administration > Users]) (och inte **[!UICONTROL Properties]** -fliken) har din organisation en [!DNL Target] [!UICONTROL Standard] licens. [!DNL Target] [!UICONTROL Standard] ska kunderna följa instruktionerna i den här artikeln för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
>
>* **[!DNL Target]Premiumkunder**: Om [!UICONTROL Users] -fliken och [!UICONTROL Properties] tab ([!UICONTROL Administration > Properties]) har din organisation en [!DNL Target] Premiumlicens. [!DNL Target] Premium-kunder bör följa instruktionerna i [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) och [Konfigurera företagsbehörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
>
>Detaljerad information om hur du hanterar användare och behörigheter finns i [Hantera produkter och profiler](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) i *Användarhandbok för Enterprise &amp; Teams*.

När du börjar med [!DNL Adobe Target], hittar du ID:n (som slutar i Adobe.com) som är förifyllda i [!DNL Adobe Experience Cloud] konto. Dessa ID:n är för medlemmar i [!DNL Adobe] så att de kan hjälpa dig med ditt nya konto och med din användning av [!DNL Adobe Target], om du behöver hjälp. Kontakta era Adobe-team på vanligt sätt för att få hjälp.

Du kommer inte att se nya användare i listan på [!UICONTROL Users] tills de loggar in med sina [!DNL Adobe Experience Cloud] konto och logga sedan in på [!DNL Target].

Som standard är alla [!DNL Target] användare börjar med [!UICONTROL Observer] behörigheter.

Administratörsanvändare identifieras i [!UICONTROL Users] lista. Kontakta en av systemadministratörsanvändarna om du behöver ändra åtkomstnivån.

## Visa användarinformation inifrån [!DNL Target]

Du kan visa en lista över dina nuvarande användare i [!DNL Target] Användargränssnitt, inklusive deras roller per arbetsyta och e-postadresser.

Så här visar du [!UICONTROL Users] sida, klicka **[!UICONTROL Administration]** > **[!UICONTROL Users]**.

![Användarlista från mål](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Om du vill hantera en befintlig användare eller lägga till nya användare måste du använda [!UICONTROL Adobe Admin Console], vilket förklaras nedan.

## Öppna [!DNL Adobe Admin Console] {#access}

För uppgifter som utförs i [!DNL Adobe Admin Console]öppnar du konsolen genom att följa dessa steg:

1. Från [!DNL Target], klicka **[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**.

   eller

   Gå till [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)loggar du sedan in med din Adobe ID, om du inte redan har loggat in.

1. (Villkorligt) Om du har tillgång till [!DNL Admin Console for Enterprise] för mer än en organisation klickar du på användarens avatar i det högra hörnet eller i det övre navigeringsfältet och väljer önskad organisation.

## Lägg till användare {#add-users}

All användarhantering måste utföras i [!DNL Adobe Admin Console for Enterprise]. Alla dina befintliga användare i [!DNL Target] migreras från [!DNL Target] till [!DNL Admin Console for Enterprise].

1. [I ADMIN CONSOLE](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), klicka **[!UICONTROL Users]** > **[!UICONTROL Users]** för att skapa nya användare eller redigera befintliga användare.
1. Följ instruktionerna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i *Enterprise User Guide*.

## Skapa användargrupper {#user-groups}

Du kan skapa användargrupper som utvecklare, analytiker, marknadsförare, chefer och så vidare, och sedan tilldela behörigheter i flera [!DNL Adobe] produkter och arbetsytor. Tilldela en ny teammedlem alla behörigheter som krävs för olika [!DNL Adobe] -produkter kan vara lika enkla som att lägga till dem i en viss användargrupp.

1. [I ADMIN CONSOLE](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), klicka **[!UICONTROL Users]** > **[!UICONTROL User Groups]** för att skapa nya användargrupper eller redigera befintliga grupper.
1. Följ instruktionerna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) i *Enterprise User Guide*.

## Ange roller och behörigheter {#roles-permissions}

Endast systemadministratörer kan ange användarroller i [!DNL Target]. Till exempel en [!UICONTROL Standard] godkännaranvändaren kan inte ändra en observatör till en godkännare utan att också ha [!DNL Experience Cloud] Administratörsrättigheter.

Systemadministratörsanvändare måste lägga till användare i systemet. Användare läggs inte till automatiskt. De bjuds in via e-post från [!DNL Experience Cloud] och måste bekräfta sina e-postadresser innan deras konton registreras.

1. [I ADMIN CONSOLE](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), klicka **[!UICONTROL Products]** väljer du sedan namnet på önskad produkt.

   ![Fliken Produkter](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Klicka på önskad arbetsyta (till exempel Standardarbetsyta).

   ![Standardarbetsyta](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   The [!UICONTROL Users] -fliken visar alla användare på den arbetsytan.

   ![konfigurationsanvändare](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Välj önskad behörighetsroll ([!UICONTROL Approver], [!UICONTROL Editor], [!UICONTROL Observer] eller [!UICONTROL Publisher]) genom att använda listrutan för varje användare i [!UICONTROL Product Role] kolumn.

   ![Listruta för produktroll](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Roll | Beskrivning |
   |--- |--- |
   | [!UICONTROL Approver] | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | [!UICONTROL Editor] | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | [!UICONTROL Observer] | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | [!UICONTROL Publisher] | Liknar [!UICONTROL Observer] roll (kan visa aktiviteter, men inte skapa eller redigera dem). Men [!UICONTROL Publisher] rollen har ytterligare behörighet att aktivera aktiviteter. |

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
>The [!DNL Target] [!UICONTROL Administration] menygränssnitt (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är i allmänhet korrekt, men alternativen kan finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
