---
keywords: dataavvikelser;analys;skillnader;avvikelse;a4t;analys för mål;analys som rapportkälla;avvikelser;avvikelser
description: Lär dig mer om de förväntade dataavvikelserna mellan Adobe Target och Analytics när du inte använder Analytics for Target (A4T), vilket eliminerar helt olika datavariationer.
title: Vad är den förväntade datavariansen mellan Analytics och A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# Förväntade datavariationer mellan Adobe Target och Adobe Analytics när A4T används och inte används

Information om förväntade dataavvikelser mellan [!DNL Target] och Adobe [!DNL Analytics] när *använder* och *inte* använder Analytics som rapportkälla (A4T). A4T minskar datavariansen avsevärt.

## Förväntad datavarians vid användning av A4T {#expected-using-a4t}

Med A4T använder både Analytics- och Target-rapportering av aktiviteter enbart analysdata, vilket innebär att det finns få skillnader mellan lösningarna i Target-aktivitetsrapporter. I vissa fall jämför kunderna Target-data med Analytics-data som ligger utanför A4T-integreringens omfång och upplever därmed de variationsproblem som beskrivs nedan.

Här följer några scenarier där du kan få en förväntad datavariation:

* A4T tillåter möjligheten att en Target-träff (överst på sidan) inträffar, men ingen Analytics-träff (nederst på sidan) inträffar. Anta till exempel att en besökare läser in sidan, men stänger webbläsaren innan Analytics-anropet utlöses. I dessa fall utesluter A4T Target-träffen från data. Om Target-träffar (återigen, överst på sidan) räknas som Analytics-träffar i avsaknad av ett faktiskt Analytics-anrop skapas inkonsekvenser med de data som anges i Analytics (besökarinflationen osv.).

   Om ett omdirigeringstest har ställts in i Target för att dela upp trafik 50/50 (eller 25/25/25/25 och så vidare), är det inte säkert att användarbeteendet delas jämnt. Om du ser en ojämn delning betyder det bara att en grupp användare inte kunde genomföra ett Analytics-anrop på landningssidan mer än vad de andra grupperna gjorde. Det här misslyckandet med att köra Analytics-anropet för en grupp gjorde att Target-träffen för den användaren uteslöts, vilket skapade ojämnheten.

   Adobe hoppas kunna ta itu med denna fråga i framtiden när Adobe team arbetar mot A4T på Adobe Experience Platform. Adobe team avgör hur de olika händelserna ska hanteras vid olika tidpunkter på sidan.

   >[!NOTE]
   >
   >Det finns ett känt fel som gör att ett begränsat antal kunder använder omdirigeringar med A4T för att se en högre procentandel av antalet träffar som inte sammanställts. Se [Kända fel och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Datavarians förväntades när *inte använder* A4T {#expected-not-using-a4t}

Variationer på 15-20 % är normala, även med liknande datauppsättningar. System som räknas olika kan ge mycket större dataavvikelser, upp till 35-50 %. Ibland kan avvikelser vara ännu högre.

Även om faktiska data kan variera avsevärt är trenderna vanligtvis konsekventa. Så länge skillnaderna och trenderna är konsekventa förblir data värdefulla och användbara. Om skillnaderna och trenderna är inkonsekventa kan det betyda att något är felaktigt inställt. Kontakta i så fall din kontorepresentant för att få hjälp.

[!DNL Analytics] använder ett system som bygger på besök och transaktioner, men  [!DNL Target] använder besöksbaserade mått. När en besökare öppnar en sida räknas det som ett besök i [!DNL Analytics], men [!DNL Target] räknar inte besöket förrän de villkor som angetts i aktiviteten är uppfyllda.

Rapporter i [!DNL Target] visar prestanda baserat på den konverteringsruta som valts när aktiviteten definierades. Dessa konverteringsrutedata skickas dock inte till [!DNL Analytics], som har egna konverteringsvariabler som definieras av [!DNL Analytics]-taggimplementeringen. Där du förväntar dig identiska data (till exempel om en återförsäljares beställning bekräftar att sidan innehåller både en konverteringsruta och en [!DNL Analytics]-köphändelse) kan data variera beroende på placeringen av dessa taggar. Generellt sett är trenderna i de två produktrapporterna likartade.

Förväntade dataavvikelser kan orsakas av både tekniska och affärsmässiga avvikelser.

### Exempel på tekniska avvikelser {#section_C3B50ED2E2F9416FAC91437CF1A87369}

Följande kan orsaka dataavvikelser baserade på tekniska skillnader:

* [!DNL Target] besökarna måste tillåta cookies och JavaScript
* cookies från första och tredje part behandlas på olika sätt; därför matchar inte data från dessa cookie-typer
* Relativ placering av taggar på sidor och&quot;läckage&quot; som orsakas av besökare som lämnar sidan innan den har lästs in helt
* Tidszonshändelser
* Skillnader i vilka enheter kan räknas

### Exempel på affärsvarianter {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

Följande kan orsaka dataavvikelser baserade på affärsskillnader:

* Skillnader mellan besöks- och besökssiffror
* Att rikta in sig på aktiviteter utesluter vissa besökare
* En enda mbox på flera sidor där besökarna på varje sida räknas
* Aktivitetsprioriteringarna kan omfatta vissa besökare och utesluta andra på en sida
* Besökare som har konverterat en gång kan räknas igen när de återgår till aktiviteten
* [!DNL Analytics] räknar alla konverteringar för alla besök och besökare, men  [!DNL Target] räknar endast konverteringar för de besök och besökare som ingår i aktiviteten