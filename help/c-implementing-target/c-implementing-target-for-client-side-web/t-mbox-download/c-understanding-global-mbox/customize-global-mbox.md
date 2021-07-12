---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: Lär dig hur du anpassar en global mbox för at.js på sidan Administration-Implementation i Adobe Target.
title: Hur anpassar jag en global mbox?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: fb0a62ecc5609e7b8ef5f6a4fb5a94f8ba025fec
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# Anpassa en global mbox

Information som hjälper dig att anpassa en global mbox för at.js.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

1. Inaktivera **[!UICONTROL Page load enabled (Auto create global mbox)]** och lägg sedan till namnet på den anpassade globala mbox som du vill använda för att leverera aktiviteter från [!DNL Target].

   >[!IMPORTANT]
   >
   >Ändringen sparas automatiskt när du väljer en annan global ruta.

   Den här anpassade globala rutan används även för klickspårning.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Implementera [!DNL at.js]-biblioteket på din plats.

   Mer information finns i [Distribuera at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

1. Tid för övergången med din release.

   När du är redo för [!DNL Target] att börja använda din globala mbox för alla aktiviteter i framtiden kan du fortsätta med det här steget.

   Uppdatera namnet på den anpassade globala mbox så att det matchar namnet som används i steg 2 ovan.

   >[!IMPORTANT]
   >
   >Alla aktiviteter i ditt konto synkroniseras med den här rutan. Om den här kryssrutan inte finns på din plats slutar alla aktiviteter att fungera.
