---
keywords: order confirmation;orderConfirmPage
description: I rutan Orderbekräftelse registreras detaljer om beställningar på er webbplats och du kan rapportera baserat på intäkter och order. I rutan Orderbekräftelse kan du också skapa rekommendationsalgoritmer, till exempel"Personer som köpt produkten x har också köpt produkten y".
title: Skapa en orderbekräftelseruta - mbox.js
feature: null
subtopic: Getting Started
uuid: 001da2bd-2ccf-490b-ba84-ac9b9a2a5451
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 19%

---


# Skapa en orderbekräftelseruta - mbox.js{#create-an-order-confirmation-mbox-mbox-js}

I rutan Orderbekräftelse registreras detaljer om beställningar på er webbplats och du kan rapportera baserat på intäkter och order. I rutan Orderbekräftelse kan du också skapa rekommendationsalgoritmer, till exempel&quot;Personer som köpt produkten x har också köpt produkten y&quot;.

>[!NOTE]
>
>* Om användarna gör inköp på webbplatsen rekommenderar vi att du implementerar en orderbekräftelseruta även om du använder Analytics for Target (A4T) för din rapportering.
   >
   >
* Du kan också skapa en orderbekräftelseruta för at.js 1.*x* med samma metod, Metoden är dock att föredra [!DNL at.js] . Mer information finns i [Spåra konverteringar](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
   >
   >
* Om du använder at.js 2.*x*, `mboxCreate` stöds inte längre. För orderbekräftelse med at.js 2.*x* använder du följande spårningsrelaterade API:er: [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) och [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).


1. Infoga mbox-skriptet efter modellen nedan på sidan med orderinformation.
1. Ersätt ORD I VERSALA BOKSTÄVER med antingen dynamiska eller statiska värden från katalogen.

   >[!NOTE]
   >
   >Använd kommaavgränsning för att avgränsa flera produkt-ID:n.

   **Tips:** Du kan också skicka beställningsinformation i valfri ruta (den behöver inte namnges `orderConfirmPage`). Du kan också skicka beställningsinformation i flera rutor inom samma kampanj.

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