---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 065220af5c8e3b6cc25ef7289d006a901d2e932a
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 22 juli 2025**

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
* En ny API-slutpunkt introducerades som gör att användare kan återställa tidigare borttagna aktivitetsalternativ från en sekundär databas. Den här funktionen utnyttjar den befintliga infrastrukturen som tillhandahålls av klasserna `RemovedCampaignElements` och `RemovedOptionInfo`, vilket säkerställer smidig återintegrering av borttagna alternativ i aktiva aktiviteter. (TGT-52903)
* Korrigerade ett problem i det uppdaterade användargränssnittet för [!DNL Target] där raderade erbjudanden i [!UICONTROL Automated Personalization] (AP) aktiviteter visades som `Deleted option with ID: X` i stället för deras ursprungliga namn (till exempel `Offer Name [Deleted]` enligt det gamla användargränssnittet). Med den här korrigeringen återställs meningsfulla etiketter för borttagna erbjudanden, vilket gör rapporteringen tydligare och mer användarvänlig. (TGT-52921)
* Korrigerade ett problem i det permanenta bakgrundslagret där borttagna alternativ lagrades korrekt men inte var tillgängliga via befintliga API-slutpunkter. Därför kunde klientprogram inte hämta beskrivande namn för borttagna alternativ, vilket påverkade historiska rapportvyer. Den här korrigeringen ser till att bevarade borttagna alternativdata nu kan visas korrekt i användargränssnittet. (TGT-52973)
* Ett problem har korrigerats där vissa aktiviteter som migrerades från Target-fronten till Target Central hade inkonsekventa mätkonfigurationer på grund av ett tidigare fast synkroniseringsfel. Aktiviteter som ursprungligen använde ett konverteringsmått och som senare uppdaterades till ett analysbaserat mått, lagrades inaktuella värden i fälten `primaryMetricType` och `successCriteria`. (TGT-52643)

+++

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
* Ett problem har korrigerats där [!DNL Recommendations] aktiviteter som innehåller måttnamn som är längre än 25 tecken inte kunde öppnas eller redigeras på grund av API-begränsningar. Den här korrigeringen säkerställer kompatibilitet med metriska namn som överskrider teckengränsen och återställer fullständig åtkomst till berörda aktiviteter. (TGT-52839)
* Ett problem har korrigerats där användare inte kunde redigera aktiviteten site_cart_z1 [!DNL Recommendation] i användargränssnittet för [!DNL Target]. Ett försök att öppna aktiviteten utlöste ett fel på sidan [!UICONTROL Overview], vilket blockerade åtkomst till redigeraren. (TGT-53221)

+++

**Rapportering**

+++Se information
* Ett problem har korrigerats där sandlådefältet i aktivitetsdatabasen inte rensades när rapportkällan växlades från [!DNL Customer Journey Analytics] eller [!DNL Analytics] till [!DNL Target]. Tidigare skickade användargränssnittet en korrekt sandlåda: null, men backend ignorerade det här värdet och lämnade inaktuella sandlådedata på plats. Backend rensar nu sandlådefältet korrekt när null tas emot. (TGT-52798)
* Återimplementerade det borttagna alternativbeständiga lagret i målserverdelen för att stödja korrekt historikrapportering i [!UICONTROL Automated Personalization] (AP)-aktiviteter. Tidigare, när ett alternativ togs bort, gick dess namn förlorat, vilket gjorde det svårt att tolka tidigare prestandadata.

  **Viktiga förbättringar**:

   * Borttagna alternativ spåras nu med den befintliga `RemovedCampaignElements`- och `RemovedOptionInfo`-infrastrukturen.
   * När ett alternativ tas bort från en AP-aktivitet bevaras dess metadata (till exempel ID och namn).
   * Rapporteringsgränssnittet kan nu visa det ursprungliga alternativnamnet (till exempel `Option Name [Deleted]`) tillsammans med historiska värden, vilket förbättrar klarheten och användbarheten.

  Denna uppdatering ger en konsekvent och meningsfull rapportering, även efter det att alternativen har tagits bort från en aktivitet. (TGT-52986)

* Implementerade en ny migreringsslutpunkt som stöder överföring av borttagna aktivitetsalternativ från JCR-baserade aktiviteter till [!DNL Target] Central. Den här funktionen gör det möjligt att följa upp och rapportera konsekvent mellan olika system. Den här funktionen ser till att borttagna alternativ bevaras och synkroniseras över [!DNL Target] frontend och backend, vilket förbättrar den historiska rapporteringen och dataintegriteten. (TGT-53217)

+++

**Visual Experience Composer (VEC)**

+++Se information

* Korrigerade ett fel i VEC där en ändring av en vy orsakade duplicering och utlöste ett fel av typen&quot;Ogiltig användarinmatning&quot;. (TGT-52886)
* Ett problem med funktionen [!UICONTROL Undo] för alternativen [!UICONTROL Insert Before] och [!UICONTROL Insert After] har korrigerats vid konfiguration av bilderbjudanden i VEC.

  Om du tidigare ångrar en [!UICONTROL Insert Before]- eller [!UICONTROL Insert After]-åtgärd för bilderbjudanden uppstod ett inkonsekvent beteende eller ett fel uppstod när ändringen skulle återställas korrekt, särskilt i aktiviteter som skapades i det äldre [!DNL Target]-gränssnittet. Det här problemet har lösts för att säkerställa att ångra-åtgärder nu fungerar tillförlitligt för dessa ändringar. (TGT-52809)

* Ett problem har korrigerats där attributet `contentEditable` oavsiktligt hade angetts till true och sparades i sparat HTML-innehåll. Denna uppdatering säkerställer renare, förväntade HTML-utdata utan oönskat redigeringsbeteende. (TGT-52319)
* För att förhindra permanent förlust av borttagna alternativ och för att säkerställa ett konsekvent beteende för alla tjänster har funktionen för mjuk borttagning implementerats för alternativ i användargränssnittet och relaterade mikrotjänster.

  **Viktiga ändringar**:

   * Alternativen tas inte längre bort permanent. I stället markeras de med en ny borttagen: true-flagga i parameterns XML-objekt.
   * Den här flaggan används endast av det uppdaterade användargränssnittet för [!DNL Target] för att utesluta borttagna alternativ från återgivning och för att förhindra att de skickas till kanttjänster.
   * Borttagna alternativ är fortfarande en del av aktivitetens nyttolast under redigeringar, vilket säkerställer spårbarhet samtidigt som man undviker att ge kunderna obefintliga alternativ.

  Uppdateringen förbättrar dataintegriteten och är anpassad efter bästa praxis för hantering av borttagningar i distribuerade system. (TGT-52726)

+++

**Arbetsytor**

+++Se information
* Ett problem har korrigerats vid kopiering av en aktivitet från en icke-standardarbetsyta eller mellan icke-standardarbetsytor. Erbjudandena är nu dubblerade med förbättrad spårning och namngivning för att förhindra konflikter.

  **Viktiga förbättringar**:
   * Erbjudandena återskapas i målarbetsytan med uppdaterade ID:n och metadata.
   * Kopierade erbjudanden får nya namn i formatet:&quot;Erbjudandekopia&quot; plus ett slumpmässigt nummer eller en tidsstämpel för att säkerställa att de är unika.
   * Systemet uppdaterar erbjudanden och aktivitetstillstånd för att återspegla de nya ID:n.
   * Den här funktionen förhindrar fel som orsakas av flera identiska&quot;Erbjudandekopia&quot;-namn vid upprepade kopieringsåtgärder.
   * Erbjudandena kanske inte visas omedelbart i erbjudandelistan för målarbetsytan, utan bearbetas och visas på rätt sätt.

  Den här uppdateringen förbättrar tillförlitligheten och spårbarheten när erbjudanden hanteras på flera arbetsytor. (TGT-53080)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
