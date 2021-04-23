---
keywords: IP-adress;IP-adresser;vitlista;tillåtelselista;brandvägg;recs;feed;servrar;adobe marketing cloud;rekommendationer
description: Visa en lista över IP-adresser som används i [!DNL Target] Recommendations feeds-bearbetningsservrar så att du kan konfigurera brandväggen så att IP-adresser från Adobe-servrar tillåts.
title: Vilka IP-adresser använder Recommendations-servrar för mathantering?
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%

---

# ![](/help/assets/premium.png) PREMIUMIP-adresser som används av Recommendations servrar för bearbetning av matning

Lista med IP-adresser som används i [!DNL Adobe Target] [!DNL Recommendations]-feeds-servrar för att hjälpa dig konfigurera brandväggen så att IP-adresser från Adobe-servrar tillåts.

[!DNL Target] [!UICONTROL Recommendations] Följande AWS-värdar används för aktiviteter vid åtkomst till kundernas FTP-servrar:

| Plats | Värd |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API:er använder också samma AWS-värdar.

>[!NOTE]
>
>Dessa IP-adresser uppdaterades senast den 16 mars 2021. Tidigare fanns servrarna som använde FTP-servrarna i CIDR-blocket 192.243.242.0/24. Servrarna som var värdar för Recommendations API:er fanns i CIDR-blocket 192.243.224.0/20.
