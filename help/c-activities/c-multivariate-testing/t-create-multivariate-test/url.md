---
keywords: Multivariate Tests;activity url
description: Activity URL (Aktivitets-URL) bestämmer vilken sida som används i ett Adobe Target Multivariate Test (MVT) och som öppnas när testet är utformat i Adobe Target.
title: Aktivitets-URL
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---


# Aktivitets-URL{#activity-url}

Aktivitets-URL:en bestämmer vilken sida som används i [!UICONTROL Multivariate Test] (MVT) och som öppnas när testet är utformat i [!DNL Adobe Target].

Ange aktivitets-URL när du uppmanas till detta när [aktiviteten skapas](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md). Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] skiljer inte mellan URL-protokoll (  [!DNL https] och  [!DNL http]). Därför matchar både [!DNL `https://www.adobe.com`] och [!DNL `http://www.adobe.com`].

Som standard öppnar [!UICONTROL Visual Experience Composer] (VEC) den sida som anges i [inställningarna för Visual Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md). Du kan ange en annan sida när du skapar en aktivitet.

Om du vill visa en annan sida efter att VEC har öppnats klickar du på ikonen **[!UICONTROL Configure]**, väljer **[!UICONTROL Page Delivery]** och anger sedan URL:en.

![Dialogrutan Sidleverans](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Klicka på **[!UICONTROL Add Template Rule]** om du vill lägga till fler sidor eller avsnitt i aktiviteten.

Ytterligare regler kan baseras på något av följande:

* URL
* Domän
* Bana
* Hash-fragment (#)
* Fråga
* Parameter

Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

Klicka på **[!UICONTROL Save]** när du är klar.

>[!NOTE]
>
>Om du har angett en URL för en plats som inte innehåller JavaScript-kod enligt målstandard kan du inte markera sidelement.

VEC tillåter som standard inte ändringar av element som innehåller JavaScript, t.ex. roterande banners. Du kan inaktivera **[!UICONTROL Render using JavaScript]** om du vill kunna ändra dessa element med [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.