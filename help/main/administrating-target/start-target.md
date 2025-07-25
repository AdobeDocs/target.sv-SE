---
keywords: Administration;godkännarroll;godkännare
description: Utför de första  [!DNL Adobe Target] uppgifterna som administratörer ska utföra efter att ha tagit emot e-postinbjudan till  [!DNL Adobe Experience Cloud].
title: Var kommer jag igång med att administrera [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: 614fd89c9746ce55f502debd5b689c34de400ae5
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 0%

---

# Administratörssteg

Den här artikeln innehåller de första stegen som [!DNL Adobe Target]-administratörer ska utföra efter att ha tagit emot e-postinbjudan till [!DNL Adobe Experience Cloud].

## Få inbjudan till [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

En systemadministratör i [!DNL Adobe Admin Console] måste lägga till dig som en användare i [!DNL Target] genom att bjuda in dig. Systemadministratören bör sedan lägga till dig i en eller flera rollspecifika produktprofiler (användargrupper). Båda dessa åtgärder utförs i [Adobe Admin Console](https://adminconsole.adobe.com).

Mer information finns i [Hantera användargrupper](https://helpx.adobe.com/se/enterprise/using/users.html).

Du får ett e-postmeddelande med en inbjudan när systemadministratören har utfört de här stegen.

## Acceptera inbjudan {#task_24FE66659E634B24AB61DB8497772E17}

När du har fått inbjudan att gå med i [!DNL Adobe Experience Cloud] godkänner du inbjudan, loggar in och accepterar [!UICONTROL End User License Agreement] (EULA).

1. Acceptera inbjudan till [!DNL Adobe Experience Cloud].
1. Om du inte redan har en Adobe ID uppmanas du att skapa en.

   Om du har en Adobe ID känner din Adobe ID igen sig och du uppmanas att logga in.
1. Acceptera [!UICONTROL Terms of Use].
1. Granska sammanfattningen av vad du har gjort hittills och klicka sedan på **[!UICONTROL Continue to Experience Cloud]**.
1. Logga in på [!DNL Adobe Experience Cloud] och klicka på **[!UICONTROL Link Account]**.

   >[!NOTE]
   >
   >Om du inte länkar ditt konto kan du inte komma åt [!DNL Target].

   Alla [!UICONTROL Experience Cloud]-produkter visas på länkningssidan. Klicka på `Link Target` och ange ditt [!DNL Target]-användarnamn och lösenord för att komma åt [!DNL Target].
1. Klicka på **[!UICONTROL Continue to Experience Cloud]**.

   För närvarande har du inte skapat några grupper som du kan länka till.
1. Om du vill kan du titta på videon som presenterar [!DNL Adobe Experience Cloud].
1. Logga ut från [!DNL Adobe Experience Cloud] och logga sedan in igen om du vill se dina nya privilegier och få tillgång till produkten.
1. Fortsätt till nästa steg, [tilldela dig själv rollen Godkännare](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Tilldela dig själv rollen Godkännare {#task_15CAA437A71444E2932B333D5E66A3C7}

När du har accepterat inbjudan att gå med i [!DNL Adobe Experience Cloud] och logga in bekräftar du att [!DNL Target] har lagts till i ditt [!DNL Experience Cloud]-konto och tilldelar dig sedan rollen [!UICONTROL Approver] för [!DNL Target].

Om din organisation har en [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905)-licens, se [Ange roller och behörigheter](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) i *Användare*.

Om din organisation har en [Target Premium](/help/main/c-intro/intro.md#premium)-licens, se [Steg 6: Ange roller och behörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) i *Konfigurera företagsbehörigheter*.

Nästa steg bör vara att konfigurera användare i [!DNL Target Standard] och [!DNL Target Premium]. Mer information finns i [Användarhantering](/help/main/administrating-target/c-user-management/user-management.md).

## Behörigheter krävs för att redigera inställningarna för [!UICONTROL Administration] {#admin-permissions}

**Före den 22 april 2025**: Användare med [!UICONTROL Approvers] rättigheter i [!DNL Adobe Admin Console] kan redigera eller ändra alla inställningar på [[!UICONTROL Administration] page](/help/main/administrating-target/administrating-target.md)-sidan i [!DNL Target], oavsett deras [!DNL Target]-roll.

**Gäller från 22 april 2025**: Endast [!UICONTROL Product] - och [!UICONTROL Solutions] -administratörer kan uppdatera inställningarna i [[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md) -avsnitten, oavsett deras roller i [!DNL Target] -arbetsytorna. Användare utan den här behörigheten har skrivskyddad åtkomst till [!UICONTROL Administration]-avsnitten.

Den här uppdateringen förbättrar organisationskontrollen över [!DNL Target] instanskonfigurationer och förhindrar oavsiktliga uppdateringar som kan påverka aktivitetsleveransen i olika testnings- och personaliseringsteam.
