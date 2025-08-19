---
keywords: Experience Targeting;xt;activity url;url
description: Lär dig hur du anger den [!UICONTROL Activity URL] som avgör vilken sida som ska användas i testet och som öppnas när [!UICONTROL Experience Targeting]-aktiviteten utformas med  [!DNL Adobe Target].
title: Vad är [!UICONTROL Activity URL] i en [!UICONTROL Experience Targeting] (XT) aktivitet?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Aktivitets-URL i [!UICONTROL Experience Targeting] (XT) aktiviteter

[!UICONTROL Activity URL] avgör vilken sida som används i en [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT)-aktivitet. Det här är den sida som öppnas i [!UICONTROL Visual Experience Composer] (VEC) eller [!UICONTROL Form-Based Experience Composer] när aktiviteten är utformad.

1. Ange aktivitets-URL när du uppmanas till det när [skapar en XT-aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md). Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Därför matchar både [!DNL `https://www.adobe.com`] och [!DNL `http://www.adobe.com`].
   >
   >Som standard öppnar VEC- eller [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) den sida som anges i [inställningarna för Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Du kan ange en annan sida när du skapar en aktivitet.
   >
   >Om du anger en URL för en webbplats som inte innehåller ett [[!DNL Target]  at.js JavaScript-bibliotek eller  [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=sv-SE){target=_blank} kan du inte välja sidelement.

1. (Villkorligt) Om du vill visa en annan sida efter att VEC har öppnats klickar du på **[!UICONTROL Configure]**, väljer **[!UICONTROL Page Delivery]** och anger sedan URL:en i fältet [!UICONTROL URL].

   ![Dialogrutan Sidleverans](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.

1. (Villkorligt) Klicka på **[!UICONTROL Add Template Rule]** om du vill lägga till fler sidor eller avsnitt i aktiviteten.

   Ytterligare regler kan baseras på något av följande:

   * URL
   * Domän
   * Bana
   * Hash-fragment (#)
   * Fråga
   * mbox-parameter

   Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

1. Klicka på **[!UICONTROL Save]** när du är klar.
