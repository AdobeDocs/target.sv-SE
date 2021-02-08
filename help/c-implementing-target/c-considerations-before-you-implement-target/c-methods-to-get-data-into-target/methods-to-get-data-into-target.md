---
keywords: implementera;implementera;konfigurera;konfigurera;sidparameter;tomcat;url-kodad;in page profile attribute;mbox parameter;in page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;data provider;data provider
description: Hämta data till Target (sidparametrar, profilattribut, skriptprofilattribut, dataleverantörer, uppdaterings-API:er för en och flera profiler, kundattribut).
title: Hur får jag in data i Target?
feature: Implementation
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Metoder för att hämta data till Target

Information om de olika metoder du kan använda för att hämta data till [!DNL Adobe Target], inklusive sidparametrar, profilattribut på sidan, skriptprofilattribut, DataProvider, API för satsprofiluppdatering, API för uppdatering av en profil samt kundattribut.

## Sidparametrar (kallas även&quot;mbox parameters&quot;) {#section_5A297816173C4FE48DC4FE03860CB42B}

Sidparametrar är namn/värde-par som skickas direkt via sidkod och som inte lagras i besökarens profil för framtida bruk.

Sidparametrar är användbara när du vill skicka ytterligare siddata till Target som inte behöver lagras med besökarens profil för framtida målinriktning. Dessa värden används i stället för att beskriva sidan eller den åtgärd som användaren utförde på den specifika sidan.

### Format

Sidparametrar skickas till Target via ett serveranrop som ett strängnamn/värde-par. Parameternamn och värden kan anpassas (även om det finns &quot;reserverade namn&quot; för vissa användningsområden).

Exempel:

* `page=productPage`

* `categoryId=homeLoans`

### Exempel på användningsfall

**Produktsidor**: Skicka information om den specifika produkten som visas (så här fungerar Recommendations)

**Beställningsinformation**: Skicka order-ID, orderTotal o.s.v. för ordersamling

**Kategoritillhörighet**: Skicka kategorivisad information till Target för att skapa kunskap om användarens tillhörighet till särskilda webbplatskategorier

**Tredjepartsdata**: Skicka information från externa datakällor, som till exempel leverantörer av väderanpassning, kontodata (till exempel DemandBase), demografiska data (till exempel Experience) och mycket mer.

### Fördelar med metoden

Data skickas till Target i realtid och kan användas på samma server för att anropa de data som de kommer in på.

### Caveats

* Kräver uppdatering av sidkod (direkt eller via ett tagghanteringssystem).
* Om data behöver användas för att rikta in sig på en efterföljande sida/server-anrop måste de översättas till ett profilskript.
* Frågesträngar får endast innehålla tecken enligt standarden [IETF (Internet Engineering Task Force)](https://www.ietf.org/rfc/rfc3986.txt).

   Förutom de som nämns på IETF-webbplatsen tillåter Target följande tecken i frågesträngar:

   `&lt; > # % &quot; {} | \\ ^ \[\] \&quot;

   Allt annat måste vara url-kodat. Standarden anger följande format ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), enligt nedan:

   ![](assets/ietf1.png)

   Eller hela listan för enkelhet:

   ![](assets/ietf2.png)

### Kodexempel

targetPageParamsAll (bifogar parametrarna till alla mbox-anrop på sidan):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (lägger till parametrarna i den globala mbox på sidan):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Parametrar i mboxSkapa kod:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

### Länkar till relevant information

Recommendations: [Implementering enligt sidtyp](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Orderbekräftelse: [Spåra konverteringar](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Kategoritillhörighet: [Kategoritillhörighet](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)

## Profilattribut på sidan (kallas även &quot;in-mbox profile attributes) {#section_57E1C161AA7B444689B40B6F459302B6}

Profilattribut på sidan är namn/värde-par som skickas direkt via sidkoden och som lagras i besökarens profil för framtida bruk.

Med profilattribut på sidan kan användarspecifika data lagras i Target-profilen för senare målinriktning och segmentering.

### Format

Profilattribut på sidan skickas till Target via ett serveranrop som ett strängnamn/värde-par med prefixet &quot;profile&quot;. före attributnamnet.

Attributnamn och värden är anpassningsbara (även om det finns &quot;reserverade namn&quot; för vissa användningsområden).

Exempel:

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

### Exempel på användningsfall

**Inloggningsinformation**: Dela icke-PII-data (Personally Identiitable Information) till Target baserat på användarens inloggning. Det kan vara medlemskapsstatus, orderhistorik eller mer.

**Butiksinformation**: Spåra vilket arkiv som är användarens föredragna plats.

**Tidigare interaktioner**: Spåra vad användaren har gjort på webbplatsen tidigare för att informera om framtida personalisering.

### Fördelar med metoden

Data skickas till Target i realtid och kan användas i samma serveranrop som data kommer in i.

### Caveats

Kräver uppdatering av sidkod (direkt eller via ett tagghanteringssystem).

Attribut och värden visas vid serveranrop, så att besökaren kan se värdena. Om du delar information som kreditintervall eller annan potentiellt privat information kanske detta inte är det bästa sättet.

### Kodexempel

targetPageParamsAll (bifogar attributen till alla mbox-anrop på sidan):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (appends the attributes to the global mbox on the page):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Attribut i mboxSkapa kod:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

### Länkar till relevant information

[Profilattribut](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Besökarprofil](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)

## Skriptprofilattribut {#section_3E27B58C841448C38BDDCFE943984F8D}

Skriptprofilattribut är namn/värde-par som definieras i Target-lösningen. Värdet avgörs av om ett JavaScript-fragment körs på målservern per serveranrop.

Användare skriver små kodfragment som körs per mbox-anrop och innan en besökare utvärderas för målgrupps- och aktivitetsmedlemskap.

### Format

Skriptprofilattribut skapas i målgruppsavsnittet. Alla attributnamn är giltiga och värdet är resultatet av en JavaScript-funktion som skrivits av Target-användaren. Attributnamnet prefixeras automatiskt av användaren . &quot; i Target för att skilja dem från profilattribut på sidan.

Kodfragmentet är skrivet i JS-språket Rhino och kan referera till tokens och andra värden.

### Exempel på användningsfall

**Cart Abandonment**: När besökaren når kundvagnen ställer du in profilskriptet på 1. Återställ besökaren till 0 när besökaren konverterar. Om värdet = 1 har besökaren en artikel i kundvagnen.

**Besök Antal**: Vid varje nytt besök ökar du antalet med 1 för att hålla reda på hur ofta en besökare återvänder till webbplatsen.

### Fördelar med metoden

Inga sidkodsuppdateringar krävs.

Körs före målgrupps- och aktivitetsmedlemskapsbeslut, så dessa profilskriptattribut kan påverka medlemskapet för ett enda serversamtal.

Kan vara mycket robust. Upp till 2 000 instruktioner kan köras per skript.

### Caveats

Kräver JavaScript-kunskaper.

Körningsordningen för profilskript kan inte garanteras, så de kan inte vara beroende av varandra.

Kan vara svårt att felsöka.

### Kodexempel

Profilskript är relativt flexibla:

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### Länkar till relevant information

[Profilskriptattribut](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)

## Dataleverantörer {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

Data Providers är en funktion som gör att du enkelt kan skicka data från tredje part till Target.

Obs! Data Providers kräver at.js 1.3 eller senare.

### Format

Inställningen `window.targetGlobalSettings.dataProviders` är en matris med dataleverantörer.

Mer information om strukturen för varje dataleverantör finns i [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Exempel på användningsfall

Samla in data från tredje part, t.ex. en vädertjänst, en datahanteringsplattform eller till och med din egen webbtjänst. Sedan kan ni använda dessa data för att skapa målgrupper, målinnehåll och berika besökarprofilen.

### Fördelar med metoden

Med den här inställningen kan kunder samla in data från tredjepartsleverantörer av data, som Demandbase, BlueKai och anpassade tjänster, och skicka data till Target som mbox-parametrar i den globala mbox-begäran.

Det stöder insamling av data från flera leverantörer via asynkrona och synkroniserade begäranden.

Med den här metoden blir det enkelt att hantera flimmer av standardsidinnehåll, samtidigt som oberoende tidsgränser för varje leverantör tas med för att begränsa effekten på sidans prestanda

### Caveats

Om dataleverantörerna som läggs till i `window.targetGlobalSettings.dataProviders` är asynkrona körs de parallellt. Besökar-API-begäran körs parallellt med funktioner som lagts till i `window.targetGlobalSettings.dataProviders` för att ge en minimal väntetid.

at.js försöker inte cachelagra data. Om dataleverantören bara hämtar data en gång, bör dataleverantören se till att data cachelagras och, när providerfunktionen anropas, hantera cachedata för det andra anropet.

### Kodexempel

Flera exempel finns i [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Länkar till relevant information

Dokumentation: [Dataleverantörer](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

### Utbildningsvideor:

* [Använda Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implementera Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html)

## API för gruppprofilsuppdatering {#section_92AB4820A5624C669D9A1F1B6220D4FA}

Via API skickar du en CSV-fil till Target med uppdateringar av besökarprofilen för många besökare. Varje besökarprofil kan uppdateras med flera profilattribut på sidan i ett anrop.

Det här alternativet liknar kundattribut med några skillnader:

* Kundattribut använder en FTP-överföring medan API:t för uppdatering av målgruppsprofil använder ett API för HTTP-POST.
* Data för kundattribut kan delas med Analytics. Det går bara att använda gruppprofilsuppdatering i Target.
* Kundattribut som stöder att skapa en profil för ett användarmål har ännu inte setts. API:t för uppdatering av gruppprofil uppdaterar bara befintliga målprofiler.
* Kundattribut kräver att Experience Cloud ID (ECID) används. API:t för uppdatering av gruppprofil kräver antingen TNT-ID eller `mbox3rdPartyId`.
* Du kan inte skicka följande tecken i `mbox3rdPartyID`: plustecken (+) och snedstreck (/).

### Format

CSV-filen måste referera till varje besökare via sitt Target PCID eller mboxThirdPartyId. Experience Cloud ID (ECID) stöds inte. Alla profilattribut/värden skapas och uppdateras via API:t. Formatinformation finns i API-dokumentationen.

### Exempel på användningsfall

CRM-systemet eller andra interna system lagrar värdefulla data om besökarna som du vill uppdatera konsekvent i Target, utan att visa profildata i din sidimplementering.

### Fördelar med metoden

Det finns ingen gräns för antalet profilattribut.

Profilattribut som skickas via webbplatsen kan uppdateras via API och vice versa.

### Caveats

Batchfilens storlek måste vara mindre än 50 MB. Dessutom bör det totala antalet rader inte överstiga 500 000 rader per överföring.

Det finns ingen gräns för hur många rader du kan överföra under 24 timmar i efterföljande batchar. Intag kan dock begränsas under kontorstid för att säkerställa att andra processer körs effektivt.

Flera [V2-batchuppdateringsanrop](https://developers.adobetarget.com/api/#updating-profiles) utan mbox-anrop däremellan för samma thirdPartyIds åsidosätter egenskaperna som uppdaterades i det första batchuppdateringsanropet.

### Kodexempel

Se [Uppdatera profiler](https://developers.adobetarget.com/api/#updating-profiles).

### Länkar till relevant information

[Uppdaterar profiler](https://developers.adobetarget.com/api/#updating-profiles)

## API för enkel profiluppdatering {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Nästan identiskt med API:t för uppdatering av gruppprofil, men en besökarprofil uppdateras åt gången, i linje i API-anropet i stället för med en CSV-fil

### Format

Besökaren måste identifieras via Target mboxPC-värdet eller mboxThirdPartyId-värdet. Experience Cloud ID (ECID) stöds inte.

### Exempel på användningsfall

Du vill uppdatera Target i realtid när en besökare utför en offlineåtgärd, som att nå en kundtjänst, ett lån finansieras, använda ett förmånskort i butiken, få tillgång till en kioskdator och så vidare.

### Fördelar med metoden

Det finns ingen gräns för antalet profilattribut.

Profilattribut som skickas via webbplatsen kan uppdateras via API och vice versa.

### Caveats

Gräns på 1 000 000 API-anrop (1 miljon) per 24-timmarsperiod

Uppdaterar endast profiler. Det går inte att skapa en profil för en potentiell användare som Target ännu inte ser.

### Kodexempel

GET och POST stöds. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Länkar till relevant information

[Uppdaterar profiler](https://developers.adobetarget.com/api/#updating-profiles)

## Kundattribut {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Med kundattribut kan du överföra besökarprofildata via FTP till Experience Cloud. Använd data i Adobe Analytics och Adobe Target när de har överförts.

Målgruppen Standard-kunder kan utnyttja fem attribut, Target Premium-kunder kan utnyttja 200 attribut.

### Format

En CSV-fil med Experience Cloud ID (ECID) och attributnamn/värde-par överförs via FTP eller manuellt i användargränssnittet för Experience Cloud.

### Exempel på användningsfall

CRM-systemet eller andra interna system lagrar värdefull information som du vill dela med Adobe Experience Cloud, inklusive Target och Analytics.

### Fördelar med metoden

När du överför kunddata skapas en profilpost för besökaren i Target, även om Target ännu inte har sett besökaren.

Samma data är automatiskt tillgängliga i Target och Analytics.

FTP kan vara en enklare implementeringsmetod än API.

### Caveats

Målkunder kan utnyttja fem attribut, Target Premium-kunder kan utnyttja 200 attribut

Kan bara uppdatera värden via kundattribut, inte på sidan.

Kräver implementering av Experience Cloud ID (ECID).

### Kodexempel

Mer information finns i [Skapa en kundattributkälla och överför datafilen](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Länkar till relevant information

[Skapa en kundattributskälla och överför datafilen](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).