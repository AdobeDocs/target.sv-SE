---
keywords: Administration;approver role;approver
description: Perform the first tasks [!DNL Adobe Target] administrators should take after receiving the emailed invitation to the [!DNL Adobe Experience Cloud].
title: Where Do I Get Started Administering [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: 0618d39fc5966c64cceea8f5bcccb625fc243ebb
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Administratörens första steg

Den här artikeln innehåller de första stegen [!DNL Adobe Target] som administratörer bör vidta när de har fått en inbjudan till .[!DNL Adobe Experience Cloud]

## Bli inbjuden till [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

En systemadministratör i måste [!DNL Adobe Admin Console] lägga till dig som användare genom [!DNL Target] att bjuda in dig att gå med. Systemadministratören ska sedan lägga till dig i en eller flera rollspecifika grupper. Båda dessa uppgifter utförs i [Adobe Admin Console](https://adminconsole.adobe.com).

Mer information finns i [Hantera användare och produkter](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) i Experience *Cloud och bastjänster hjälpen*.

Du kommer att få en inbjudan via e-post efter att systemadministratören har utfört dessa steg.

## Acceptera inbjudan {#task_24FE66659E634B24AB61DB8497772E17}

After receiving the invitation to join the [!DNL Adobe Experience Cloud], accept the invitation, log in, and accept the [!UICONTROL End User License Agreement] (EULA).

1. Accept the invitation to the [!DNL Adobe Experience Cloud].
1. If you do not already have an Adobe ID, you are prompted to create one.

   Om du har ett Adobe ID känns ditt Adobe ID igen och du uppmanas att logga in.
1. Godkänn [!UICONTROL Terms of Use].
1. Granska sammanfattningen av vad du har gjort hittills och klicka sedan på **[!UICONTROL Continue to Experience Cloud]**.
1. Logga in på och [!DNL Adobe Experience Cloud] klicka på **[!UICONTROL Link Account]**.

   >[!NOTE]
   >
   >Om du inte länkar ditt konto kommer du inte att kunna komma åt [!DNL Target].

   Alla [!UICONTROL Experience Cloud] produkter visas på den länkande sidan. Klicka `Link Target` och ange ditt [!DNL Target] användarnamn och lösenord för att komma åt [!DNL Target].
1. Klicka på **[!UICONTROL Continue to Experience Cloud]**.

   Nu har du ännu inte konfigurerat några grupper med rättigheter som du kan länka.
1. If desired, watch the video introducing you to the [!DNL Adobe Experience Cloud].
1. To see your new privileges and access the product, sign out of [!DNL Adobe Experience Cloud], then sign back in.
1. Fortsätt till nästa steg och [tilldela dig själv rollen](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7) Godkännare.

## Tilldela dig själv rollen Godkännare {#task_15CAA437A71444E2932B333D5E66A3C7}

När du har accepterat inbjudan att gå med [!DNL Adobe Experience Cloud] och loggat in, bekräfta att det [!DNL Target] har lagts till på ditt [!DNL Experience Cloud] konto och tilldela sedan dig själv [!UICONTROL Approver] rollen för [!DNL Target].

Om din organisation har en [Target Standard-licens](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) , se [Ange roller och behörigheter](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) i *Användare*.

Om din organisation har en [Target Premium-licens](/help/main/c-intro/intro.md#premium) kan du läsa [Steg 6: Ange roller och behörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) i *Konfigurera företagsbehörigheter*.

Nästa steg bör vara att ställa in användare i [!DNL Target Standard] och [!DNL Target Premium]. Mer information finns i [Användarhantering](/help/main/administrating-target/c-user-management/user-management.md).

## Behörigheter som krävs för att redigera [!UICONTROL Administration] inställningar {#admin-permissions}

**Before April 22, 2025**: Users with [!UICONTROL Approvers] rights in the [!DNL Adobe Admin Console] can edit or change all settings on the [[!UICONTROL Administration] page](/help/main/administrating-target/administrating-target.md) page of [!DNL Target], regardless of their [!DNL Target] role.

**Effective April 22, 2025**: Only [!UICONTROL Product] and [!UICONTROL Solutions] admins will be able to update settings in the [[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md) sections, regardless of their roles in [!DNL Target] workspaces. Användare utan den här behörigheten har skrivskyddad åtkomst till [!UICONTROL Administration]-avsnitten.

This update enhances organizational control over [!DNL Target] instance configurations, preventing accidental updates that could affect activity delivery across various testing and personalization teams.
