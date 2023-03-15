---
keywords: IP-adress;IP-adresser;vitlista;tillåtelselista;brandvägg;recs;feed;servrar;adobe marketing cloud;rekommendationer
description: Visa en lista över IP-adresser som används i [!DNL Target] Recommendations servrar för hantering av feeds som hjälper dig att konfigurera brandväggen så att IP-adresser från Adobe-servrar tillåts.
title: Vilka IP-adresser använder Recommendations-servrar för mathantering?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 0%

---

# IP-adresser som används av Recommendations feed-bearbetningsservrar

Lista över IP-adresser som används i [!DNL Adobe Target] [!DNL Recommendations] servrar för feed-processing som hjälper dig att konfigurera brandväggen så att IP-adresser från Adobe-servrar tillåts.

[!DNL Target] [!UICONTROL Recommendations] Följande AWS-värdar används för att komma åt kundernas FTP-servrar:

| Plats | Värd |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API:er använder också samma AWS-värdar.

>[!NOTE]
>
>Dessa IP-adresser uppdaterades senast den 16 mars 2021. Tidigare fanns servrarna som använde FTP-servrarna i CIDR-blocket 192.243.242.0/24. Servrarna som var värdar för Recommendations API:er fanns i CIDR-blocket 192.243.224.0/20.
