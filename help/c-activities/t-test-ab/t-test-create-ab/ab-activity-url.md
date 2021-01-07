---
keywords: activity url;url;different url
description: Aktivitets-URL:en bestämmer vilken sida som används i testet och som öppnas när testet har utformats med Adobe Target.
title: Aktivitets-URL
feature: A/B Tests
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Aktivitets-URL

Aktivitets-URL:en bestämmer vilken sida som används i testet och som öppnas när testet har utformats med Adobe Target.

Ange aktivitets-URL när du uppmanas att göra det när aktiviteten skapas. Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] skiljer inte mellan URL-protokoll (  [!DNL https] och  [!DNL http]). Därför matchar både [!DNL `http://www.adobe.com`] och [!DNL `https://www.adobe.com`].

## Ange en annan URL

Som standard öppnar [!UICONTROL Visual Experience Composer] sidan som anges i [inställningarna för Visual Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md)
. Du kan ange en annan sida när du skapar en aktivitet.

Om du vill visa en annan sida efter att [!UICONTROL Visual Experience Composer] har öppnats klickar du på kugghjulsikonen **[!UICONTROL Configure]** och väljer sedan **[!UICONTROL Page Delivery]**. Ange URL-adressen i fältet Aktivitets-URL.

![Dialogrutan Sidleverans](/help/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

Klicka på **[!UICONTROL Add Template Rule]** om du vill lägga till fler sidor eller avsnitt i aktiviteten.

Ytterligare regler kan baseras på något av följande:

* URL
* Domän
* Bana
* Hash-fragment (#)
* Fråga
* mbox-parameter

Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

Klicka på **[!UICONTROL Save]** när du är klar.

>[!NOTE]
>
>Om du angav en URL för en plats som inte innehåller JavaScript-standardkoden [!DNL Target] kan du inte välja sidelement.

Som standard tillåter inte [!UICONTROL Visual Experience Composer] ändringar av element som innehåller JavaScript, t.ex. roterande banners. Du kan inaktivera **[!UICONTROL Render using JavaScript]** om du vill kunna ändra dessa element med [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.
