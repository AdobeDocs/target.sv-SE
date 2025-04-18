---
keywords: activity url;url;different url
description: Lär dig hur du anger den aktivitets-URL som avgör vilken sida som ska användas i testet och som öppnas när testet utformas med  [!DNL Adobe Target].
title: Vad är aktivitets-URL:en i en A/B-aktivitet?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Aktivitets-URL

Aktivitets-URL:en avgör vilken sida som används i testet och som öppnas när testet har utformats med Adobe Target.

Ange aktivitets-URL när du uppmanas att göra det när aktiviteten skapas. Skriv den fullständiga URL:en (inklusive `https://`) och klicka sedan på **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Därför matchar både [!DNL `http://www.adobe.com`] och [!DNL `https://www.adobe.com`].

## Ange en annan URL

Som standard öppnar [!UICONTROL Visual Experience Composer] sidan som anges i [inställningarna för Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Du kan ange en annan sida när du skapar en aktivitet.

1. Om du vill visa en annan sida efter att [!UICONTROL Visual Experience Composer] har öppnats klickar du på kugghjulsikonen **[!UICONTROL Experiences]** på sidan **[!UICONTROL Configure]** och väljer sedan **[!UICONTROL Page Delivery]**.

1. Ange URL-adressen i fältet **[!UICONTROL URL]**.

   ![Dialogrutan Sidleverans](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

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

Om du angav en URL för en webbplats som inte innehåller JavaScript-standardkoden [!DNL Target] kan du inte välja sidelement.

Som standard tillåter inte [!UICONTROL Visual Experience Composer] ändringar i element som innehåller JavaScript, t.ex. roterande banderoller. Du kan inaktivera **[!UICONTROL Render using JavaScript]** om du vill kunna ändra dessa element med [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Om du ändrar URL:en efter att ha gjort ändringar på en sida för en eller flera upplevelser, återställs upplevelsen med den nya sidan och ändringarna du gjorde går förlorade.
