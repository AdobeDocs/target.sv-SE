---
keywords: lägg till användare;hantera användare;användarbehörigheter
description: Lär dig hur du använder  [!DNL Adobe Admin Console] för att hantera användare och deras behörigheter och rättigheter i  [!DNL Adobe Target Standard].
title: Hur lägger jag till användare och hanterar behörigheter för ett [!DNL Target Standard] konto?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 484971ab0fcd07205935c0fef3ea1484f40c3e96
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# Användare

Lägg till användare och hantera deras behörigheter i [!DNL Adobe Admin Console] för ett [!DNL Target Standard]-konto.

>[!NOTE]
>
>Funktionerna [!UICONTROL Properties] och [!UICONTROL Permissions] är tillgängliga som en del av lösningen [!DNL Target Premium]. De är inte tillgängliga i [!DNL Target] Standard utan en [!DNL Target] Premium-licens.
>
>Du kan se om din organisation har en [!UICONTROL Standard]- eller [!UICONTROL Premium]-licens genom att klicka på länken [!UICONTROL Administration] överst i användargränssnittet för [!DNL Target].
>
>* **[!DNL Target]&#x200B;[!UICONTROL Standard] Kunder**: Om du ser fliken [!UICONTROL Users] ([!UICONTROL Administration > Users]) (och inte fliken **[!UICONTROL Properties]**) har din organisation en [!DNL Target] [!UICONTROL Standard]-licens. [!DNL Target] [!UICONTROL Standard]-kunder bör följa instruktionerna i den här artikeln för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
>
>* **[!DNL Target]Premium-kunder**: Om du ser fliken [!UICONTROL Users] och fliken [!UICONTROL Properties] ([!UICONTROL Administration > Properties]) har din organisation en [!DNL Target] Premium-licens. [!DNL Target] Premium-kunder bör följa instruktionerna i [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) och [Konfigurera företagsbehörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].
>
>Detaljerad information om hur du hanterar användare och behörigheter finns i [Hantera produkter och profiler](https://helpx.adobe.com/se/enterprise/using/manage-products-and-profiles.html) i *användarhandboken för Enterprise &amp; Teams*.

När du börjar med [!DNL Adobe Target] hittar du ID:n (som slutar med Adobe.com) som är förifyllda i ditt [!DNL Adobe Experience Cloud]-konto. Dessa ID:n är till för medlemmar i [!DNL Adobe]-team så att de kan hjälpa dig med ditt nya konto och använda [!DNL Adobe Target] om du behöver hjälp. Kontakta Adobe-teamet på vanligt sätt för att få hjälp.

Nya användare visas inte på sidan [!UICONTROL Users] förrän de loggar in med sitt [!DNL Adobe Experience Cloud]-konto och sedan loggar in på [!DNL Target].

Som standard börjar alla [!DNL Target]-användare med [!UICONTROL Observer]-behörigheter.

Administratörsanvändare identifieras i listan [!UICONTROL Users]. Kontakta en av systemadministratörsanvändarna om du behöver ändra åtkomstnivån.

## Visa användarinformation inifrån [!DNL Target]

Du kan visa en lista över dina aktuella användare i användargränssnittet för [!DNL Target], inklusive deras roller per arbetsyta och e-postadresser.

Om du vill visa sidan [!UICONTROL Users] klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Users]**.

>[!NOTE]
>
>Om du vill hantera en befintlig användare eller lägga till nya användare måste du använda [!UICONTROL Adobe Admin Console], vilket förklaras nedan.

## Åtkomst till [!DNL Adobe Admin Console] {#access}

För uppgifter som utförs i [!DNL Adobe Admin Console] kan du få åtkomst till konsolen genom att följa de här stegen:

1. I [!DNL Target] klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**.

   eller

   Gå till [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) och logga sedan in med din Adobe ID, om du inte redan har loggat in.

1. (Villkorligt) Om du har åtkomst till [!DNL Admin Console for Enterprise] för mer än en organisation klickar du på användaravataren i det högra hörnet eller det övre navigeringsfältet och väljer önskad organisation.

## Lägg till användare {#add-users}

All användarhantering måste utföras i [!DNL Adobe Admin Console for Enterprise]. Alla dina befintliga användare i [!DNL Target] migreras dock från [!DNL Target] till [!DNL Admin Console for Enterprise].

1. [I Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) klickar du på **[!UICONTROL Users]** > **[!UICONTROL Users]** för att skapa nya användare eller redigera befintliga användare.
1. Följ anvisningarna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/se/enterprise/help/users.html) i *Enterprise User Guide*.

## Skapa användargrupper {#user-groups}

Du kan skapa användargrupper, till exempel utvecklare, analytiker, marknadsförare, chefer och så vidare, och sedan tilldela behörigheter för flera [!DNL Adobe]-produkter och arbetsytor. Att tilldela en ny teammedlem alla lämpliga behörigheter för olika [!DNL Adobe]-produkter kan vara lika enkelt som att lägga till dem i en viss användargrupp.

1. [I Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) klickar du på **[!UICONTROL Users]** > **[!UICONTROL User Groups]** om du vill skapa nya användargrupper eller redigera befintliga grupper.
1. Följ anvisningarna i [Hantera användare och grupper i Experience Cloud](https://helpx.adobe.com/se/enterprise/help/users.html) i *Enterprise User Guide*.

## Ange roller och behörigheter {#roles-permissions}

Endast systemadministratörer kan ange användarroller i [!DNL Target]. En [!UICONTROL Standard]-godkännaranvändare kan till exempel inte ändra en observatör till en godkännare utan att ha [!DNL Experience Cloud] administratörsbehörighet.

Systemadministratörsanvändare måste lägga till användare i systemet. Användare läggs inte till automatiskt. De bjuds in via e-post från [!DNL Experience Cloud] och måste bekräfta sina e-postadresser innan deras konton registreras.

>[!NOTE]
>
>Om du vill visa aktiviteter i [!DNL Target] måste användare tilldelas direkt till en arbetsyta med minst rollen [!UICONTROL Observer]. Tilldelning via enbart användargrupper är inte tillräcklig. Vi rekommenderar att du ger användarna tillgång till standardarbetsytan.

1. [I Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) klickar du på **[!UICONTROL Products]** och väljer sedan namnet på önskad produkt.

1. Klicka på önskad arbetsyta (till exempel Workspace som standard).

   Fliken [!UICONTROL Users] visar alla användare på den arbetsytan.

1. Välj önskad behörighetsroll ([!UICONTROL Approver], [!UICONTROL Editor], [!UICONTROL Observer] eller [!UICONTROL Publisher]) genom att använda listrutan för varje användare i kolumnen [!UICONTROL Product Role].

   | Roll | Beskrivning |
   |--- |--- |
   | [!UICONTROL Approver] | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | [!UICONTROL Editor] | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | [!UICONTROL Observer] | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | [!UICONTROL Publisher] | Liknar rollen [!UICONTROL Observer] (kan visa aktiviteter, men inte skapa eller redigera dem). Rollen [!UICONTROL Publisher] har dock ytterligare behörighet att aktivera aktiviteter. |

Mer information finns i [Hantera produktbehörigheter och roller i Admin Console](https://helpx.adobe.com/se/enterprise/help/manage-permissions-and-roles.html) i *Enterprise-användarhandboken*.

## Utbildningsvideo: Så här konfigurerar du Adobe Target Workspaces ![Självstudiekurs](/help/main/assets/tutorial.png)

Utbildningsmål:

* Få åtkomst till Adobe Admin Console från Adobe Target gränssnitt (tre sätt)
* Konfigurera en arbetsyta i Adobe Admin Console
   * Lägga till användare i arbetsytor
   * Lägga till egenskaper i arbetsytor
* Förstå standardarbetsytor

>[!NOTE]
>
>Gränssnittet för [!DNL Target] [!UICONTROL Administration]-menyn (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är i allmänhet korrekt, men alternativen kan finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
