---
keywords: data variances;analytics;differences;variance;a4t;analytics for target;analytics as the reporting source;discrepancies;discrepancy
description: Information om förväntade dataavvikelser mellan Target och Adobe Analytics när Analytics inte används som rapportkälla (A4T), vilket eliminerar helt olika datavariationer.
title: Förväntade datavarianser när A4T inte används
feature: null
topic: Advanced
uuid: 61bef460-8613-4251-b1b2-b6226ec86d9b
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 0%

---


# Förväntade datavariationer mellan Target och Analytics när A4T används och inte används{#expected-data-variances-when-not-using-a-t}

Information om förväntade dataavvikelser mellan [!DNL Target] och Adobe [!DNL Analytics] när *Analytics används* och *inte* används som rapportkälla (A4T). A4T minskar datavariansen avsevärt.

## Förväntad datavarians vid användning av A4T {#expected-using-a4t}

Med A4T använder både Analytics- och Target-rapportering av aktiviteter enbart analysdata, vilket innebär att det finns få skillnader mellan lösningarna i Target-aktivitetsrapporter. I vissa fall kan kunderna dock jämföra Target-data med analysdata som ligger utanför A4T-integreringens omfång och därmed uppleva de variationsproblem som beskrivs nedan.

Här följer några scenarier där du kan få en förväntad datavariation:

* A4T tillåter möjligheten att en Target-träff (överst på sidan) inträffar, men ingen Analytics-träff (nederst på sidan) inträffar. Ett exempel på detta skulle vara om användaren läser in sidan, men stänger webbläsaren innan Analytics-anropet utlöstes. I dessa fall utesluter A4T Target-träffen från våra data. Anledningen till detta är att om Target-träffar (återigen den översta sidan) räknas som Analytics-träffar i avsaknad av ett riktigt Analytics-anrop skulle detta skapa inkonsekvenser med de data som anges i Analytics (besökaruppblåsning, osv.).

   Om ett omdirigeringstest har ställts in i Target för att dela upp trafik 50/50 (eller 25/25/25/25, osv.), är det inte säkert att användarbeteendet delas jämnt. Om du ser en ojämn delning innebär det helt enkelt att en grupp användare inte kunde genomföra ett Analytics-anrop på landningssidan mer än vad de andra grupperna gjorde. Det här misslyckandet med att köra Analytics-anropet för en grupp gjorde att Target-träffen för den användaren uteslöts, vilket skapade ojämnheten.

   Det här är något vi hoppas kunna ta upp i framtiden när vi arbetar mot A4T på Adobe Experience Platform. Våra team arbetar på hur de bäst hanterar de olika händelser som inträffar vid olika tidpunkter på sidan.

   >[!NOTE]
   >
   >Det finns ett känt fel som gör att ett begränsat antal kunder använder omdirigeringar med A4T för att se en högre procentandel av antalet träffar som inte sammanställts. Se [Kända fel och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

* Anta att du skapar en automatiskt fördelad aktivitet som är öppen för alla besökare på en viss sida. Eftersom Automatisk allokering inte stöder A4T, samlas alla aktivitetsdata in av [!DNL Target]. Du kanske förväntar dig att besökarna i aktiviteten i rapporten ska matcha besökarna till den sidan i [!DNL Target] [!DNL Analytics] rapporteringen för samma datumintervall. Detta är ett scenario där den avvikelse som beskrivs nedan förväntas.

   En fullständig lista över aktivitetstyper som stöder A4T finns i [Aktivitetstyper](../../c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)som stöds.

## Förväntad datavarians när *inte A4T används* {#expected-not-using-a4t}

Variationer på 15-20 % är normala, även med liknande datauppsättningar. System som räknas olika kan ge mycket större dataavvikelser, upp till 35-50 %. I vissa fall kan avvikelserna vara ännu högre.

Även om faktiska data kan variera avsevärt är trenderna vanligtvis konsekventa. Så länge skillnaderna och trenderna är konsekventa förblir data värdefulla och användbara. Om skillnaderna och trenderna är inkonsekventa kan det betyda att något är felaktigt inställt. Kontakta i så fall din kontorepresentant för att få hjälp.

[!DNL Analytics] använder ett system som bygger på besök och transaktioner, men [!DNL Target] använder besöksbaserade mått. Det innebär att när en besökare öppnar en sida räknas det som ett besök i [!DNL Analytics], men [!DNL Target] räknar inte besöket förrän de villkor som anges i aktiviteten är uppfyllda.

Rapporter i [!DNL Target] visar prestanda baserat på den konverteringsruta som valts när aktiviteten definierades, men konverteringsrutedata skickas inte till [!DNL Analytics], som har egna konverteringsvariabler som definierats av [!DNL Analytics] taggimplementeringen. Om du förväntar dig identiska data (t.ex. om en återförsäljares bekräftelsesida innehåller både en konverteringsruta och en [!DNL Analytics] köphändelse) kan data variera beroende på placeringen av dessa taggar. I allmänhet bör trenderna i de två produktrapporterna vara desamma.

Förväntade dataavvikelser kan orsakas av både tekniska och affärsmässiga avvikelser.

### Exempel på tekniska avvikelser {#section_C3B50ED2E2F9416FAC91437CF1A87369}

Följande kan orsaka dataavvikelser baserade på tekniska skillnader:

* [!DNL Target] besökarna måste tillåta cookies och JavaScript
* cookies från första och tredje part behandlas på olika sätt; därför matchar inte data från dessa cookie-typer
* Relativ placering av taggar på sidor och&quot;läckage&quot; som orsakas av besökare som lämnar sidan innan den har lästs in helt
* Tidszonshändelser
* Skillnader i vilka enheter kan räknas

### Exempel på affärsavvikelser {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

Följande kan orsaka dataavvikelser baserade på affärsskillnader:

* Skillnader mellan besöks- och besökssiffror
* Att rikta in sig på aktiviteter utesluter vissa besökare
* En enda ruta kan placeras på flera sidor, där besökarna på varje sida räknas
* Aktivitetsprioriteringarna kan omfatta vissa besökare och utesluta andra på en sida
* Besökare som har konverterat en gång kan räknas igen när de återgår till aktiviteten
* [!DNL Analytics] räknar alla konverteringar för alla besök och besökare, men [!DNL Target] räknar endast konverteringar för de besök och besökare som ingår i aktiviteten