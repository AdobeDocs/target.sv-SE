---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics
description: I Adobe Target är framgångsmått förkonfigurerade för både rapportering och spårning.
title: Framgångsstatistik i Adobe Target
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: c7664f9674234565a3657f453541095811fa5aa6
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 0%

---


# Framgångsmått{#success-metrics}

I Adobe Target är framgångsmått förkonfigurerade för både rapportering och spårning.

Framgångsmått är parametrar som används för att mäta en aktivitets framgång. Framgångsstatistik innehåller viktiga affärsåtgärder som gör det möjligt att avgöra hur framgångsrik en viss upplevelse eller ett visst erbjudande är i en Target-aktivitet. Du kan till exempel bestämma om ett nytt erbjudande ökar intäkterna per besökare eller lägger till en artikel i en kundvagn. Framgångsstatistik kan vara användbar för att upptäcka problem med registrering, beställning eller inköpskanaler, men också helt enkelt med besökarens eller kundens engagemang.

I linje med målet att förenkla testskapandet tar programmet hand om en del av konfigurationen som gjordes manuellt i [!DNL Target Standard] [!DNL Target Classic]. Exempel: framgångsmått är förkonfigurerade med de optimala alternativen.

Som standard är konverteringshändelser inställda på&quot;Antal en gång och behåll deltagaren i aktiviteten&quot; i [!DNL Target Standard]. Konverteringar räknas bara en gång, inga upprepade konverteringar räknas och besökaren ser alltid testinnehållet.

Inkomstmått som är inställda på Ökningsantal och behåller användaren i aktiviteten, loggordningsinformation endast för den första ordern som gjorts av samma besökare. Alla efterföljande order ökar antalet konverteringar, men lägger inte till intäkter till RPV/AOV/Sales och inkluderas inte i rapporten Orderdetaljer.

>[!NOTE]
>
>Standardbeteendet för aktiviteter där [Analytics används som rapportkälla](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) är&quot;Ökningsantal och behåll användaren i aktiviteten&quot; med&quot;En gång per deltagare&quot;.

Följande framgångsmått finns:

| Resultatmått | Mätningsmetod | Definition |
|--- |--- |--- |
| Konvertering | Konverteringsbaserad | Konvertering är när en besökare utför en åtgärd på webbplatsen som du har definierat (klickade på en knapp, visade en sida, slutförde en undersökning eller gjorde ett köp). En konvertering kan antingen räknas en gång per besökare eller varje gång en besökare slutför en konvertering. |
| Intäkter | Konverteringsbaserad | Intäkter från besöket. Du kan välja mellan följande intäktsmått:<ul><li>Intäkter per besökare (RPV)</li><li>Genomsnittligt ordervärde (AOV)</li><li>Total försäljning</li></ul> |
| Sidvyer | Engagement-based | Varje unikt besök räknas som en konvertering. |
| Tid på plats | Engagement-based | Den tid som tillbringats i besöket (i sekunder) från den punkt där besökaren ser aktivitetens första Target-begäran till den sista sidans inläsning med en begäran i sessionen. |
| Anpassad poängsättning | Engagement-based | Sammanställd poäng baserad på det värde som tilldelats de sidor som besöks på webbplatsen, från den punkt där besökaren först ser aktivitetens första [!DNL Target] visningsbegäran. |

För interaktionsbaserade mätvärden (till skillnad från för konverteringsbaserade och intäktsbaserade mätvärden) måste besökarna omkvalificera sig för aktiviteten vid varje besök för att öka antalet för den sessionen. Det associerade måttet börjar öka efter omkvalificering och stannar i slutet av varje besökares session. En session avslutas efter 30 minuters inaktivitet. Därför kommer du inte att se resultat direkt under testningen, men alla resultat från den sessionen är tillgängliga inom några minuter efter att sessionen avslutats.

Ni kan också skapa anpassade framgångsmått.

När du har valt framgångsmått väljer du den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett konverteringsmått, ange att det ska räknas en gång per besökare och ange om resultatet ska uppnås när en besökare visar en viss sida (eller en uppsättning sidor), visar en viss [!DNL Target] begäran eller klickar på en viss länk.

Om det här alternativet är aktiverat ger det beräknade värdet för ett konverteringsfält (inte tillgängligt för sidpoängsmått) ett värde för ditt mål, men inte för andra mått. Detta värde gör det möjligt [!DNL Target] att beräkna en uppskattad ökning av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. För alla intäktsmått (Intäkt per besökare, Genomsnittligt ordervärde, Total försäljning och Beställningar) används Intäkt per besökare i uppskattningen. Datatypen är valuta. Mer information finns i [Beräkna Lyft i intäkter](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) .

De framgångsmått du väljer för din aktivitet finns i rapportinställningarna när du visar en rapport för aktiviteten.

Vissa mätvärden, som Custom Scoring och Revenue Per Visitor, kräver en anpassad implementering som skickar in information som ordersummor och order-ID:n.

## Avancerade inställningar {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Använd de avancerade inställningarna för att hantera hur du mäter framgång. Du kan bland annat räkna mätvärdena per intryck eller en gång per besökare och välja om du vill behålla användaren i aktiviteten eller ta bort dem.

>[!NOTE]
>
>Om du använder [!DNL Adobe Analytics] som rapportkälla hanteras inställningarna av [!DNL Analytics] servern. Alternativet för avancerade inställningar är inte tillgängligt.

![Listrutan Avancerade inställningar](/help/c-activities/r-success-metrics/assets/Menu_AdvancedSettings.png)

Du kan också använda de avancerade inställningarna för att skapa beroende framgångsmått, som bara ökas med ett mätvärde om besökaren når ett annat mätvärde först.

![Lägg till beroende](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

En testkonvertering kan till exempel bara vara giltig om en besökare klickar på erbjudandet eller når en viss sida innan konverteringen.

Beroende framgångsmått stöds i A/B-testning, automatiserad personalisering, Experience Targeting och Multivariate-testning. Rekommendationsaktiviteter stöder för närvarande inte beroende framgångsmått.

>[!NOTE]
>
>Beroende framgångsmått konverteras inte i följande fall:

* Om du skapar ett cirkelberoende där metrisk1 är beroende av metrisk2 och metrisk2 är beroende av metrisk1, kan inget av dem konverteras.
* Automatiserade personaliseringsaktiviteter frigör användare och startar om aktiviteten när konverteringsmåtten nås, så att inga mätvärden som är beroende av konverteringsmåttet konverteras.

Använd de avancerade inställningarna för att avgöra vad som händer när en användare når målmåttet. I följande tabell visas de tillgängliga alternativen.

| När en användare påträffar detta mål | Alternativ |
|--- |--- |
| Öka antal och behåll användaren i aktiviteten | Ange hur antalet ska ökas:<ul><li>En gång per deltagare (standard)</li><li>Vid varje intryck, exklusive siduppdatering</li><li>På varje intryck</li></ul> |
| Ökning av antal, släpp användare och tillåt återinträde | Välj den upplevelse besökaren ser om de återupptar aktiviteten:<ul><li>Samma upplevelse (standard)</li><li>Slumpmässig upplevelse</li><li>Osynlig upplevelse</li></ul> |
| Ökning av antalet, släpp användare och hindra användaren från att registrera sig igen | Bestäm vad användaren ser i stället för aktivitetsinnehållet:<ul><li>Samma upplevelse, utan spårning (standard)</li><li>Standardinnehåll eller annat aktivitetsinnehåll</li></ul> |

## Utbildningsvideo: Aktivitetsmått

I den här videon visas hur du använder aktivitetsmått.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)