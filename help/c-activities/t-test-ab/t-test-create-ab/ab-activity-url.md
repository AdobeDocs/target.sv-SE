---
keywords: Overview and Reference
description: Aktivitets-URL:en bestämmer vilken sida som används i testet och som öppnas när testet har utformats.
title: Aktivitets-URL
feature: null
topic: Standard
uuid: 65489969-d548-4286-858f-8420120317c0
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---


# Aktivitets-URL{#activity-url}

Aktivitets-URL:en bestämmer vilken sida som används i testet och som öppnas när testet har utformats.

Ange aktivitets-URL när du uppmanas att göra det när aktiviteten skapas. Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Resultatet blir att [!DNL `http://www.adobe.com`] och [!DNL `https://www.adobe.com`] båda matchar.

## Ange en annan URL

Som standard [!UICONTROL Visual Experience Composer] öppnas sidan som anges i inställningarna för [](/help/administrating-target/visual-experience-composer-set-up.md)Visual Experience Composer. Du kan ange en annan sida när du skapar en aktivitet.

Om du vill visa en annan sida efter att [!UICONTROL Visual Experience Composer] öppnas klickar du på **[!UICONTROL Configure]** kugghjulsikonen och väljer sedan **[!UICONTROL Page Delivery]**. Ange URL-adressen i fältet Aktivitets-URL.

![Dialogrutan Sidleverans](/help/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

Klicka **[!UICONTROL Add Template Rule]** för att lägga till fler sidor eller avsnitt i aktiviteten.

Ytterligare regler kan baseras på något av följande:

* URL
* Domän
* Bana
* Hash-fragment (#)
* Fråga
* mbox-parameter

Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

Klicka **[!UICONTROL Save]** när du är klar.

>[!NOTE]
>
>Om du har angett en URL för en plats som inte innehåller JavaScript- [!DNL Target] standardkoden kan du inte markera sidelement.

Som standard tillåts inte ändringar i element som innehåller JavaScript, t.ex. roterande banners. [!UICONTROL Visual Experience Composer] Du kan inaktivera **[!UICONTROL Render using JavaScript]** om du vill kunna ändra dessa element med hjälp av [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.
