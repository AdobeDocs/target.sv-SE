---
keywords: felsökning;vanliga frågor;vanliga frågor;Vanliga frågor;Vanliga frågor;mål;målgrupper
description: Visa vanliga frågor och svar om målgruppsanpassning och målgrupper som används i Adobe [!DNL Target] verksamhet.
title: Var kan jag hitta frågor och svar om mål och målgrupper?
feature: Audiences
exl-id: f829bd4a-852a-4eb1-85d1-89e74c14b37e
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 1%

---

# Mål och målgrupper Frågor och svar

Lista med vanliga frågor och svar om målinriktning och målgrupper.

## Hur [!DNL Target] Vill du utvärdera URL:er för målinriktning? {#url}

Med Target utvärderas URL:er på olika sätt beroende på om du använder målgrupps-URL:er när du skapar en aktivitet eller om du använder URL-mål när du skapar en målgrupp.

Ta följande URL:

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### Målgrupps-URL

Om du vill använda målgrupps-URL när du skapar en aktivitet, klickar du på kugghjulsikonen på sidan Erfarenheter (steg ett av de guidade arbetsflödena i tre steg), klickar på Sidleverans och anger önskad URL.

![URL för sidleverans](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

Målgrupps-URL söker efter en exakt URL-matchning. Om URL:en matchar varandra kommer Target inte att överväga ytterligare logik. Om aktiviteten är inställd på att utlösas på `www.example.com`matchar URL:en för följande URL:er eftersom målgrupps-URL:er är frågeagnostiska:

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

Förutom målgruppsanpassning på URL:en kan du även ange specifika värden som kan finnas i frågan.

### URL-mål

Om du vill använda URL-adress när du skapar en målgrupp klickar du på Lägg till regel, klickar på Webbplatssidor, väljer ett alternativ i den första listrutan (Aktuell sida, Föregående sida eller Landningssida), väljer URL i den andra listrutan, anger en utvärderare och anger önskad URL.

![Webbplatssidor > Aktuell sida > URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

URL med målinriktning omvandlar URL:en till en uppsättning regler som ska utvärderas:

* URL-domän = `example.com`
* Sökväg = bana1/bana2/bana3
* queryStringParam1 = test123
* queryStringParam2 = test7

## När du skapar komplexa URL-strängar gör det [!DNL Target] Vill du utvärdera hela URL:en?

Om du använder samma parameternamn mer än en gång i en URL-sträng, kommer HTTP att undersöka det första parameternamnet och ignorera efterföljande parametrar med samma namn.

I följande URL-sträng:

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

den första instansen av `Category` parametern utvärderas och den andra `Category` parametern ignoreras.

Det bästa sättet är att ha flera värden kopplade till en enskild kategori, vilket visas nedan:

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## När ni bygger målgrupper, varför är fördefinierade målgrupper under [!DNL Target] Finns biblioteket under andra kategorier? {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

De färdiga målgrupperna i kategorin Målbibliotek är äldre målgrupper och finns i andra kategorier. Det gamla målbiblioteket > Ny besökare har till exempel en uppdaterad motsvarighet: Besöksprofil > Ny besökare.

Det bästa sättet är att använda de nyare målgrupperna eftersom de har bättre prestanda. Vissa kunder kanske använder äldre, förbyggda målgrupper, så de har inte tagits bort från Target-gränssnittet.

## Hur vet jag hur trafiken kommer att delas mellan olika målgrupper? {#section_067EEFB956E7465CBF77EC86834470AB}

Som standard fördelas trafiken jämnt mellan upplevelserna. Du kan dock ange procentvärden för varje upplevelse. I det här fallet genereras ett slumpmässigt tal och det talet används för att välja vilken upplevelse som ska visas. De resulterande procentsatserna kanske inte matchar de angivna målen exakt, men mer trafik innebär att upplevelserna ska delas närmare målmålen.

## Vilken upplevelse visas om en användare kvalificerar sig för en aktivitet som innehåller flera upplevelser med flera kvalificerade målgrupper? {#section_94A60B11212D48FD8AB0803C6C7E7253}

Användaren kvalificerar sig för den första upplevelsen/målgruppen som visas på aktivitetens [!UICONTROL Target] sida.

I följande exempel kvalificerar en användare från Kalifornien som använder en Windows-enhet sig för både Experience A (Windows-publik) och Experience C (California-publik). Den här användaren visas Experience A eftersom den visas i listan ovanför Experience C på målsidan.

![audiences_order image](assets/audiences_order.png)

## Varför ska jag namnge samma målgrupp i [!DNL Target] , Adobe Audience Manager (AAM) och Audience Library i bastjänsterna skiljer sig åt? {#section_F67E61A607B6444C8DAA4F99C3E95AED}

Målgruppsnamn i [!DNL Target] är unika, som [!DNL AAM] och [!DNL Audience Library]kan du ha samma namn för flera målgrupper (om de finns i olika mappar).När [!DNL Target] påträffar ett målgruppsnamn som motsvarar ett [!DNL AAM] eller [!DNL Audience Library] målgrupp, [!DNL Target] lägger till &quot;#&lt;number>till namnet.

Du kan till exempel se följande målgrupper: &quot;PC Users&quot; (in [!DNL AAM]) och &quot;PC Users #1&quot; (in [!DNL Target]).

## Varför kan jag inte byta namn på en publik? {#section_54E420556F534D20836E261E253D8B97}

Vissa målgrupper är fördefinierade, till exempel&quot;Nya besökare&quot; och&quot;Returning Visitors&quot;. Dessa fördefinierade målgrupper kan inte namnändras av användare.

## Varför visas inte alla profilparametrar i [!DNL Target] användargränssnitt? {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] har en gräns på 50 unika profilattribut per mbox-anrop. Om du behöver skicka mer än 50 profilattribut till [!DNL Target]kan du skicka dem med [!UICONTROL Profile Update] API-metod. Mer information finns i [Profiluppdatering](https://developers.adobetarget.com/api/#authentication-tokens) i Adobe Target API-dokumentationen.

## Varför ser besökarna upplevelser för en AP-aktivitet som de inte ska se? {#section_41CECEAE0881446A8D9F3B016857914B}

Automated Personalization-aktiviteter utvärderas en gång per session. Om det finns aktiva sessioner som har kvalificerat sig för en viss upplevelse och nu har nya erbjudanden lagts till, kommer användarna att se det nya innehållet tillsammans med tidigare erbjudanden. Eftersom de tidigare har kvalificerat sig för de här upplevelserna skulle de fortfarande se dem under hela sessionen. Om du vill utvärdera detta vid varje sidbesök bör du byta till aktivitetstypen Experience Targeting (XT).

## Varför återspeglas ändringar i målgrupper som skapats via API inte i [!DNL Target] UI? {#section_6BEB237CAC004A06A290F9644E5BF0FB}

Till skillnad från erbjudanden och profilskript synkroniseras för närvarande inte ändringar som görs av API till målgrupper som skapats via Target Standard tillbaka till målgränssnittet.

## Strängar som representerar tal (flyttal stöds också) jämförs som tal.{#strings-that-represent-numbers}

Om den vänstra och högra delen av likhetsuttrycken kan tolkas till ett tal, jämförs de två delarna som tal, inte som strängar.

Exempel:

| Värde | Målvillkor | Resultat |
| --- | --- | --- |
| 1.0 | är lika med 1 | true |
| 1 | equalsIgnoreCase 1.0 | true |
| 1,230 | är lika med 1 | true |
| 1 500 | är lika med 1,5 | true |
| 1 200 | är mindre än 2 | true |
| 2 | är större än 3.0 | false |
| 045 | är lika med 45 | true |

Siffror skrivna med vetenskaplig notation jämförs alltid som strängar.

Exempel:

&quot;4e-2&quot; är bara lika med &quot;4e-2&quot;. Det kommer *not* lika med &quot;0.04&quot;.
