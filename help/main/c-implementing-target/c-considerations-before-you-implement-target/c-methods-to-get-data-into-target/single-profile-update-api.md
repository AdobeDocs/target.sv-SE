---
keywords: implementera;implementera;konfigurera;konfigurera;uppdatering av en profil
description: Hämta data till [!DNL Target] med API:t för uppdatering av en profil.
title: Hur får jag in data på [!DNL Target] Använda API:t för uppdatering av en profil?
feature: Implementation
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# API för enkel profiluppdatering

Nästan identiskt med API:t för uppdatering av gruppprofil, men en besökarprofil uppdateras åt gången, i enlighet med API-anropet i stället för med en CSV-fil.

## Format

Besökaren måste identifieras via Target mboxPC-värdet eller mboxThirdPartyId-värdet. Experience Cloud ID (ECID) stöds inte.

## Exempel på användningsfall

Du vill uppdatera Target i realtid när en besökare utför någon offlineåtgärd. Åtgärderna kan omfatta att nå en kundtjänst, ett lån finansieras, använda ett förmånskort i butik, få tillgång till en kioskdator och så vidare.

## Fördelar med metoden

Det finns ingen gräns för antalet profilattribut.

Profilattribut som skickas via webbplatsen kan uppdateras via API och vice versa.

## Caveats

Gräns på 1 000 000 API-anrop (1 miljon) per 24-timmarsperiod

Uppdaterar endast profiler. Det går inte att skapa en profil för en potentiell användare som Target ännu inte ser.

## Exempel på koder

GET och POST stöds. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [Uppdaterar profiler](https://developers.adobetarget.com/api/#updating-profiles)
