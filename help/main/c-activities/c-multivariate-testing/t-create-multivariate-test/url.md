---
keywords: Multivariata tester;aktivitets-URL
description: Lär dig hur du anger den aktivitets-URL som avgör vilken sida som används i testet och som öppnas när aktiviteten [!UICONTROL Multivariate Test] utformas med  [!DNL Adobe Target].
title: Vad är aktivitets-URL:en i en [!UICONTROL Multivariate Test]-aktivitet (MVT)?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Aktivitets-URL

Aktivitets-URL:en avgör vilken sida som används i [!UICONTROL Multivariate Test] (MVT) och som öppnas när testet är utformat i [!DNL Adobe Target].

1. Ange aktivitets-URL när du uppmanas att göra det när [aktiviteten](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md) skapas. Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Därför matchar både [!DNL `https://www.adobe.com`] och [!DNL `http://www.adobe.com`].

   Som standard öppnar [!UICONTROL Visual Experience Composer] (VEC) sidan som anges i [inställningarna för Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Du kan ange en annan sida när du skapar en aktivitet.

1. (Villkorligt) Om du vill visa en annan sida efter att VEC har öppnats klickar du på ikonen **[!UICONTROL Configure]**, väljer **[!UICONTROL Page Delivery]** och anger sedan URL:en.

1. (Villkorligt) Klicka på **[!UICONTROL Add Rule]** om du vill lägga till fler sidor eller avsnitt i aktiviteten.

   Ytterligare regler kan baseras på något av följande:

   * [!UICONTROL  URL]
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment]
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

   Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.

   Klicka på **[!UICONTROL Save]** när du är klar.

>[!NOTE]
>
>Om du angav en URL för en webbplats som inte innehåller JavaScript-koden [!DNL Target] kan du inte markera sidelement.
>
>VEC tillåter som standard inte ändringar av element som innehåller JavaScript, t.ex. roterande banderoller. Du kan inaktivera **[!UICONTROL Render using JavaScript]** om du vill kunna ändra dessa element med [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.
