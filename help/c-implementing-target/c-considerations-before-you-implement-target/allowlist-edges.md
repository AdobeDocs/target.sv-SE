---
keywords: implementera;implementera;vitlista;vit lista;tillåtelselista;tillåtelselista;kant;kanter
description: Visa en lista med värdar som hjälper dig att tillåtslista Adobe Target-kanter (geografiskt utspridda noder som ger optimala svarstider för slutanvändarna).
title: Hur Tillåtslista jag Edge-målnoder?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: 806c52e69cce636a56eb067759612f80829418f9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---


# Tillåtelselista: Hörnkantsnoder

Information och en uppdaterad lista över värdar som kan hjälpa dig att tillåtslista kanter i [!DNL Adobe Target].

En kant är en geografiskt fördelad serverarkitektur som ger optimala svarstider för slutanvändare som behöver innehåll, oavsett var de befinner sig. Varje edge-nod har all information som krävs för att svara på användarens innehållsförfrågan och för att spåra analysdata på den begäran. Användarförfrågningar dirigeras till närmaste kantnod. Mer information finns i [Edge Network](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) i *Hur Adobe [!DNL Target] fungerar*.

Du kan tillåtslista kantnoderna [!DNL Target] om du vill.

## NAT-IP-adresser (Network Address Translation) för målkanter

Lista över IP-adresser för utgångar för [!DNL Target]-kanter. Tillåtslista dessa IP-adresser om du tänker få Target att nå ut till era tjänster.

| Edge Location | IP-adresser för Egress |
| --- | --- |
| Edge31 (Mumbai) | 13.126.131.246<br>13.234.229.8 |
| Edge32 (Tokyo) | 3.115.154.28<br>3.115.227.146 |
| Edge34 (East Coast US) | 34.232.149.249<br>52.21.139.93 |
| Edge35 (West Coast US) | 52.10.11.139<br>44.231.171.161 |
| Edge36 (Sydney) | 13.237.227.20<br>13.210.93.142 |
| Edge37 (Irland) | 54.72.21.68<br>52.208.139.19 |
| Edge38 (Singapore) | 18.141.132.96<br>54.179.187.167 |

## IP-adresser för målkant

Lista över IP-adresser för [!DNL Target]-kanter. Tillåtslista de här IP-adresserna om du vill göra API-anrop till målkanterna.

| Edge Location | Domän | IP-adresser |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(där CLIENTCODE är ditt  [!DNL Target] klient-ID) |  |
| Edge31 (Mumbai) | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.201 |
| Edge32 (Tokyo) | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34 (East Coast US) | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.22.9 3<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35 (West Coast US) | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162.2 74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36 (Sydney) | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37 (Irland) | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>5 2.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38 (Singapore) | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |





