---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: Information som hjälper dig att anpassa en global mbox för at.js.
title: Anpassa en global mbox
feature: null
subtopic: Getting Started
topic: Standard
uuid: 0f784d6e-8f36-4c26-adbf-0d56b7d6d390
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# Anpassa en global mbox{#customize-a-global-mbox}

Information som hjälper dig att anpassa en global mbox för at.js.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

1. Inaktivera **[!UICONTROL Page load enabled (Auto create global mbox)]** och lägg sedan till namnet på den anpassade globala mbox som du vill använda för att leverera aktiviteter från [!DNL Target].

   Den här anpassade globala rutan används även för klickspårning.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Klicka **[!UICONTROL Save]** när du är klar.

1. Implementera [!DNL at.js] biblioteket på din webbplats.

   Mer information finns i [Så här distribuerar du at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) .

1. Tid för övergången med din release.

   Så fort du är redo [!DNL Target] att börja använda din globala mbox för alla aktiviteter framåt kan du fortsätta med det här steget.

   Uppdatera namnet på den anpassade globala mbox så att det matchar namnet som används i steg 2 ovan.

   >[!IMPORTANT]
   >
   >När du sparar synkroniseras alla aktiviteter på ditt konto med den här rutan. Om den här rutan inte finns på din webbplats kommer alla aktiviteter att sluta fungera.

