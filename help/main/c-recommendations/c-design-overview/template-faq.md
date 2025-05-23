---
keywords: rekommendationer;vanliga frågor;frågor
description: Vanliga frågor och svar om  [!DNL Target Recommendations] design.
title: Var kan jag få svar på designfrågor för  [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
source-git-commit: eba9e0b02ce74fea127d2cb2d08d04dcd2da2d76
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 0%

---

# Vanliga frågor om design

Lista med vanliga frågor och svar om [!DNL Adobe Target] [!DNL Recommendations]-designer.

## Det rekommenderade objektets pris visar inte båda värdena till höger om decimalkommat. Hur visar jag dem?

Som standard kommer numeriska värden (till exempel `entity.value`) som returneras i designmallar inte att visa efterföljande nollor efter decimalkommat. Om ett objekt till exempel är $35.00 är `entity.value` lika med 35 och bara 35 visas på sidan, inte $35.00.

Det finns två alternativ för att åtgärda problemet:

* Du kan använda Velocity-skript eller Javascript om du vill formatera det returnerade värdet.

* Du kan skicka priset på artikeln till två separata entitetsattribut. Den första, `entity.value`, kan användas för numeriska jämförelser (till exempel prisjämförelseregler). Den andra bör vara ett anpassat attribut, till exempel `entity.displayValue`, som lagrar värdet för entiteten som en sträng för att möjliggöra korrekt återgivning.

  Exempel:

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## Varför visas inte kategorier i designen? Jag använder `$entity1.categoryId`. {#section_073309B8051049C7953D396A93EA0713}

Kategori-ID kan inte visas i designen. Eftersom flera kategorier kan lagras vet systemet inte vilken kategori som ska visas.

## Hur ska jag ändra en design för att få en omedelbar uppdatering? {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

Det tar en stund att uppdatera den design som används. Om du vill ändra designen direkt skapar du en ny design, markerar den i aktiviteten och sparar rekommendationen.

## Hur samlar jag in viktig information som ska visas i designen? Exempel: Om vi vill visa nyckelproduktens kategori, hur skulle jag koda det värdet i snabbdesignen? {#section_F08043B14BA24BC8815FEF25F4F84C39}

Parametern `$key. *`value`*` hämtar större delen av nyckelproduktens information som ska visas i designen. Om du till exempel vill visa nyckelproduktens miniatyrbild använder du `$key.thumbnailURL`.

## Vilken version av Velocity används? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

Version 1.7 utan ytterligare verktyg eller bibliotek tillagda i. Det finns grundläggande snabbhetsfunktioner.

## Hur ersätter jag ett befintligt enhetsvärde med ett tomt värde? Till exempel måste ett objekts `entity.message` rensas när en befordran avslutas. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Att skicka i ett hårt JavaScript-format verkar göra detta. Låt utvecklarna skicka in `\u00A0` som värde. Exempel: `entity.message=\u00A0`. Du kan överväga att använda det som standardvärde när det inte finns något värde i stället för ett null-värde.

## Kan jag använda ett profilskript i en [!DNL Recommendations]-design? {#section_6BD55203984A4D80A0C6F241AD7806DF}

Ja. Om du vill använda ett profilskript i en [!DNL Recommendations]-design måste du omsluta namnet i `\${...}`. Om ditt profilskript till exempel heter `user.basket`, refererar du det som `\${user.basket}` i designen. Observera att det omvända snedstrecket innebär att profilskriptet inte återges av Velocity. Du kan därför inte utföra några åtgärder på profilskriptet i en Velocity-mall. Värdet skrivs ut direkt på sidan.
