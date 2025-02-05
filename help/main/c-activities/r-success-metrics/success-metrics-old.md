---
keywords: Mått på konvertering;lyckad;konverteringsmått;sidpoängsmått;mått för sidvisningar;intäktsmått;tid på webbplatsmått;uppskattat värde;avancerade inställningar;mått på framgångar;beroende;ökning och behåll användaren i aktiviteten;Öka antal, frigör användare och Tillåt återinträde;ökning, Frigör användare och fält från återinträde
description: Lär dig mer om framgångsmått i Adobe [!DNL Target] som hjälper dig att avgöra om en aktivitet lyckades. Exempel på framgångsmått är konvertering, intäkter, sidvyer, anpassad poängsättning och tid på webbplatsen.
title: Vad är Success Metrics?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 0%

---

# Framgångsmått

I [!DNL Adobe Target]-framgångsmått används parametrar för att mäta en aktivitets framgång. Framgångsstatistik innehåller viktiga affärsåtgärder som gör att du kan avgöra om en viss upplevelse eller ett visst erbjudande i en [!DNL Target]-aktivitet lyckades.

Du kan till exempel bestämma om ett nytt erbjudande ökar intäkterna per besökare eller lägger till en artikel i en kundvagn. Framgångsstatistik kan vara användbar för att upptäcka problem med registrering, beställning eller inköpskanaler, men också helt enkelt med besökarens eller kundens engagemang.

## Ökning

I [!DNL Target] är framgångsmått förkonfigurerade med de optimala alternativen för både rapportering och spårning.

Som standard är konverteringshändelser inställda på [!UICONTROL Increment count & keep user in activity]. Konverteringar räknas bara en gång, inga upprepade konverteringar räknas och besökaren ser alltid aktivitetsinnehållet.

Intäktsmått som är inställda på [!UICONTROL Increment count & keep user in activity], loggordningsinformation endast för den första ordern som görs av samma besökare. Alla efterföljande order ökar antalet konverteringar, men lägger inte till intäkter till RPV/AOV/Sales, och inkluderas inte i [!UICONTROL Order Details]-rapporten.

>[!NOTE]
>
>För aktiviteter som använder [Analytics som rapportkälla](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) använder målmåttet alltid inställningarna [!UICONTROL Increment Count & Keep User in Activity] och [!UICONTROL On Every Impression]. Detta är *inte* konfigurerbart.

Följande framgångsmått finns:

| Resultatmått | Mätningsmetod | Definition |
|--- |--- |--- |
| Konvertering | Konverteringsbaserad | Konverteringen är när en besökare utför en åtgärd på din webbplats som du har definierat, till exempel <ul><li>Klicka på en knapp</li><li>Visad sida</li><li>Slutförde en undersökning</li><li>Köpte</li></ul>En konvertering kan räknas en gång per besökare eller varje gång en besökare slutför en konvertering. |
| Intäkter | Konverteringsbaserad | Intäkter från besöket. Du kan välja mellan följande intäktsmått:<ul><li>Intäkter per besökare</li><li>Genomsnittligt ordervärde (AOV)</li><li>Total försäljning</li><li>Beställningar</li></ul> |
| Sidvyer | Engagement-based | Varje unikt besök räknas som en konvertering. |
| Anpassad poängsättning | Engagement-based | Sammanställd poäng baserad på det värde som tilldelats sidor som besökts på webbplatsen, från den punkt besökaren först ser aktivitetens första visningsbegäran [!DNL Target]. |
| Tid på plats | Engagement-based | Tid som har tillbringats i besöket (i sekunder) från den punkt där besökaren ser aktivitetens första visningsbegäran [!DNL Target] till inläsningen av den sista sidan med en begäran i sessionen. |

För interaktionsbaserade mätvärden (till skillnad från för konverteringsbaserade och intäktsbaserade mätvärden) måste besökarna omkvalificera sig för aktiviteten vid varje besök för att öka antalet för den sessionen. Det associerade måttet börjar öka efter omkvalificering och stannar i slutet av varje besökares session. En session avslutas efter 30 minuters inaktivitet. Därför kommer du inte att se resultat direkt under testningen, men alla resultat från den sessionen är tillgängliga inom några minuter efter att sessionen avslutats.

## Anpassade framgångsmått

Ni kan också skapa anpassade framgångsmått.

När du har valt framgångsmått väljer du den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett [!UICONTROL Conversion]-mått, ange att det ska räknas en gång per besökare och ange om det ska lyckas när en besökare visar en viss sida (eller en uppsättning sidor), visar en viss [!DNL Target]-begäran eller klickar på en specifik länk.

Om det här alternativet är aktiverat tillhandahåller fältet [!UICONTROL Estimated Value of one conversion] (inte tillgängligt för [!UICONTROL Page Score]-måtten) ett värde för ditt mål, men inte för andra mätvärden. Detta värde gör att [!DNL Target] kan beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] och [!UICONTROL Orders]) använder uppskattningen [!UICONTROL Revenue per Visitor]. Datatypen är valuta. Mer information finns i [Beräknar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

De framgångsmått du väljer för din aktivitet finns i rapportinställningarna när du visar en rapport för aktiviteten.

Vissa mätvärden, som [!UICONTROL Custom Scoring] och [!UICONTROL Revenue Per Visitor], kräver en anpassad implementering som skickar in information som ordersummor och order-ID:n.

## Avancerade inställningar {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Använd de avancerade inställningarna för att hantera hur du mäter framgång. Du kan lägga till beroenden, välja om du vill behålla användaren i aktiviteten eller ta bort dem och om mätvärdet ska räknas en gång per deltagare eller vid varje intryck.

Klicka på **[!UICONTROL vertical ellipses]** > **[!UICONTROL Advanced Settings]** om du vill komma åt alternativen för [!UICONTROL Advanced Settings].

![Menyn Avancerade inställningar](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Om du använder [!DNL Adobe Analytics] som rapportkälla hanteras inställningarna av servern [!DNL Analytics]. Alternativet [!UICONTROL Advanced Settings] kommer inte att vara tillgängligt. Mer information finns i [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Lägg till beroende

Du kan använda de avancerade inställningarna för att skapa beroende framgångsmått och bara öka ett mätvärde om en besökare når ett annat mätvärde först.

![Lägg till beroende](/help/main/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

En testkonvertering kan till exempel bara vara giltig om en besökare klickar på erbjudandet eller når en viss sida innan konverteringen.

Beroendefunktionen stöds *inte* för följande:

* [!UICONTROL Recommendations] aktiviteter. Den här funktionen stöds för alla andra aktivitetstyper.
* Om du använder [Analytics som rapportkälla](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Mättypen Visad sida.
* Mättypen&quot;Click an an Element&quot; för VEC-aktiviteter (Visual Experience Composer).

Beroende framgångsmått konverteras inte i följande fall:

* Om du skapar ett cirkelberoende där metrisk1 är beroende av metrisk2 och metrisk2 är beroende av metrisk1, kan inget av dem konverteras.
* Automated Personalization-aktiviteter frigör användare och startar om aktiviteten när konverteringsmåtten nås, så att inga mått som är beroende av konverteringsmåttet konverteras.

### Vad händer efter att en användare har påträffat det här målmåttet?

Använd de avancerade inställningarna för att avgöra vad som händer när en användare når målmåttet. I följande tabell visas de tillgängliga alternativen:

| Efter att en användare påträffar detta mål | Alternativ |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Ange hur antalet ska ökas:<ul><li>En gång per deltagare (standard)</li><li>Vid varje intryck, exklusive siduppdatering</li><li>På varje intryck</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Välj den upplevelse besökaren ser om de återupptar aktiviteten:<ul><li>Samma upplevelse (standard)</li><li>Slumpmässig erfarenhet</li><li>Osynlig upplevelse</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Bestäm vad användaren ser i stället för aktivitetsinnehållet:<ul><li>Samma upplevelse, utan spårning (standard)</li><li>Standardinnehåll eller annat aktivitetsinnehåll</li></ul> |

>[!NOTE]
>
>Om du konfigurerar ett mätvärde till något av [!UICONTROL Increment Count]-alternativen (som nämns ovan) ökas mätvärdet korrekt en gång per deltagare endast på besökarnivå. Antalet mätvärden ökar en gång per besök för varje ny session på besöksnivå.

### Hur kommer antalet att ökas:

Välj önskat beteende:

* En gång per deltagare
* Vid varje intryck (exklusive uppdatering av sidor)
* På varje intryck

## Kända fel

* Framgångsmått med det avancerade alternativet &quot;Hur kommer antalet att ökas&quot; inställt på &quot;varje intryck&quot; eller &quot;varje intryck (exklusive uppdateringar)&quot; kan inte användas som ett framgångsmått som ett annat mätvärde är beroende av.

När ett framgångsmått är inställt på ökning för varje intryck, räknar [!DNL Target] besökaren igen varje gång besökaren besöker det här framgångsmåttet. [!DNL Target] återställer sedan måttet för framgång till 0 så att det kan räkna med nästa intryck. Om ett annat mått kräver att det här måttet har setts först, kommer [!DNL Target] alltså aldrig ihåg att användaren har sett det första måttet.

## Utbildningsvideo: Aktivitetsstatistik

I den här videon visas hur du använder aktivitetsmått.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
