---
keywords: Targeting
description: Aktivitets-URL:en bestämmer vilken sida som används i aktiviteten Experience Targeting och som öppnas i Adobe Target Visual Experience Composer (VEC) eller Form-Based Experience Composer när aktiviteten har designats.
title: Aktivitets-URL
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Aktivitets-URL{#activity-url}

Aktivitets-URL:en bestämmer vilken sida som används i aktiviteten Experience Targeting (XT) och som öppnas i Visual Experience Composer (VEC) eller Form-Based Experience Composer när aktiviteten har designats.

1. Ange aktivitets-URL när du uppmanas att [skapa en XT-aktivitet](/help/c-activities/t-experience-target/t-xt-create/xt-create.md). Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Resultatet blir att [!DNL `https://www.adobe.com`] och [!DNL `http://www.adobe.com`] båda matchar.
   >
   >Som standard öppnar VEC- eller Form-Based Experience Experience Composer sidan som anges i [kontoinställningarna](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Du kan ange en annan sida när du skapar en aktivitet.
   >
   >Om du anger en URL för en plats som inte innehåller JavaScript-koden för målstandard kan du inte markera sidelement.

1. (Villkorligt) Om du vill visa en annan sida efter att VEC har öppnats klickar du på **[!UICONTROL Configure]**, väljer **[!UICONTROL Page Delivery]** och anger URL:en i [!UICONTROL URL] fältet.

   ![Dialogrutan Sidleverans](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.

1. (Villkorligt) Klicka för **[!UICONTROL Add Template Rule]** att lägga till fler sidor eller avsnitt i aktiviteten.

   Ytterligare regler kan baseras på något av följande:

   * URL
   * Domän
   * Bana
   * Hash-fragment (#)
   * Fråga
   * mbox-parameter
   Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

1. Klicka **[!UICONTROL Save]** när du är klar.