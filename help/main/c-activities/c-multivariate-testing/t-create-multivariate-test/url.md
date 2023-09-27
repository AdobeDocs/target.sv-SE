---
keywords: Multivariata tester;aktivitets-URL
description: Lär dig hur du anger den aktivitets-URL som avgör vilken sida som ska användas i testet och som öppnas när [!UICONTROL Multivariate Test] aktiviteten är utformad med [!DNL Adobe Target].
title: Vad är aktivitets-URL i en [!UICONTROL Multivariate Test] Aktivitet?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Aktivitets-URL

Aktivitets-URL:en bestämmer vilken sida som används i [!UICONTROL Multivariate Test] (MVT), som öppnas när testet är utformat i [!DNL Adobe Target].

När du uppmanas under [skapande av aktivitet](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)anger du aktivitets-URL:en. Ange den fullständiga URL:en (inklusive `https://`) och sedan klicka på **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Detta resulterar i [!DNL `https://www.adobe.com`] och [!DNL `http://www.adobe.com`] båda matchar.

Som standard är [!UICONTROL Visual Experience Composer] (VEC) öppnar sidan som anges i [Inställningar för Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Du kan ange en annan sida när du skapar en aktivitet.

Om du vill visa en annan sida efter att VEC öppnas klickar du på **[!UICONTROL Configure]** ikon och sedan välja **[!UICONTROL Page Delivery]** anger du sedan webbadressen.

![Dialogrutan Sidleverans](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Klicka **[!UICONTROL Add Template Rule]** om du vill lägga till fler sidor eller avsnitt i aktiviteten.

Ytterligare regler kan baseras på något av följande:

* URL
* Domän
* Bana
* Hash-fragment (#)
* Fråga
* Parameter

Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

Klicka **[!UICONTROL Save]** när du är klar.

>[!NOTE]
>
>Om du angav en URL för en plats som inte innehåller [!DNL Target] JavaScript-kod kan inte markera sidelement.

VEC tillåter som standard inte ändringar av element som innehåller JavaScript, t.ex. roterande banners. Du kan inaktivera **[!UICONTROL Render using JavaScript]** om du vill kunna ändra dessa element med [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.
