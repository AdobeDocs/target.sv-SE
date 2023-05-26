---
keywords: mål;a4t;geo;geotargeting;geotargeting precision;land;state;city;zip code;dma;mobile company;city codes;region codes;country codes;metro codes;profile scripts;geotargeting profile scripts;geotargeting mobile
description: Lär dig skapa målgrupper i [!DNL Adobe Target] målgruppsanpassning baserat på deras geografiska plats.
title: Kan jag rikta besökarna baserat på plats?
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: 195028613dec0294c816703b9145e720e3209d74
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 1%

---

# Geo

Använd målgrupper i [!DNL Adobe Target] målgruppsanpassning baserat på deras geografiska plats.

Med parametrar för geografisk plats kan ni inrikta er på aktiviteter och upplevelser baserat på besökarnas geografiska läge. Du kan inkludera eller exkludera besökare baserat på land, stat/provins, stad, postnummer, latitud, longitud, DMA eller mobiloperatör. Dessa data skickas med varje [!DNL Target] begär och baseras på besökarens IP-adress. Välj de här parametrarna precis som andra målvärden.

## Skapa en målgrupp med målinriktning {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. I [!DNL Target] gränssnitt, klicka **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Geo]** till målgruppsverktyget.

1. Klicka **[!UICONTROL Select]** väljer du sedan något av följande alternativ:

   * [!UICONTROL Country/Region]
   * [!UICONTROL State]
   * [!UICONTROL City]
   * [!UICONTROL Zip Code]
   * [!UICONTROL Longitude]
   * [!UICONTROL Latitude]
   * [!UICONTROL DMA]
   * [!UICONTROL Mobile Carrier]

   En besökares geografiska information bestäms av den ursprungliga IP-adressen för en [!DNL Target] platsbegäran (mbox-begäran). IP-till-geo-upplösning utförs för det första anropet av en ny session. Det innebär att om IP-adressen för en besökare ändras under ett besök, så baseras geoinformationen fortfarande på IP-adressen för det första samtalet.

   För [!UICONTROL Mobile Carrier], [!DNL Target] använder IP-adressregistreringsuppgifterna (som äger IP-adressblocket) för att avgöra vilket mobiloperatör som använder [MCC (Mobile Country Codes) och MNC (Mobile Network Codes)](https://www.mcc-mnc.com).

1. Ange en operator och lämpligt värde.
1. (Valfritt) Ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Done]**.

I följande bild visas en målgrupp som riktar sig till användare som har åtkomst till aktiviteten från en latitud större än 44° och en longitud mindre än 22°.

![target_geo-bild](assets/target_geo.png)

## Noggrannhet {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

Exaktheten i målinriktningen beror på flera faktorer. WiFi-anslutningar är exaktare än mobilnät. När en besökare använder en mobildataanslutning kan noggrannheten för geosökningen påverkas av platsen, providerns datarelation med [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester)och andra faktorer. Celltornbaserade nätverksanslutningar kan vara mindre noggranna än kabelanslutningar och WiFi-anslutningar. En besökares IP-adress kan också mappas till besökarens Internet-leverantör, som kanske inte är samma som besökarens faktiska plats. Vissa problem med mobil geolokalisering kan lösas med [Geolocation-API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

I följande tabell visas riktigheten i IP-baserad geografisk information från [DigitalEnvoy](https://www.digitalelement.com/solutions/) för kabelanslutna eller WiFi-internetanslutningar. DigitalEnvoy ger branschens mest korrekta data. Den globala precisionen är mer än 99,9 procent på landsnivå och är upp till 97 procent korrekt på stadsnivå. Noggrannhetsinformation gäller inte för celltornbaserade nätverk.

| Land | Läge | Ort | Län |
|--- |--- |--- |--- |
| USA | 99.99% | 96% | 94% |
| Kanada | 99.99% | 96% | 94% |
| Europa | 99.99% |  |  |
| Storbritannien | 99.99% |  | 87% |
| Tyskland | 99.99% | 95% | 93% |
| Skandinavien | 99% | Låg 90-tal | Mid 80s |
| Spanien | 99.99% | Cirka 90 % | Från medelhög till hög 90-tal |
| Asien | 99% | Mid 90s | Låg 90-tal |
| Japan | 99.99% | Mid 90s | Låg 90-tal |
| Australien | 99.99% | 94% | 91% |

## Använd geoanpassning i profilskript {#section_92C93138542C4A94997E3F4BE3F5DA28}

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

## Använd geomål-värden som token {#section_E7F7FDF62C3B4934A6565D04B24655F6}

Du kan använda `profile.geolocation` värden direkt som tokens i erbjudanden, plugin-program och så vidare.

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

## Vanliga frågor om målinriktning {#section_DD308A53AF0F48FA8C81423580561FE7}

Följande frågor ställs ofta om geoanpassning:

### Hur anger jag latitud och longitud?

+++Se information
* Värdet för latitud och longitud ska vara ett numeriskt värde i grader.
* Värdet för latitud och longitud kan ha en maxprecision på fem decimaler.
* Värdet för latitud måste vara mellan -90 och 90.
* Värdet för longitud ska vara mellan -180 och 180.

+++

### Hur fungerar geoanpassning för mobila enheter?

+++Se information De flesta användare av mobila enheter får tillgång till innehåll via WiFi, vilket betyder [!DNL Target]Den IP-baserade geolokaliseringen är lika exakt som på en stationär dator. Celltornbaserade anslutningar kan vara mindre exakta eftersom besökarens IP-adress baseras på tornet där signalen hämtas. Vissa problem med mobil geolokalisering kan lösas med [Geolocation-API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

+++

### Hur hanterar geo besökare från AOL?

+++Se information På grund av hur AOL proxiderar sin trafik, [!DNL Target] kan endast rikta sig till dem på landsnivå. En kampanj som riktar sig till Frankrike riktar sig till exempel till AOL-användare i Frankrike. Men en kampanj som riktar sig till Paris har inte lyckats rikta sig till AOL-användare i Paris. Om du avser att särskilt rikta in dig på AOL-användare kan du ställa in regionfältet på &quot;aol&quot;. Man kan faktiskt rikta in sig på AOL-användare genom att ange två målinriktningsvillkor: land matchar exakt&quot;USA&quot; och region matchar&quot;aol&quot;.

+++

### Vilken platsgranularitet har geoanpassning?

+++Se information
* Land - globalt
* Stat/provins/region - global
* Ort - global
* Postnummer - USA, Tyskland, Kanada
* DMA/ITV (UK) - USA, Storbritannien
* Mobiloperatör - globalt

+++

### Hur testar jag mina aktiviteter som om jag är en användare som kommer från en annan plats?

+++Se information
* **at.js 1.*x***: Du kan åsidosätta din IP-adress med en IP-adress från en annan plats och använda `mboxOverride.browserIp url` parameter. Om ditt företag till exempel är i Storbritannien, men din globala kampanj riktar sig till besökare i Auckland i Nya Zeeland, använder du den här URL-adressen under förutsättning att `60.234.0.39` är en IP-adress i Auckland:

   `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

   Rensa dina cookies innan du testar aktiviteten.

   >[!NOTE]
   >
   >`mboxOverride.browserIp` stöds i at.js 1.*x* endast. Den här funktionen stöds inte i at.js 2.*x*.

* **at.js 2.*x***: Om du vill åsidosätta din IP-adress med at.js 2.*x*, installerar du ett webbläsartillägg/plugin-program (till exempel X-Forwarded-For Header för Chrome eller Firefox). Med det här tillägget kan du skicka det x-vidarebefordrade sidhuvudet i dina sidförfrågningar.

+++

### Hur är områden, som Puerto Rico och Hong Kong, mappade till strukturen för geografisk anpassning?

+++Se information om Puerto Rico, Hongkong och andra områden behandlas som separata värden för&quot;Land&quot;.

+++

### Gör [!DNL Target] hämta (och lagra) information som Zip-kod när aktiviteten är inriktad på geolokalisering?

+++Se information nr, [!DNL Target] använder endast geo-data under sessionen, och data ignoreras.

+++

## Utbildningsvideo: Skapa målgrupper ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
