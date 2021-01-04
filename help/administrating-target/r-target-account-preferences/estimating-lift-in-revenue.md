---
keywords: revenue lift;revenue;estimating lift in revenue;calculate lift;estimated value
description: Använd Adobe Target för att uppskatta den vinst du skulle uppnå om alla användare såg den vinnande upplevelsen.
title: Uppskattad ökning av intäkter
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 0%

---


# Uppskattad ökning av intäkter{#estimate-lift-in-revenue}

Använd [!DNL Adobe Target] för att uppskatta den vinst du skulle uppnå om alla användare såg den vinnande upplevelsen.

>[!NOTE]
>
>Uppskattad lyft är för närvarande inte tillgänglig för [!UICONTROL Experience Targeting] (XT)-aktiviteter.

Den uppskattade lyftfunktionen är inaktiverad som standard. Den kan aktiveras i dina kontoinställningar. Det är bara användare av Experience Cloud Admin som kan aktivera eller inaktivera den här funktionen. Om den uppskattade höjden är inaktiverad visas inte motsvarande fält i gränssnittet. Om du inaktiverar funktionen går det inte att förlora data, inklusive data som används för dina uppskattningar. Beräkningarna baseras på data som samlas in oavsett om funktionen är aktiverad eller inte.

>[!IMPORTANT]
>
>Den uppskattade hissen är endast en uppskattning. Hur riktig den är beror på ett antal faktorer, bland annat på prognostiserade siffror om de aktuella trenderna fortsätter. Dessa värden är uppskattningar baserade på tidigare resultat och bör inte användas som ekonomisk vägledning. Framtida resultat kan variera.

Denna uppskattning beräknar den lyft som den vinnande upplevelsen och det totala antalet besökare har uppnått under aktivitetens livstid, och visar den lyft som du kan uppnå om alla besökare ser den vinnande upplevelsen, om trenderna fortsätter som de har under testet.

Den uppskattade ökningen av intäkterna beräknas utifrån de intäkter per besök (RPV) som erhållits från det primära målmåttet.

Den uppskattade lyften beräknas med hjälp av följande formel: (&lt;vinnande upplevelse RPV> - &lt;kontrollupplevelse RPV&lt;)*&lt;totalt antal besökare i aktiviteten>

Det resulterande talet avrundas till en decimal, max, om det komprimerade formuläret bara har en siffra före decimaltalet. Till exempel: 1,6 miljoner dollar, 60 000 dollar, 900 dollar, 8,5 000 dollar

Om din vinnande upplevelse till exempel visar ett lyft på 0,59 USD, och din kontrollupplevelse visar ett lyft på 0,15 USD, beräknar uppskattningen ett lyft på 0,44 USD per besökare. Om ni hade 75 000 besökare skulle intäkterna öka med 33 000 dollar om alla besökare ser den vinnande upplevelsen och de aktuella trenderna fortsätter.

På samma sätt kan du förvänta dig en ökning på 32 640 dollar om den vinnande upplevelsen visar en ökning på 0,17 dollar i kontrollupplevelsen och du har haft 192 000 besökare under testperioden.

Den uppskattade höjningen i inkomstfältet visas som &quot;—&quot; under följande omständigheter:

* Om det inte finns tillräckligt många besökare för att beräkna en rimlig uppskattning
* Om det uppskattade värdet av måttet inte har angetts på sidan för metriska inställningar
* Om den bästa prestandaupplevelsen är kontrollen

När du ställer in en aktivitets mål ger fältet Uppskattat värde ett värde för ditt mål. Detta värde gör att Target kan beräkna den uppskattade ökningen av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet.

Den beräknade intäkten om 100 % av besökarna ser den vinnande upplevelsen visas högst upp i Target-rapporterna.
