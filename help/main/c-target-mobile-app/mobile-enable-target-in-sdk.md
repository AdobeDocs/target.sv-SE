---
keywords: mobilapp;mobilapp sdk;target mobile app;mobile target sdk;mobile app sdk;enable target in sdk
description: Lär dig hur du lägger till Adobe Mobile Services SDK i din mobilapp.
title: Hur aktiverar jag [!DNL Target] i Adobe Mobile SDK?
feature: Implement Mobile
role: Developer
exl-id: c34bd50c-e17f-4dfb-8470-8f4c8639ee9f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Aktivera [!DNL Target] i SDK

Lägg till Adobe Mobile Services SDK i din app.

1. Om du inte har installerat Adobe Mobile Services SDK i din app använder du inloggningsuppgifterna för Analytics eller Experience Cloud och hämtar SDK från [Adobe Mobile Services](https://mobilemarketing.adobe.com/) webbplats.

1. Lägg till Adobe Mobile Services SDK i din app.

   Instruktionerna finns under [Kärnimplementering och livscykel](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html).

1. Lägg till klientkod, tidsgräns och aktivera SSL.

   Öppna Mobile Services i Experience Cloud och gå sedan till **[!UICONTROL Manage App Settings]** > **[!UICONTROL SDK Target Options]**.

   Lägg till din Target-klientkod och tidsgräns. Klientkoden är unik för ditt konto eller företag. Tidsgränsen är tiden i antal sekunder tills Target väntar på ett svar innan standardinnehållet visas. Se till att **[!UICONTROL Use HTTPS]** alternativet är markerat på sidan Hantera programinställningar i Adobe Mobile Services. Om HTTPS inte är aktiverat blockeras alla anrop i iOS9+ om du inte tillåtslista målservern.

   ![](assets/mobile-clientcode.png)

1. När du har skapat/hittat programmet kan du hitta programinställningarna och hämta önskat SDK.

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> Om du inte har tillgång till gränssnittet för mobilmarknadsföring kan du göra ändringar direkt i konfigurationsfilen i appkoden; Den kommer dock inte att vara synkroniserad med inställningssidan i användargränssnittet.
