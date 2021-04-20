---
keywords: implementera;implementera;konfigurera;konfigurera;sidparameter
description: Hämta in data i Target med profilattribut på sidan.
title: Hur hämtar jag data till målet med hjälp av attribut för sidprofil?
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Profilattribut på sidan

Attribut för sidprofiler i [!DNL Adobe Target] (kallas även&quot;in-mbox profile attributes&quot;) är namn/värde-par som skickas direkt via sidkod som lagras i besökarens profil för framtida bruk.

Med profilattribut på sidan kan användarspecifika data lagras i Target-profilen för senare målinriktning och segmentering.

## Format

Profilattribut på sidan skickas till Target via ett serveranrop som ett strängnamn/värde-par med prefixet &quot;profile&quot;. före attributnamnet.

Attributnamn och värden är anpassningsbara (även om det finns &quot;reserverade namn&quot; för vissa användningsområden).

### Exempel

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## Exempel på användningsområden

* **Inloggningsinformation**: Dela icke-PII-data (Personally Identiitable Information) till Target baserat på användarens inloggning. Dessa data kan vara medlemskapsstatus, orderhistorik eller mer.
* **Butiksinformation**: Spåra vilket arkiv som är användarens föredragna plats.
* **Tidigare interaktioner**: Spåra vad användaren har gjort på webbplatsen tidigare för att informera om framtida personalisering.

## Fördelar med metoden

Data skickas till Target i realtid och kan användas i samma serveranrop som data kommer in i.

## Caveats

Kräver uppdatering av sidkod (direkt eller via ett tagghanteringssystem).

Attribut och värden visas vid serveranrop, så att besökaren kan se värdena. Om du delar information som kreditintervall eller annan potentiellt privat information kanske den här metoden inte är den bästa metoden.

## Exempel på koder

targetPageParamsAll (bifogar attributen till alla mbox-anrop på sidan):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (appends the attributes to the global mbox on the page):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Attribut i mboxSkapa kod:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## Länkar till relevant information

[Profilattribut](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Besökarprofil](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
