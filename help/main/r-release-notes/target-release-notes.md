---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 926a045e5bcebc8d094ea41a6c1b7c59568a35ab
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 26 juni 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.6.4 (26 juni 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Alternativet [!UICONTROL Rearrange] har lagts till i det uppdaterade användargränssnittet för [!UICONTROL Visual Experience Composer] (VEC) för att anpassas till funktioner som är tillgängliga i det äldre VEC. (TGT-46957 &amp; TGT-52876)
* Ett problem har korrigerats där ändringar som gjorts i variantupplevelser (till exempel upplevelse B) i en [!UICONTROL A/B Test]-aktivitet inte sparades. Efter att ha bytt mellan upplevelser försvinner ändringarna till varianten. Problemet påverkade inte kontrollupplevelsen. (TGT-52664)
* Ett problem har korrigerats där vissa kunder inte kunde skapa eller spara aktiviteter, medan andra kunde utföra samma åtgärder utan problem. Problemet var inkonsekvent mellan konton.(TGT-52842)
* Ett problem har korrigerats där användare i det uppdaterade VEC inte kunde flytta ändringar till [!UICONTROL Page Load event], en funktion som fanns i det gamla användargränssnittet. (TGT-52617)
* Ett problem som förhindrade att vissa aktivitetsändringar visades korrekt i den uppdaterade VEC har åtgärdats. (TGT-52818)
* Ett null-pekarundantag som inträffade när rapportdata hämtades för [!UICONTROL Automated Personalization] (AP)-aktiviteter har åtgärdats. (TGT-52362)
* Ett problem har korrigerats som förhindrade att information på erbjudandenivå visas i .CSV-filen för [!UICONTROL Automated Personalization] (AP)-aktiviteter. (TGT-52675)
* Ett problem har korrigerats när ändringar tillämpades i den uppdaterade VEC-konfigurationen. Ändringarna visades ursprungligen korrekt, inklusive [!UICONTROL Experience Fragment]. Men när du byter upplevelser eller gör ytterligare redigeringar kan vissa ändringar inte tillämpas på grund av väljarproblem. (TGT-52679)
* Ett problem har korrigerats där QA-länkarna i den klonade aktiviteten felaktigt bevarade sidans URL:er från den ursprungliga aktiviteten när en ny aktivitet skapades genom kloning. (TGT-52775)
* Korrigerade ett problem som oavsiktligt förhindrade [!UICONTROL On-device Decisioning] från att vara tillgänglig i den uppdaterade VEC:n. (TGT-52371)
* Ett problem som gjorde att en produkt [!DNL Recommendations] inte kunde redigeras har åtgärdats. När du försöker få åtkomst till VEC via målgränssnittet uppstod ett fel på sidan [!UICONTROL Overview] som förhindrar redigeringar. (TGT-52823)
* Korrigerade ett problem som gjorde att en [!DNL Recommendations]-aktivitet inte kunde sparas när upplevelsenamnen överskrider 50 tecken. (TGT-52619)
* Ett problem har korrigerats där kunderna inte kunde spara aktiviteten Rekommendationer efter att ha ändrat villkoren i det nya användargränssnittet. Problemet verkar vara behörighetsrelaterat och påverkar inte alla användare med liknande roller. (TGT-52816)
* Ett problem har korrigerats där användare med rollen [!UICONTROL Editor] inte kunde redigera en [!DNL Recommendations]-aktivitet. Försök att ändra design och spara aktiviteten resulterade i ett 403-fel som anger att privilegiet [editor] krävdes, även om användaren redan hade den rollen i den relevanta arbetsytan. (TGT-52836)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
