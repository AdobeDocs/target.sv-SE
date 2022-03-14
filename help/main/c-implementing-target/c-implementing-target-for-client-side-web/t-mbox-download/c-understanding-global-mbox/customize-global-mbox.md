---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: Lär dig hur du anpassar en global mbox för at.js på sidan Administration-Implementation i Adobe Target.
title: Hur anpassar jag en global mbox?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Anpassa en global mbox

Information som hjälper dig att anpassa en [!DNL Adobe Target] global mbox för at.js.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

1. Inaktivera **[!UICONTROL Page load enabled (Auto create global mbox)]** lägger du sedan till namnet på den anpassade globala mbox som du vill använda för att leverera aktiviteter från [!DNL Target].

   >[!IMPORTANT]
   >
   >Ändringen sparas automatiskt när du väljer en annan global ruta.

   Den här anpassade globala rutan används även för klickspårning.

   ![custom-global-mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Implementera [!DNL at.js] bibliotek på din webbplats.

   Se [Så här distribuerar du at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) för mer information.

1. Tid för övergången med din release.

   När du är redo för [!DNL Target] Om du vill börja använda din globala mbox för alla aktiviteter i framtiden kan du fortsätta med det här steget.

   Uppdatera namnet på den anpassade globala mbox så att det matchar namnet som används i steg 2 ovan.

   >[!IMPORTANT]
   >
   >Alla aktiviteter i ditt konto synkroniseras med den här rutan. Kontrollera att den globala mbox finns på din webbplats så att aktiviteterna fortsätter att fungera. Var noga med att redigera och spara om påverkade aktiviteter som har skapats med Visual Experience Composer (VEC) som har synkroniserats med den här kryssrutan. Du behöver inte spara om aktiviteter som skapats i den formulärbaserade Experience Composer eller via API.

