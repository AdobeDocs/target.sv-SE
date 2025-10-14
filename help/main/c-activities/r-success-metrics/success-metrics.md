---
keywords: Mått på konvertering;lyckad;konverteringsmått;sidpoängsmått;mått för sidvisningar;intäktsmått;tid på webbplatsmått;uppskattat värde;avancerade inställningar;mått på framgångar;beroende;ökning och behåll användaren i aktiviteten;Öka antal, frigör användare och Tillåt återinträde;ökning, Frigör användare och fält från återinträde
description: Lär dig mer om framgångsmått som hjälper dig att avgöra hur framgångsrik en aktivitet är. Exempel på framgångsmått är konvertering, intäkter, sidvyer, anpassad poängsättning och tid på webbplatsen.
title: Vad är Success Metrics?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: a34d40bef584bfa941731df718cb402c658f5d28
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 0%

---

# [!UICONTROL Success metrics]

Framgångsmått i [!DNL Adobe Target] är nyckelindikatorer som hjälper dig att mäta hur dina aktiviteter fungerar. Dessa mätvärden fångar upp viktiga affärsresultat som konverteringar, intäkter per besökare och kundengagemang, så att ni kan utvärdera effekten av specifika upplevelser eller erbjudanden.

Du kan till exempel spåra om en ny kampanj ökar intäkterna per besökare eller leder till fler artiklar i kundvagnen. Framgångssiffror hjälper också till att identifiera problem i användarflöden som registrering, utcheckning eller inköpsprocesser, samtidigt som de ger insikter i besökarnas övergripande beteende.

## Ökning

I [!DNL Target] är framgångsmått förkonfigurerade med rekommenderade inställningar för att säkerställa korrekt rapportering och effektiv spårning.

Som standard använder konverteringshändelser inställningen **[!UICONTROL Increment count & keep user in activity].** Den här inställningen innebär att varje besökare bara räknas som en konvertering en gång. Inga upprepade konverteringar räknas. Dessa besökare fortsätter att se aktivitetsinnehållet under hela sessionen.

För intäktsmått med samma inställning loggar endast den första ordern från en besökare orderdetaljer. Efterföljande order ökar antalet konverteringar, men de bidrar inte till intäktsbaserade mått som [!UICONTROL Revenue per Visitor (RPV)], [!UICONTROL Average Order Value (AOV)] eller [!DNL Total Sales]. Dessa ytterligare order exkluderas också från rapporten [!UICONTROL Order Details].

>[!NOTE]
>
>För aktiviteter som använder [Analytics som rapportkälla](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) använder målmåttet alltid inställningarna [!UICONTROL Increment Count & Keep User in Activity] och [!UICONTROL On Every Impression]. Dessa inställningar är *inte* konfigurerbara.

Följande framgångsmått kan konfigureras i avsnittet [!UICONTROL Reporting Settings] i [!UICONTROL Activity Settings page], under steget [!UICONTROL Goals & Settings]:

| Resultatmått | Mätningsmetod | Definition |
|--- |--- |--- |
| [!UICONTROL Conversion] | Konverteringsbaserad | Konverteringen är när en besökare utför en åtgärd på din webbplats som du har definierat, till exempel <ul><li>Visad sida</li><li>Visad mbox</li><li>Klicka på ett element</li></ul>En konvertering kan räknas en gång per besökare eller varje gång en besökare slutför en konvertering. |
| [!UICONTROL Revenue] | Konverteringsbaserad | Intäkter från besöket. Du kan bara välja ett intäktsmått:<ul><li>Visad mbox</li></ul>Mer information om ändringar i det uppdaterade [!DNL Target]-användargränssnittet, som det gäller resultatvärden, finns i [Uppdaterade  [!DNL Target] gränssnittsändringar](#changes) nedan. |
| [!UICONTROL Engagement] | Engagement-based | Engagemang som genererats av besöket. Du kan välja mellan följande interaktionsmått:<UL><li>Sidvyer: Varje unikt besök räknas som en konvertering.</li><li>[!UICONTROL Custom Scoring]: Sammanställd poäng baserad på det värde som tilldelats till sidor som besökts på webbplatsen, från den punkt besökaren först ser aktivitetens första [!DNL Target] -visningsbegäran.</li>[!DNL Time on Site]: Den tid som har tillbringats i besöket (i sekunder) från den punkt där besökaren ser aktivitetens första [!DNL Target] -begäran till den sista sidans inläsning med en begäran i sessionen.</UL> |

För interaktionsbaserade mätvärden (till skillnad från för konverteringsbaserade och intäktsbaserade mätvärden) måste besökarna omkvalificera sig för aktiviteten vid varje besök för att öka antalet för den sessionen. Det associerade måttet börjar öka efter omkvalificering och stannar i slutet av varje besökares session. En session avslutas efter 30 minuters inaktivitet. Därför ser du inga resultat direkt under testningen, men alla resultat från den sessionen är tillgängliga inom några minuter efter att sessionen avslutats.

## Anpassade framgångsmått

Ni kan också skapa anpassade framgångsmått.

När du har valt framgångsmått väljer du den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett [!UICONTROL Conversion]-mått, ange att det ska räknas en gång per besökare och ange om det ska lyckas när en besökare visar en viss sida (eller en uppsättning sidor), visar en viss [!DNL Target]-begäran eller klickar på en specifik länk.

Om det här alternativet är aktiverat tillhandahåller fältet [!UICONTROL Estimated Value of one conversion] (inte tillgängligt för [!UICONTROL Page Score]-måtten) ett värde för ditt mål, men inte för andra mätvärden. Detta värde gör att [!DNL Target] kan beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] och [!UICONTROL Orders]) använder uppskattningen [!UICONTROL Revenue per Visitor]. Datatypen är valuta. Mer information finns i [Beräknar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

De framgångsmått du väljer för din aktivitet finns i rapportinställningarna när du visar en rapport för aktiviteten.

Vissa mätvärden, som [!UICONTROL Custom Scoring] och [!UICONTROL Revenue Per Visitor], kräver en anpassad implementering som skickar information, som ordersummor och order-ID:n.

## Avancerade inställningar {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Använd de avancerade inställningarna för att hantera hur du mäter framgång. Du kan lägga till beroenden, välja om du vill behålla användaren i aktiviteten eller ta bort dem och om mätvärdet ska räknas en gång per deltagare eller vid varje intryck.

Om du vill komma åt alternativen för [!UICONTROL Advanced Settings] klickar du på ikonen **[!UICONTROL More Actions]** ( ![Fler åtgärder-ikon](/help/main/assets/icons/MoreSmallListVert.svg) ) och sedan på **[!UICONTROL Advanced Settings]**.

![Menyn Avancerade inställningar](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

Mer information om [!UICONTROL Advanced Settings]-alternativen ([!UICONTROL What will happen after a user encounters this goal] och [!UICONTROL How will the count be incremented]) finns i [Vad händer när en användare påträffar det här målmåttet &#x200B;](#what-happens)?

>[!NOTE]
>
>Om du använder [!DNL Adobe Analytics] som rapportkälla hanteras inställningarna av servern [!DNL Analytics]. Alternativet [!UICONTROL Advanced Settings] är inte tillgängligt. Mer information finns i [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Lägg till beroende

Du kan använda de avancerade inställningarna för att skapa beroende framgångsmått och bara öka ett mätvärde om en besökare når ett annat mätvärde först.

En testkonvertering kan till exempel bara vara giltig om en besökare klickar på erbjudandet eller når en viss sida innan konverteringen.

Beroendefunktionen stöds *inte* för följande:

* [!UICONTROL Recommendations] aktiviteter. Den här funktionen stöds för alla andra aktivitetstyper.
* Om du använder [Analytics som rapportkälla](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Mättypen Visad sida.
* Mättypen&quot;Click an an Element&quot; för VEC-aktiviteter (Visual Experience Composer).

Beroende framgångsmått konverteras inte i följande fall:

* Om du skapar ett cirkelberoende där metrisk1 är beroende av metrisk2 och metrisk2 är beroende av metrisk1, kan inget av dem konverteras.
* [!UICONTROL Automated Personalization] aktiviteter frigör användare och startar om aktiviteten när konverteringsmått nås, så att alla mått som är beroende av konverteringsmåttet inte konverteras.

### Vad händer efter att en användare har påträffat det här målmåttet? {#what-happens}

Använd de avancerade inställningarna för att avgöra vad som händer när en användare når målmåttet. I följande tabell visas de tillgängliga alternativen:

| Efter att en användare påträffar detta mål | Alternativ |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Ange hur antalet ska ökas:<ul><li>En gång per deltagare (standard)</li><li>Vid varje intryck, exklusive siduppdatering</li><li>På varje intryck</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Välj den upplevelse som besökaren ser om de återupptar aktiviteten:<ul><li>Samma upplevelse (standard)</li><li>Slumpmässig erfarenhet</li><li>Osynlig upplevelse</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Bestäm vad användaren ser i stället för aktivitetsinnehållet:<ul><li>Samma upplevelse, utan spårning (standard)</li><li>Standardinnehåll eller annat aktivitetsinnehåll</li></ul> |

>[!NOTE]
>
>Om du konfigurerar ett mätvärde till något av [!UICONTROL Increment Count]-alternativen (som nämns ovan) ökas mätvärdet korrekt en gång per deltagare endast på besökarnivå. Antalet mätvärden ökar en gång per besök för varje ny session på besöksnivå.

### Hur ökas antalet:

Välj önskat beteende:

* En gång per deltagare
* Vid varje intryck (exklusive uppdatering av sidor)
* På varje intryck

## Kända fel

* Framgångsmått med det avancerade alternativet &quot;Hur kommer antalet att ökas&quot; inställt på &quot;varje intryck&quot; eller &quot;varje intryck (exklusive uppdateringar)&quot; kan inte användas som ett framgångsmått som ett annat mätvärde är beroende av.

  När ett framgångsmått är inställt på ökning för varje intryck, räknar [!DNL Target] besökaren igen varje gång besökaren besöker det här framgångsmåttet. [!DNL Target] återställer sedan måttet för framgång till 0 så att det kan räkna med nästa intryck. Om ett annat mått kräver att det här måttet har setts först, kommer [!DNL Target] alltså aldrig ihåg att användaren har sett det första måttet.

## Uppdaterade [!DNL Target] gränssnittsändringar {#changes}

[[!DNL Target Standard/Premium] 25.2.1-utgåvan](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2), som startades den 17 februari 2015, introducerade uppdaterade användargränssnitt för [!DNL Target] och [!UICONTROL Visual Experience Composer] (VEC). I det här avsnittet beskrivs de viktigaste skillnaderna mellan det gamla och uppdaterade användargränssnittet, särskilt eftersom de gäller att konfigurera och hantera framgångsmått.

### Gränssnittsändringar relaterade till [!UICONTROL Revenue] framgångsmått

Listrutan [!DNL Target] har tagits bort i det uppdaterade [!UICONTROL Default View for Reporting]-gränssnittet. Det här fältet var överflödigt eftersom det tidigare sparade standardrapportvyn under [!DNL Overview] > [!UICONTROL Reports] i det gamla användargränssnittet.

Med det uppdaterade användargränssnittet är standardrapportmåttet nu alltid inställt på [!UICONTROL Revenue per Visitor (RPV)]. Du kan fortfarande anpassa vyn i avsnittet [!UICONTROL Reports] för att visa mätvärden som är mest relevanta för din analys.

Den här ändringen påverkar inte leveransstatistik. Den här ändringen påverkar bara det standardfilter som visas i rapportvyn. Eftersom RPV är det vanligaste måttet bland kunderna har detta standardvärde valts för att effektivisera rapporteringsarbetsflödena. Du kan växla till andra mått när som helst i avsnittet [!UICONTROL Reports].