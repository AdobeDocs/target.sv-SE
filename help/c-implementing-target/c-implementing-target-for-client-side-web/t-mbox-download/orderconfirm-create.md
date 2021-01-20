---
keywords: order confirmation;orderConfirmPage
description: I rutan Orderbekräftelse registreras detaljer om beställningar på er webbplats och du kan rapportera baserat på intäkter och order. I rutan Orderbekräftelse kan du också skapa rekommendationsalgoritmer, till exempel"Personer som köpt produkten x har också köpt produkten y".
title: Skapa en orderbekräftelseruta - mbox.js
feature: null
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 15%

---


# Skapa en orderbekräftelseruta - mbox.js

I rutan Orderbekräftelse registreras detaljer om beställningar på er webbplats och du kan rapportera baserat på intäkter och order. I rutan Orderbekräftelse kan du också skapa rekommendationsalgoritmer, till exempel&quot;Personer som köpt produkten x har också köpt produkten y&quot;.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>* Om användarna gör inköp på webbplatsen rekommenderar vi att du implementerar en orderbekräftelseruta även om du använder Analytics for Target (A4T) för din rapportering.
   >
   >
* Du kan också skapa en orderbekräftelseruta för at.js 1.*som* använder samma metod, men  [!DNL at.js] metoden är att föredra. Mer information finns i [Spåra konverteringar](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
   >
   >
* Om du använder at.js 2.*x*,  `mboxCreate` stöds inte längre. För orderbekräftelse med at.js 2.*x* använder du följande spårningsrelaterade API:er:  [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md)  och  [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).


1. Infoga mbox-skriptet efter modellen nedan på sidan med orderinformation.
1. Ersätt ORD I VERSALA BOKSTÄVER med antingen dynamiska eller statiska värden från katalogen.

   >[!NOTE]
   >
   >Använd kommaavgränsning för att avgränsa flera produkt-ID:n.

   **Tips:** Du kan också skicka beställningsinformation i valfri ruta (den behöver inte namnges  `orderConfirmPage`). Du kan också skicka beställningsinformation i flera rutor inom samma kampanj.

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

I rutan Orderbekräftelse används följande parametrar:

| Parameter | Beskrivning |
|--- |--- |
| `orderId` | Unikt värde för att identifiera en order för konverteringsinventering.<br>Värdet `orderId` måste vara unikt. Dubblettorder ignoreras i rapporter. |
| `orderTotal` | Köpets monetära värde.<br>Skicka inte valutasymbolen. Använd ett decimaltecken (inte kommatecken) för att ange decimalvärden. |
| `productPurchasedId` (Valfritt) | En kommaseparerad lista över produkt-ID:n som köpts i ordern.<br>Dessa produkt-ID:n visas i granskningsrapporten som stöd för ytterligare rapportanalyser. |