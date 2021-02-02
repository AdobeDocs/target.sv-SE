---
keywords: Experience Targeting;xt;activity url;url
description: Aktivitets-URL:en bestämmer vilken sida som används i Adobe Target Experience Targeting-aktiviteten och som öppnas i Visual Experience Composer (VEC) eller Form-Based Experience Composer när aktiviteten har designats.
title: Aktivitets-URL
feature: Experience Targeting
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---


# Aktivitets-URL i XT-aktiviteter (Experience Targeting)

[!UICONTROL Activity URL] avgör vilken sida som används i aktiviteten [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) och som öppnas i [!UICONTROL Visual Experience Composer] (VEC) eller [!UICONTROL Form-Based Experience Composer] när aktiviteten har designats.

1. Ange aktivitets-URL när du uppmanas att göra [en XT-aktivitet](/help/c-activities/t-experience-target/t-xt-create/xt-create.md). Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll (  [!DNL https] och  [!DNL http]). Därför matchar både [!DNL `https://www.adobe.com`] och [!DNL `http://www.adobe.com`].
   >
   >Som standard öppnar VEC- eller Form-Based Experience Experience Composer sidan som anges i [inställningarna för Visual Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md). Du kan ange en annan sida när du skapar en aktivitet.
   >
   >Om du anger en URL för en plats som inte innehåller JavaScript-koden för målstandard kan du inte markera sidelement.

1. (Villkorligt) Om du vill visa en annan sida efter att VEC har öppnats klickar du på **[!UICONTROL Configure]**, väljer **[!UICONTROL Page Delivery]** och anger URL:en i fältet [!UICONTROL URL].

   ![Dialogrutan Sidleverans](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

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