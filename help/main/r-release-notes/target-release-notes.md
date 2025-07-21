---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: df7e28060a6add53e1aaed928351b4f399b19c17
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 10 juli 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.7.3 (24 juli 2025)

På grund av nyligen identifierade problem, som främst gäller komplexa kundanpassningar, innehåller den här versionen följande korrigeringar och uppdateringar:

**Aktiviteter**

+++Se information
* Ett problem har korrigerats där metoden `buildViews` i Builder-klassen felaktigt angav `viewMaxLocalId` till det totala antalet vyer, i stället för till det högsta `viewLocalId` som tilldelats. (TGT-53207)

**Formulärbaserad Experience Composer**

+++Se information
* Korrigerade ett fel i [!UICONTROL Form-Based Experience Composer] som gjorde att redigeraren kraschade efter att du klickade på ikonen **[!UICONTROL Manage Content]** ( ![Hantera innehåll ](/help/main/assets/icons/Experience.svg) ) när du skapade eller redigerade en [!UICONTROL Automated Personalization] -aktivitet. (TGT-53047)

+++

**Rekommendationer**

+++Se information
* Korrigerade ett problem som förhindrade [!UICONTROL Catalog Search] från att läsa in ytterligare resultat vid bläddring längst ned i listan, vilket återställde beteenden som överensstämmer med det tidigare användargränssnittet. (TGT-53088)
* Ett problem har korrigerats där kolumnen [!UICONTROL Number of Products] saknades på sidan [!UICONTROL Collections] i det uppdaterade användargränssnittet för [!DNL Target]. Kolumnen visas nu korrekt och förväntade funktioner återställs. (TGT-53168)
* Ett problem har korrigerats där [!UICONTROL Collection] regler inte filtrerades korrekt enligt reglerna. (TGT-53254)
* Ett problem som blockerade borttagning av objekt från dialogrutan [!UICONTROL Criteria Details] har korrigerats. (TGT-53245)
* Korrigerade ett problem som förhindrade att produkter som inte hade något namn öppnades eller interagerade. Det här problemet uppstod när miljöer som returnerade namnlösa resultat valdes, vilket förhindrar åtkomst till produktinformation. (TGT-53007)
* Korrigerade ett problem som gjorde att sidan [!UICONTROL Catalog Search] kraschade och att en tom skärm visades när vissa produkter valdes. (TGT-53087)

+++

**Visual Experience Composer (VEC)**

+++Se information

* Korrigerade ett fel i VEC där en ändring av en vy orsakade duplicering och utlöste ett fel av typen&quot;Ogiltig användarinmatning&quot;. (TGT-52886)
* Ett problem med funktionen [!UICONTROL Undo] för alternativen [!UICONTROL Insert Before] och [!UICONTROL Insert After] har korrigerats vid konfiguration av bilderbjudanden i VEC.

  Om du tidigare ångrar en [!UICONTROL Insert Before]- eller [!UICONTROL Insert After]-åtgärd för bilderbjudanden uppstod ett inkonsekvent beteende eller ett fel uppstod när ändringen skulle återställas korrekt, särskilt i aktiviteter som skapades i det äldre [!DNL Target]-gränssnittet. Det här problemet har lösts för att säkerställa att ångra-åtgärder nu fungerar tillförlitligt för dessa ändringar. (TGT-52809)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
