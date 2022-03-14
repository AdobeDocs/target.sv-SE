---
keywords: rekommendationer;vanliga frågor;frågor
description: Granska en lista med vanliga frågor och svar om Adobe [!DNL Target] Recommendations designar.
title: Var kan jag svara på designfrågor för [!DNL Target] Recommendations?
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Vanliga frågor om design

Lista med vanliga frågor och svar om [!DNL Adobe Target] [!DNL Recommendations] design.

## Det rekommenderade objektets pris visar inte båda värdena till höger om decimalkommat. Hur visar jag dem?

Som standard används numeriska värden (som `entity.value`) som returneras i designmallar visar inga efterföljande nollor efter decimalkommat. Om ett objekt till exempel är $35.00, `entity.value` är lika med 35 och endast 35 visas på sidan, inte $35.00.

Det finns två alternativ för att åtgärda problemet:

* Du kan använda Velocity-skript eller Javascript om du vill formatera det returnerade värdet.

* Du kan skicka priset på artikeln till två separata entitetsattribut. Den första, `entity.value`, kan användas för numeriska jämförelser (t.ex. prisjämförelseregler). Den andra ska vara ett anpassat attribut, som `entity.displayValue` som lagrar värdet för entiteten som en sträng för korrekt återgivning.

   Exempel:

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## Varför visas inte kategorier i designen? Jag använder `$entity1.categoryId`. {#section_073309B8051049C7953D396A93EA0713}

Kategori-ID kan inte visas i designen. Eftersom flera kategorier kan lagras vet systemet inte vilken kategori som ska visas.

## Hur ska jag ändra en design för att få en omedelbar uppdatering? {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

Det tar en stund att uppdatera den design som används. Om du vill ändra designen direkt skapar du en ny design, markerar den i aktiviteten och sparar rekommendationen.

## Hur samlar jag in viktig information som ska visas i designen? Exempel: Om vi vill visa nyckelproduktens kategori, hur skulle jag koda det värdet i snabbdesignen? {#section_F08043B14BA24BC8815FEF25F4F84C39}

The `$key. *`value`*` parametern hämtar större delen av nyckelproduktens information som ska visas i designen. Exempel: Om du vill visa nyckelproduktens miniatyrbild använder du `$key.thumbnailURL`.

## Vilken version av Velocity används? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

Version 1.7 utan ytterligare verktyg eller bibliotek tillagda i. Det finns grundläggande snabbhetsfunktioner.

## Hur ersätter jag ett befintligt enhetsvärde med ett tomt värde? Till exempel måste ett objekts entity.message rensas när en kampanj avslutas. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Att skicka i ett JavaScript-baserat hårt blanksteg verkar göra detta. Låt utvecklarna skicka in `\u00A0` som värdet. Exempel: `entity.message=\u00A0`. Du kan överväga att använda det som standardvärde när det inte finns något värde i stället för ett null-värde.

## Kan jag använda ett profilskript i en [!DNL Recommendations] design? {#section_6BD55203984A4D80A0C6F241AD7806DF}

Ja. Använda ett profilskript i en [!DNL Recommendations] design, radbryta namnet i `\${...}`. Om ditt profilskript till exempel har namnet `user.basket`, se det som `\${user.basket}` i designen. Observera att det omvända snedstrecket innebär att profilskriptet inte återges av Velocity. Du kan därför inte utföra några åtgärder på profilskriptet i en Velocity-mall. Värdet skrivs ut direkt på sidan.
