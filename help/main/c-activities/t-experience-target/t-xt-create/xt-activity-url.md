---
keywords: Experience Targeting;xt;activity url;url
description: Lär dig hur du anger [!UICONTROL Activity URL] som avgör vilken sida som används i testet och som öppnas när [!UICONTROL Experience Targeting] aktiviteten är utformad med [!DNL Adobe Target].
title: Vad är [!UICONTROL Activity URL] I en [!UICONTROL Experience Targeting] (XT) Aktivitet?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 24513d8cb39d38dcfbc74bf40961d5517cc90a4b
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Aktivitets-URL i [!UICONTROL Experience Targeting] (XT) aktiviteter

The [!UICONTROL Activity URL] bestämmer vilken sida som används i en [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) aktivitet. Det här är sidan som öppnas i [!UICONTROL Visual Experience Composer] (VEC) eller [!UICONTROL Form-Based Experience Composer] när aktiviteten är utformad.

1. När du tillfrågas när [skapa en XT-aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)anger du aktivitets-URL:en. Ange den fullständiga URL:en (inklusive `https://`) och sedan klicka på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Detta resulterar i [!DNL `https://www.adobe.com`] och [!DNL `http://www.adobe.com`] båda matchar.
   >
   >VEC eller [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) öppnar sidan som anges i [Inställningar för Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Du kan ange en annan sida när du skapar en aktivitet.
   >
   >Om du anger en URL för en plats som inte innehåller en [[!DNL Target] at.js JavaScript-bibliotek eller [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}kan du inte markera sidelement.

1. (Villkorligt) Om du vill visa en annan sida efter att VEC har öppnats klickar du på **[!UICONTROL Configure]**, markera **[!UICONTROL Page Delivery]** anger du sedan webbadressen i dialogrutan [!UICONTROL URL] fält.

   ![Dialogrutan Sidleverans](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.

1. (Villkorligt) Klicka **[!UICONTROL Add Template Rule]** om du vill lägga till fler sidor eller avsnitt i aktiviteten.

   Ytterligare regler kan baseras på något av följande:

   * URL
   * Domän
   * Bana
   * Hash-fragment (#)
   * Fråga
   * mbox-parameter

   Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

1. Klicka **[!UICONTROL Save]** när du är klar.
