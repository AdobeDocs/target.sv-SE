---
keywords: IP-adress;IP-adresser;vitlista;tillåtelselista;brandvägg;recs;feed;servrar;adobe marketing cloud;rekommendationer
description: Visa en lista över IP-adresser som används i [!DNL Target] Recommendations servrar för hantering av feeds som hjälper dig att konfigurera brandväggen så att IP-adresser från Adobe-servrar tillåts.
title: Vilka IP-adresser använder Recommendations-servrar för mathantering?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: 558de92e672c276474bc76fad19e5461ae7d4c88
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# IP-adresser som används av [!DNL Recommendations] servrar för hantering av feeds

Lista över IP-adresser som används i [!DNL Adobe Target] [!DNL Recommendations] servrar för feed-processing som hjälper dig att konfigurera brandväggen så att IP-adresser från [!DNL Adobe] servrar.

>[!IMPORTANT]
>
>23 februari 2023: [!DNL Target] teamet uppdaterar för närvarande NAT-gatewayadresserna för hämtning [!DNL Recommendations] feeds. Om du implementerar IP-tillåtelselistning måste du tillåtslista följande nya AWS-värdar. De befintliga värdarna kommer att avvecklas i framtiden. Alla nio värdar är nu i drift.

[!DNL Target] [!UICONTROL Recommendations] Följande AWS-värdar används för att komma åt kundernas FTP-servrar:

**Nya värdar**:

| Plats | Värd |
| --- | --- |
| Oregon | `52.40.124.129` |
| Oregon | `54.148.219.69` |
| Oregon | `54.189.208.212` |
| Oregon | `44.230.236.35` |
| Oregon | `54.190.78.243` |
| Oregon | `52.41.73.133` |

**Befintliga värdar**:

| Plats | Värd |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API:er använder också samma AWS-värdar.
