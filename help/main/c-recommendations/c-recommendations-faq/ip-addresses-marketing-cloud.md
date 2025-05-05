---
keywords: IP-adress;IP-adresser;vitlista;tillåtelselista;brandvägg;recs;feed;servrar;adobe marketing cloud;rekommendationer
description: Visa en lista över IP-adresser som används i  [!DNL Target] Recommendations-servrar för feeds som hjälper dig att konfigurera brandväggen så att IP-adresser från Adobe-servrar tillåts.
title: Vilka IP-adresser använder Recommendations-servrar för mathantering?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: be5b3158c758fa08802c1dc0541c9e989a2c7740
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# IP-adresser som används av [!DNL Recommendations] feeds-bearbetningsservrar

Lista över IP-adresser som används i [!DNL Adobe Target] [!DNL Recommendations]-servrar för feed-bearbetning för att hjälpa dig konfigurera brandväggen så att IP-adresser från [!DNL Adobe]-servrar tillåts.

>[!IMPORTANT]
>
>Teamet [!DNL Target] uppdaterar NAT-gatewayadresserna för hämtning av [!DNL Recommendations]-feeds. Om du implementerar IP-tillåtelselistning måste du tillåtslista följande nya AWS-värdar. De befintliga värdarna planeras att avvecklas den 30 juni 2024. Om du vill ha en mjuk övergång tillåtslista du alla nio adresserna. Det är inte brådskande att ta bort de befintliga adresserna.

[!DNL Target] [!UICONTROL Recommendations]-aktiviteter använder följande AWS-värdar vid åtkomst till kundens FTP-servrar:

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
