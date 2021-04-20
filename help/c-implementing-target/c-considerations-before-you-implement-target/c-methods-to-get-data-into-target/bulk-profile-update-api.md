---
keywords: implementera;implementera;konfigurera;bulkprofiluppdatering
description: Hämta data till Target med bulkprofilens uppdaterings-API.
title: Hur hämtar jag data till målet med API:t för gruppprofiluppdatering?
feature: Implementation
role: Developer
exl-id: 068658fc-7082-425a-87c1-dd0de03cdc71
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# API för gruppprofilsuppdatering

Via API skickar du en CSV-fil till [!DNL Adobe Target] med uppdateringar av besökarprofilen för många besökare. Varje besökarprofil kan uppdateras med flera profilattribut på sidan i ett anrop.

Det här alternativet liknar kundattribut med några skillnader:

* Kundattribut använder en FTP-överföring medan API:t för uppdatering av målgruppsprofil använder ett API för HTTP-POST.
* Data för kundattribut kan delas med Analytics. Det går bara att använda gruppprofilsuppdatering i Target.
* Kundattribut som stöder att skapa en profil för ett användarmål har ännu inte setts. API:t för uppdatering av gruppprofil uppdaterar bara befintliga målprofiler.
* Kundattribut kräver att Experience Cloud ID (ECID) används. API:t för uppdatering av gruppprofil kräver antingen TNT-ID eller `mbox3rdPartyId`.
* Du kan inte skicka följande tecken i `mbox3rdPartyID`: plustecken (+) och snedstreck (/).

## Format

CSV-filen måste referera till varje besökare via sitt Target PCID eller mboxThirdPartyId. Experience Cloud ID (ECID) stöds inte. Alla profilattribut/värden skapas och uppdateras via API:t. Formatinformation finns i API-dokumentationen.

## Exempel på användningsområden

CRM-systemet eller andra interna system lagrar värdefulla data om besökarna som du vill uppdatera konsekvent i Target, utan att visa profildata i din sidimplementering.

## Fördelar med metoden

Det finns ingen gräns för antalet profilattribut.

Profilattribut som skickas via webbplatsen kan uppdateras via API och vice versa.

## Caveats

Batchfilens storlek måste vara mindre än 50 MB. Dessutom bör det totala antalet rader inte överstiga 500 000 rader per överföring.

Det finns ingen gräns för hur många rader du kan överföra under 24 timmar i efterföljande batchar. Intag kan dock begränsas under kontorstid för att säkerställa att andra processer körs effektivt.

Flera [V2-batchuppdateringsanrop](https://developers.adobetarget.com/api/#updating-profiles) utan mbox-anrop däremellan för samma thirdPartyIds åsidosätter egenskaperna som uppdaterades i det första batchuppdateringsanropet.

## Exempel på koder

Se [Uppdatera profiler](https://developers.adobetarget.com/api/#updating-profiles).

### Länkar till relevant information

[Uppdaterar profiler](https://developers.adobetarget.com/api/#updating-profiles)
