---
keywords: Mått på konvertering;lyckad;konverteringsmått;sidpoängsmått;mått för sidvisningar;intäktsmått;tid på webbplatsmått;uppskattat värde;avancerade inställningar;mått på framgångar;beroende;ökning och behåll användaren i aktivitet;Öka antal, frigör användare och Tillåt återinträde;ökning, Frigör användare och fält från återinträde
description: Läs om framgångsstatistik i Adobe [!DNL Target] som hjälper dig att avgöra hur framgångsrik en aktivitet är. Exempel på framgångsmått är konvertering, intäkter, sidvyer, anpassad poängsättning och tid på webbplatsen.
title: Vad är Success Metrics?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 0%

---

# Framgångsmått

I [!DNL Adobe Target] framgångsmått är parametrar som används för att mäta en aktivitets framgång. Framgångsstatistik innehåller viktiga affärsåtgärder som gör det möjligt att avgöra hur framgångsrik en viss upplevelse eller ett visst erbjudande är i en [!DNL Target] aktivitet.

Du kan till exempel bestämma om ett nytt erbjudande ökar intäkterna per besökare eller lägger till en artikel i en kundvagn. Framgångsstatistik kan vara användbar för att upptäcka problem med registrering, beställning eller inköpskanaler, men också helt enkelt med besökarens eller kundens engagemang.

## Översikt

I [!DNL Target], är framgångsmått förkonfigurerade med de optimala alternativen för både rapportering och spårning.

Som standard är konverteringshändelser inställda på &quot;[!UICONTROL Increment count & keep user in activity].&quot; Konverteringar räknas bara en gång, inga upprepade konverteringar räknas och besökaren ser alltid aktivitetsinnehållet.

Intäktsmått som är inställda på[!UICONTROL Increment count & keep user in activity]&quot; loggordningsinformation endast för den första ordern som gjorts av samma besökare. Alla efterföljande order ökar antalet konverteringar, men lägger inte till intäkter till RPV/AOV/Sales, och inkluderas inte i [!UICONTROL Order Details] rapport.

>[!NOTE]
>
>För aktiviteter som använder [Analyser som rapportkälla](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) målmåttet kommer alltid att använda[!UICONTROL Increment Count & Keep User in Activity]&quot; och &quot;[!UICONTROL On Every Impression]&quot;. Det här är *not* kan konfigureras.

Följande framgångsmått finns:

| Resultatmått | Mätningsmetod | Definition |
|--- |--- |--- |
| Konvertering | Konverteringsbaserad | Konverteringen är när en besökare utför en åtgärd på platsen som du har definierat, till exempel <ul><li>Klicka på en knapp</li><li>Visad sida</li><li>Slutförde en undersökning</li><li>Köpte</li></ul>En konvertering kan räknas en gång per besökare eller varje gång en besökare slutför en konvertering. |
| Intäkter | Konverteringsbaserad | Intäkter från besöket. Du kan välja mellan följande intäktsmått:<ul><li>Intäkter per besökare (RPV)</li><li>Genomsnittligt ordervärde (AOV)</li><li>Total försäljning</li><li>Beställningar</li></ul> |
| Sidvyer | Engagement-based | Varje unikt besök räknas som en konvertering. |
| Anpassad poängsättning | Engagement-based | Sammanställd poäng baserad på det värde som tilldelats de sidor som besöks på webbplatsen, från den punkt där besökaren först ser aktivitetens första visning [!DNL Target] begäran. |
| Tid på plats | Engagement-based | Tid som tillbringats i besöket (i sekunder) från den punkt besökaren ser aktivitetens första skärm [!DNL Target] begäran till inläsningen av den sista sidan med en begäran i sessionen. |

För interaktionsbaserade mätvärden (till skillnad från för konverteringsbaserade och intäktsbaserade mätvärden) måste besökarna omkvalificera sig för aktiviteten vid varje besök för att öka antalet för den sessionen. Det associerade måttet börjar öka efter omkvalificering och stannar i slutet av varje besökares session. En session avslutas efter 30 minuters inaktivitet. Därför kommer du inte att se resultat direkt under testningen; Alla resultat från den sessionen är dock tillgängliga inom några minuter efter att sessionen avslutats.

## Anpassade framgångsmått

Ni kan också skapa anpassade framgångsmått.

När du har valt framgångsmått väljer du den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel en [!UICONTROL Conversion] mätvärden, ange att den ska räknas en gång per besökare och ange om den ska lyckas när en besökare visar en viss sida (eller en uppsättning sidor), visar en viss [!DNL Target] begär eller klickar på en specifik länk.

Om den är aktiverad visas [!UICONTROL Estimated Value of one conversion] fält (ej tillgängligt för [!UICONTROL Page Score] mätvärden) ger ett värde för ditt mål, men inte för andra mätvärden. Detta värde aktiverar [!DNL Target] att beräkna en uppskattad ökning av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales]och [!UICONTROL Orders]), uppskattningens användning [!UICONTROL Revenue per Visitor]. Datatypen är valuta. Se [Uppskattar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) för mer information.

De framgångsmått du väljer för din aktivitet finns i rapportinställningarna när du visar en rapport för aktiviteten.

Vissa mått, som [!UICONTROL Custom Scoring] och [!UICONTROL Revenue Per Visitor], kräver en anpassad implementering som skickar in information som ordersummor och order-ID:n.

## Avancerade inställningar {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Använd de avancerade inställningarna för att hantera hur du mäter framgång. Du kan lägga till beroenden, välja om du vill behålla användaren i aktiviteten eller ta bort dem och om mätvärdet ska räknas en gång per deltagare eller vid varje intryck.

Så här öppnar du [!UICONTROL Advanced Settings] alternativ, klicka på **[!UICONTROL vertical ellipses]** > **[!UICONTROL Advanced Settings]**.

![Menyn Avancerade inställningar](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Om du använder [!DNL Adobe Analytics] som rapportkälla hanteras inställningarna av [!DNL Analytics] server. The [!UICONTROL Advanced Settings] kommer inte att vara tillgängligt. Mer information finns i [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Lägg till beroende

Du kan använda de avancerade inställningarna för att skapa beroende framgångsmått och bara öka ett mätvärde om en besökare når ett annat mätvärde först.

![Lägg till beroende](/help/main/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

En testkonvertering kan till exempel bara vara giltig om en besökare klickar på erbjudandet eller når en viss sida innan konverteringen.

Beroendefunktionen är *not* stöds för följande:

* [!UICONTROL Recommendations] verksamhet. Den här funktionen stöds för alla andra aktivitetstyper.
* Om du använder [Analyser som rapportkälla](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Mättypen Visad sida.
* Mättypen&quot;Click an an Element&quot; för VEC-aktiviteter (Visual Experience Composer).

Beroende framgångsmått konverteras inte i följande fall:

* Om du skapar ett cirkelberoende där metrisk1 är beroende av metrisk2 och metrisk2 är beroende av metrisk1, kan inget av dem konverteras.
* Automated Personalization-aktiviteter frigör användare och startar om aktiviteten när konverteringsmåtten nås, så att inga mått som är beroende av konverteringsmåttet konverteras.

### Vad händer efter att en användare har påträffat det här målmåttet?

Använd de avancerade inställningarna för att avgöra vad som händer när en användare når målmåttet. I följande tabell visas de tillgängliga alternativen:

| När en användare påträffar detta mål | Alternativ |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Ange hur antalet ska ökas:<ul><li>En gång per deltagare (standard)</li><li>Vid varje intryck, exklusive siduppdatering</li><li>På varje intryck</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Välj den upplevelse besökaren ser om de återupptar aktiviteten:<ul><li>Samma upplevelse (standard)</li><li>Slumpmässig upplevelse</li><li>Osynlig upplevelse</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Bestäm vad användaren ser i stället för aktivitetsinnehållet:<ul><li>Samma upplevelse, utan spårning (standard)</li><li>Standardinnehåll eller annat aktivitetsinnehåll</li></ul> |

>[!NOTE]
>
>Om du konfigurerar ett mätvärde till något av [!UICONTROL Increment Count] (se ovan) ökar antalet mätvärden korrekt en gång per deltagare endast på besökarnivå. Antalet mätvärden ökar en gång per besök för varje ny session på besöksnivå.

### Hur ska antalet ökas:

Välj önskat beteende:

* En gång per deltagare
* Vid varje intryck (exklusive uppdatering av sidor)
* På varje intryck

## Utbildningsvideo: Aktivitetsmått

I den här videon visas hur du använder aktivitetsmått.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
