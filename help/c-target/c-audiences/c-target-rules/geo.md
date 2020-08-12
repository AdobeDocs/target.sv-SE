---
keywords: targeting;a4t;geo;geotargeting;geotargeting accuracy;country;state;city;zip code;dma;mobile carrier;city codes;region codes;country codes;metro codes;profile scripts;geotargeting profile scripts;geotargeting mobile
description: Använd Adobe Target målgrupper för att rikta in er på användare baserat på deras geografiska plats, inklusive land, stat/provins, ort, postnummer, DMA eller mobiloperatör.
title: Geo
feature: null
solution: Target,Analytics
topic: Reports and analytics
uuid: d30cda0e-016e-4391-95b7-ff3b55e06bf0
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 2%

---


# Geo{#geo}

Använd målgrupper för att rikta in er på användare baserat på deras geografiska plats, inklusive land, stat/provins, ort, postnummer, DMA eller mobiloperatör.

Med parametrar för geografisk plats kan ni inrikta er på aktiviteter och upplevelser baserat på besökarnas geografiska läge. Du kan inkludera eller exkludera besökare baserat på land, stat/provins, stad, postnummer, latitud, longitud, DMA eller mobiloperatör. Dessa data skickas med varje Target-begäran och baseras på besökarens IP-adress. Välj de här parametrarna precis som andra målvärden.

## Skapa en målgrupp med geolokalisering {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. I [!DNL Target] gränssnittet klickar du **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Geo]**.

1. Klicka på **[!UICONTROL Select]** och välj sedan något av följande alternativ:

   * Land
   * Läge
   * Ort
   * Postnummer
   * Latitud
   * Longitud
   * DMA
   * Mobiloperatör

   En besökares IP-adress skickas med en mbox-begäran, en gång per besök (session), för att matcha parametrar för geomål för den besökaren.

   För mobiloperatör [!DNL Target] används IP-adressregistreringsdata (som äger IP-adressblocket) för att avgöra vilket mobilföretag som är lämpligt med MCC ( [Mobile Country Codes) och MNC (Mobile Network Codes)](https://www.mcc-mnc.com).

1. Ange en operator och lämpligt värde.
1. (Valfritt) Klicka **[!UICONTROL Add Rule]** och ange ytterligare regler för publiken.
1. Klicka på **[!UICONTROL Save]**.

I följande bild visas en målgrupp som riktar sig till användare som har åtkomst till aktiviteten från en latitud som är större än 44 grader och en longitud som är mindre än 22 grader.

![](assets/target_geo.png)

## Noggrannhet {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

Exaktheten i målinriktningen beror på flera faktorer. WiFi-anslutningar är exaktare än mobilnät. När besökaren använder en mobildataanslutning kan geo-lookup-noggrannheten påverkas av plats, providerns datarelation med [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester)och andra faktorer. Celltornbaserade nätverksanslutningar kan vara mindre noggranna än kabelanslutningar och WiFi-anslutningar. En besökares IP-adress kan mappas till hans eller hennes Internet-leverantörsplats, vilket kanske inte är samma som besökarens faktiska plats. Vissa problem med geolokalisering för mobiler kan lösas med [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

I följande tabell visas precisionen i IP-baserad geografisk information från [DigitalEnvoy](https://www.digitalelement.com/solutions/) för kabelanslutna eller WiFi-internetanslutningar. DigitalEnvoy ger branschens mest korrekta data. Den globala precisionen är mer än 99,9 procent på landsnivå och är upp till 97 procent korrekt på stadsnivå. Noggrannhetsinformation gäller inte för celltornbaserade nätverk.

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

Du kan nu använda `profile.geolocation` värden direkt som token i erbjudanden, plugin-program och så vidare.

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

De flesta mobilanvändare får tillgång till innehåll via WiFi, vilket innebär att målets IP-baserade geoanpassning är lika korrekt som på en stationär dator. Celltornbaserade anslutningar kan vara mindre exakta eftersom besökarens IP-adress baseras på tornet där signalen hämtas. Vissa problem med geolokalisering för mobiler kan lösas med [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

**Hur hanterar geo besökare från AOL?**

På grund av det sätt på vilket AOL proxies sin trafik kan vi bara rikta in oss på dem på landsnivå. En kampanj som riktar sig till Frankrike kommer till exempel att rikta sig till AOL-användare i Frankrike. Men en kampanj som riktar sig till Paris har inte lyckats rikta sig till AOL-användare i Paris. Om du avser att särskilt rikta in dig på AOL-användare kan du ställa in regionfältet på &quot;aol&quot;. Man kan faktiskt rikta in sig på AOL-användare genom att ange två målinriktningsvillkor: land matchar exakt&quot;USA&quot; och region matchar&quot;aol&quot;.

**Vilken platsgranularitet ger målinriktning?**

* Land - globalt
* Stat/provins/region - global
* Ort - global
* Postnummer - USA, Tyskland, Kanada
* DMA/ITV (UK) - USA, Storbritannien
* Mobiloperatör - globalt

**Hur testar jag mina aktiviteter som om jag är en användare som kommer från en annan plats?**

Du kan åsidosätta din IP-adress med en IP-adress från en annan plats och använda `mboxOverride.browserIp url` parametern. Så om ert företag är i Storbritannien, men er globala kampanj riktar sig till besökare i Aukland i Nya Zeeland, kan du använda den här typen av URL under förutsättning att det `60.234.0.39` är en IP-adress i Auckland:

`https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

Du måste rensa dina cookies innan du gör det här.

>[!NOTE]
>
>`mboxOverride.browserIp` stöds endast i at.js 1.*jx* . Den här funktionen stöds inte i at.js 2.*x*.

**Hur är områden, som Puerto Rico och Hong Kong, mappade till strukturen för geografisk anpassning?**

Puerto Rico, Hong Kong och andra territorier behandlas som separata&quot;Country&quot;-värden.

**Fångar[!DNL Target](och lagrar) information som Zip-koder när aktiviteten är inriktad på geolokalisering med målgruppsfunktioner?**

Nej, [!DNL Target] använder endast geo-data under hela sessionen, och data ignoreras.

## Utbildningsvideo: Skapa märket för ![självstudiekurser för publiker](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
