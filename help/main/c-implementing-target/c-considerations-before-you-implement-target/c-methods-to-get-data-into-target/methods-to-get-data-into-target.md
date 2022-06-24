---
keywords: implementera;implementera;konfigurera;konfigurera;sidparameter;tomcat;url-kodad;in page profile attribute;mbox parameter;in page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;data provider;data provider
description: Hämta data till [!DNL Target] (sidparametrar, profilattribut, skriptprofilattribut, dataleverantörer, uppdaterings-API:er för en och flera profiler, kundattribut).
title: Hur får jag in data i Target?
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Översikt över metoder

Information om olika metoder som du kan använda för att hämta data till [!DNL Adobe Target].

Tillgängliga metoder:

| Metod | Detaljer |
| --- | --- |
| [Sidparametrar](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/page-parameters/){target=_blank}<br>(Kallas även&quot;mbox parameters&quot;) | Sidparametrar är namn/värde-par som skickas direkt via sidkod och som inte lagras i besökarens profil för framtida bruk.<br>Sidparametrar är användbara när du vill skicka siddata till Target som inte behöver lagras med besökarens profil för framtida målinriktning. Dessa värden används i stället för att beskriva sidan eller den åtgärd som användaren utförde på den specifika sidan. |
| [Profilattribut på sidan](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/in-page-profile-attributes/){target=_blank}<br>(kallas även&quot;in-mbox profile attributes&quot;) | Profilattribut på sidan är namn/värde-par som skickas direkt via sidkoden och som lagras i besökarens profil för framtida bruk.<br>Med profilattribut på sidan kan användarspecifika data lagras i Target-profilen för senare målinriktning och segmentering. |
| [Skriptprofilattribut](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/script-profile-attributes/){target=_blank} | Skriptprofilattribut är namn/värde-par som definieras i Target-lösningen. Värdet avgörs av om ett JavaScript-fragment körs på målservern per serveranrop.<br>Användare skriver små kodfragment som körs per mbox-anrop och innan en besökare utvärderas för målgrupps- och aktivitetsmedlemskap. |
| [Dataleverantörer](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/data-providers/){target=_blank} | Med dataleverantörer kan ni enkelt skicka data från tredje part till Target. |
| [API för gruppprofilsuppdatering](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/bulk-profile-update-api/){target=_blank} | Via API skickar du en CSV-fil till Target med uppdateringar av besökarprofilen för många besökare. Varje besökarprofil kan uppdateras med flera profilattribut på sidan i ett anrop. |
| [API för enkel profiluppdatering](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/single-profile-update-api/){target=_blank} | Nästan identiskt med API:t för uppdatering av gruppprofil, men en besökarprofil uppdateras åt gången, i enlighet med API-anropet i stället för med en CSV-fil. |
| [Kundattribut](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/customer-attributes/){target=_blank} | Med kundattribut kan du överföra besökarprofildata via FTP till Experience Cloud. Använd data i Adobe Analytics och Adobe Target när de har överförts. |












