---
keywords: Implementation;mbox.js non javascript;mbox;adbox
description: Använd en AdBox för att leverera bilder i en implementering utanför webbplatsen med Adobe Target.
title: Skapa en Adbox för en bild med Adobe Target
feature: email implementation
subtopic: Getting Started
topic: Standard
uuid: 6b1763f7-08de-4bde-9e20-e79b92b02f20
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# Skapa en Adbox för en bild{#create-an-adbox-for-an-image}

Använd en AdBox för att leverera bilder i en implementering utanför webbplatsen med Adobe Target.

En AdBox är som en mbox, men den styrs av en URL i stället för JavaScript. AdBox skapas med en särskild AdBox-URL som läser in en &quot;ad&quot;-ruta (eller AdBox) i ditt Adobe-konto. Använd den här AdBox istället för mbox i dina aktiviteter. Använd AdBox-URL:en i stället för en direkt bildreferens i e-postmeddelanden eller andra icke-JavaScript-implementeringar.

Hjälp med att välja rätt konfiguration finns i [Icke-JavaScript-baserade implementeringar](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. Skapa AdBox-URL:

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200&
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * Var `myClientCode` är företagets kundkod. Ditt företags klientkod är endast liten och har inga specialtecken.

      Klientkoden finns längst upp på [!UICONTROL Administation > Implementation] sidan i [!DNL Target] gränssnittet.

   * Var `image` är samtalstypen. I det här fallet är det en bild.

   * Där `emailHeroImage123_320x200` är namnet på AdBox.

   * Var `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` är mbox standardinnehåll. Det här måste vara en bild.

      Detta måste vara URL-kodat och måste vara en absolut referens. Du kan använda [HTML URL-kodningsreferens](https://www.w3schools.com/tags/ref_urlencode.asp) för att snabbt koda dina URL-adresser.

1. Skapa [omdirigeringserbjudanden](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) för varje alternativ bild.

   >[!NOTE]
   >
   >AdBoxes måste läsas in med ett omdirigeringserbjudande eller standarderbjudandet. Andra erbjudandetyper fungerar inte. Eftersom AdBox är en URL kan den bara visa de URL:er som den tar emot, så endast omdirigeringserbjudandet fungerar.

1. Skapa aktiviteten.

   Se [Icke-JavaScript-baserade implementeringar](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) för rätt inställningar för att uppnå dina mål.
1. Slutför Frågor och svar om aktiviteten.

   Det bästa är att skapa en dummy-sida och verifiera att alla upplevelser, standardinnehåll och rapporter fungerar som förväntat i alla webbläsartyper, för alla dina miljöer.

1. Starta aktiviteten.
