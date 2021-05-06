---
keywords: mål;a4t;geo;geotargeting;geotargeting precision;land;state;city;zip code;dma;mobile company;city codes;region codes;country codes;metro codes;profile scripts;geotargeting profile scripts;geotargeting mobile
description: Lär dig hur du skapar målgrupper i Adobe [!DNL Target] utifrån deras geografiska plats, inklusive land, ort, postnummer med mera.
title: Kan jag [!DNL Target] besöksbaserad plats?
feature: Målgrupper
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
translation-type: tm+mt
source-git-commit: 32eeec786af7aba747881ac84ef17d7a0124a45a
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 2%

---

# Geo

Använd målgrupper i [!DNL Adobe Target] för att rikta in er på användare baserat på deras geografiska plats, inklusive land, stat/provins, ort, postnummer, DMA eller mobiloperatör.

Med parametrar för geografisk plats kan ni inrikta er på aktiviteter och upplevelser baserat på besökarnas geografiska läge. Du kan inkludera eller exkludera besökare baserat på land, stat/provins, stad, postnummer, latitud, longitud, DMA eller mobiloperatör. Dessa data skickas med varje [!DNL Target]-begäran och baseras på besökarens IP-adress. Välj de här parametrarna precis som andra målvärden.

## Skapa en målgrupp med geomål {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Geo]**.

1. Klicka på **[!UICONTROL Select]** och välj sedan ett av följande alternativ:

   * Land
   * Läge
   * Ort
   * Postnummer
   * Latitud
   * Longitud
   * DMA
   * Mobiloperatör

   En besökares IP-adress skickas med en mbox-begäran, en gång per besök (session), för att matcha parametrar för geomål för den besökaren.

   För mobiloperatör använder [!DNL Target] IP-adressregistreringsuppgifterna (som äger block med IP-adresser) för att avgöra vilket mobilföretag som är lämpligt med [MCC (Mobile Country Codes) och MNC (Mobile Network Codes)](https://www.mcc-mnc.com).

1. Ange en operator och lämpligt värde.
1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** och ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Save]**.

I följande bild visas en målgrupp som riktar sig till användare som har åtkomst till aktiviteten från en latitud större än 44° och en longitud mindre än 22°.

![](assets/target_geo.png)

## Noggrannhet {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

Exaktheten i målinriktningen beror på flera faktorer. WiFi-anslutningar är exaktare än mobilnät. När besökaren använder en mobildataanslutning kan geo-lookup-noggrannheten påverkas av plats, providerns datarelation med [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) och andra faktorer. Celltornbaserade nätverksanslutningar kan vara mindre noggranna än kabelanslutningar och WiFi-anslutningar. En besökares IP-adress kan också mappas till besökarens Internet-leverantör, som kanske inte är samma som besökarens faktiska plats. Vissa problem med mobil geopositionering kan lösas med hjälp av [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

I följande tabell visas precisionen för IP-baserad geografisk information från [DigitalEnvoy](https://www.digitalelement.com/solutions/) för kabelanslutna eller WiFi-internetanslutningar. DigitalEnvoy ger branschens mest korrekta data. Den globala precisionen är mer än 99,9 procent på landsnivå och är upp till 97 procent korrekt på stadsnivå. Noggrannhetsinformation gäller inte för celltornbaserade nätverk.

| Land | Läge | Ort | Län |
|--- |--- |--- |--- |
| USA | 99,99 % | 96 % | 94 % |
| Kanada | 99,99 % | 96 % | 94 % |
| Europa | 99,99 % |  |  |
| Storbritannien | 99,99 % |  | 87 % |
| Tyskland | 99,99 % | 95 % | 93 % |
| Skandinavien | 99 % | Låg 90-tal | Mid 80s |
| Spanien | 99,99 % | Cirka 90 % | Från medelhög till hög 90-tal |
| Asien | 99 % | Mid 90s | Låg 90-tal |
| Japan | 99,99 % | Mid 90s | Låg 90-tal |
| Australien | 99,99 % | 94 % | 91 % |

## Använda geolokalisering i profilskript {#section_92C93138542C4A94997E3F4BE3F5DA28}

Du kan använda geoinformation för profilskript.

Använd till exempel:

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`

Du kan skriva ett måluttryck som heter&quot;Från Nordamerika&quot; med följande kod:

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## Använda georiktade värden som token {#section_E7F7FDF62C3B4934A6565D04B24655F6}

Du kan nu använda `profile.geolocation`-värden direkt som token i erbjudanden, plugin-program och så vidare.

Använd till exempel:

* `${profile.geolocation.country}`
* `${profile.geolocation.state}`
* `${profile.geolocation.city}`
* `${profile.geolocation.zip}`
* `${profile.geolocation.dma}`
* `${profile.geolocation.domainName}`
* `${profile.geolocation.ispName}`
* `${profile.geolocation.connectionSpeed}`
* `${profile.geolocation.mobileCarrier}`
* `${profile.geolocation.latitude}`
* `${profile.geolocation.longitude}`

## Geotargeting FAQ {#section_DD308A53AF0F48FA8C81423580561FE7}

**Hur anger jag latitud och longitud?**

* Värdet för latitud/longitud ska vara ett numeriskt värde i grader.
* Värdet för latitud/longitud kan ha en maxprecision på fem decimaler.
* Värdet för latitud måste vara mellan -90 och 90.
* Värdet för longitud ska vara mellan -180 och 180.

**Hur fungerar målinriktning mot geo för mobila enheter?**

De flesta användare av mobila enheter får tillgång till innehåll via WiFi, vilket innebär att IP-baserad geoanpassning för [!DNL Target] är lika exakt som för en dator. Celltornbaserade anslutningar kan vara mindre exakta eftersom besökarens IP-adress baseras på tornet där signalen hämtas. Vissa problem med mobil geopositionering kan lösas med hjälp av [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

**Hur hanterar geo besökare från AOL?**

På grund av hur AOL proxies sin trafik kan [!DNL Target] bara rikta sig till dem på landsnivå. En kampanj som riktar sig till Frankrike riktar sig till exempel till AOL-användare i Frankrike. Men en kampanj som riktar sig till Paris har inte lyckats rikta sig till AOL-användare i Paris. Om du avser att särskilt rikta in dig på AOL-användare kan du ställa in regionfältet på &quot;aol&quot;. Man kan faktiskt rikta in sig på AOL-användare genom att ange två målinriktningsvillkor: land matchar exakt&quot;USA&quot; och region matchar&quot;aol&quot;.

**Vilken platsgranularitet ger målinriktning?**

* Land - globalt
* Stat/provins/region - global
* Ort - global
* Postnummer - USA, Tyskland, Kanada
* DMA/ITV (UK) - USA, Storbritannien
* Mobiloperatör - globalt

**Hur testar jag mina aktiviteter som om jag är en användare som kommer från en annan plats?**

* **at.js 1.*x***: Du kan åsidosätta din IP-adress med en IP-adress från en annan plats och använda  `mboxOverride.browserIp url` parametern. Så om ert företag är i Storbritannien, men er globala kampanj riktar sig till besökare i Auckland i Nya Zeeland, använder du den här typen av URL under förutsättning att `60.234.0.39` är en IP-adress i Auckland:

   `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

   Rensa dina cookies innan du testar aktiviteten.

   >[!NOTE]
   >
   >`mboxOverride.browserIp` stöds i at.js 1.*Endast* . Den här funktionen stöds inte i at.js 2.*x*.

* **at.js 2.*x***: Om du vill åsidosätta din IP-adress med at.js 2.*x* installerar du ett webbläsartillägg/plugin-program (till exempel X-Forwarded-For Header för Chrome eller Firefox). Med det här tillägget kan du skicka det x-vidarebefordrade sidhuvudet i dina sidförfrågningar.

**Hur är områden, som Puerto Rico och Hong Kong, mappade till strukturen för geografisk anpassning?**

Puerto Rico, Hong Kong och andra territorier behandlas som separata&quot;Country&quot;-värden.

**Hämtar (och lagrar)  [!DNL Target] information som Zip-koder när aktiviteten är inriktad på geo-location-målinriktning?**

Nej, [!DNL Target] använder endast geodata under sessionen, och data ignoreras.

## Utbildningsvideo: Skapar publik ![Självstudiekursikon](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
