---
keywords: implementera;implementera;konfigurera;kundattribut
description: Hämta data till [!DNL Target] med kundattribut.
title: Hur får jag in data på [!DNL Target] Använda kundattribut?
feature: Implementation
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Kundattribut

Med kundattribut kan du överföra besökarprofildata via FTP till [!DNL Adobe Experience Cloud]. Använd data i [!DNL Adobe Analytics] och [!DNL Adobe Target].

Target Standard-kunder kan tillämpa fem attribut, Target Premium-kunder kan tillämpa 200-attribut.

## Format

En CSV-fil med Experience Cloud ID (ECID) och attributnamn/värde-par överförs via FTP eller manuellt i användargränssnittet för Experience Cloud.

## Exempel på användningsområden

CRM-systemet eller andra interna system lagrar värdefull information som du vill dela med Adobe Experience Cloud, inklusive Target och Analytics.

## Fördelar med metoden

När du överför kunddata skapas en profilpost för besökaren i Target, även om Target ännu inte har sett besökaren.

Samma data är automatiskt tillgängliga i Target och Analytics.

FTP kan vara en enklare implementeringsmetod än API.

## Caveats

Target Standard-kunder kan använda fem attribut, Target Premium-kunder kan använda 200-attribut

Kan bara uppdatera värden via kundattribut, inte på sidan.

Kräver implementering av Experience Cloud ID (ECID).

## Exempel på koder

Information finns i [Skapa en kundattributkälla och överför datafilen](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Länkar till relevant information

[Skapa en kundattributkälla och överför datafilen](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
