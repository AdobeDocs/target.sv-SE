---
keywords: activity url;url;different url
description: Lär dig hur du anger den aktivitets-URL som avgör vilken sida som ska användas i testet och som öppnas när testet har utformats med Adobe Target.
title: Vad är aktivitets-URL:en i en A/B-aktivitet?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Aktivitets-URL

Aktivitets-URL:en bestämmer vilken sida som används i testet och som öppnas när testet har utformats med Adobe Target.

Ange aktivitets-URL när du uppmanas att göra det när aktiviteten skapas. Ange den fullständiga URL:en (inklusive `https://`) och sedan klicka på **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Som en följd av detta [!DNL `http://www.adobe.com`] och [!DNL `https://www.adobe.com`] båda matchar.

## Ange en annan URL

Som standard är [!UICONTROL Visual Experience Composer] öppnar sidan som anges i [Inställningar för Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md)
. Du kan ange en annan sida när du skapar en aktivitet.

Så här visar du en annan sida efter [!UICONTROL Visual Experience Composer] öppnas, klicka på **[!UICONTROL Configure]** kugghjulsikonen och välj **[!UICONTROL Page Delivery]**. Ange URL-adressen i fältet Aktivitets-URL.

![Dialogrutan Sidleverans](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

Klicka **[!UICONTROL Add Template Rule]** om du vill lägga till fler sidor eller avsnitt i aktiviteten.

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
>Om du angav en URL för en plats som inte innehåller [!DNL Target] JavaScript-kod som standard kan du inte markera sidelement.

Som standard är [!UICONTROL Visual Experience Composer] tillåter inte ändringar av element som innehåller JavaScript, t.ex. roterande banners. Du kan inaktivera **[!UICONTROL Render using JavaScript]** om du vill kunna ändra dessa element med [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.
