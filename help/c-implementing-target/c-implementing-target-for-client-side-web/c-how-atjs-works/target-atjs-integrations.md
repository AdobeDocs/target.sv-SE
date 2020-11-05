---
keywords: at.js integration;supported integrations;unsupported integrations;third party integrations
description: Information om vanliga integreringar med Target och deras supportstatus med at.js.
title: at.js-integreringar
feature: client-side
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 0%

---


# at.js-integreringar{#at-js-integrations}

Information om vanliga integreringar med [!DNL Target] och deras supportstatus med at.js.

Om du har ett övertygande behov av en integrering som inte stöds eller nämns här, kan du kontakta din kontorepresentant eller konsult.

## Integreringar som stöds {#section_3B44A970D3FB42D1973701452C868B55}

| Integrering | Detaljer |
|--- |--- |
| Analyser för mål (A4T) | Se [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE). |
| Profiler och målgrupper (P&amp;A) | Se [Målgrupper](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) i *användarhandboken* för bastjänsterna. |
| Experience Cloud ID-tjänst | Se dokumentationen [för](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Cloud ID-tjänsten. |
| Adobe Launch | Launch är nästa generationens tagghanteringsplattform från Adobe och är den metod som rekommenderas för att implementera Adobe Target. Launch ger kunderna ett enkelt sätt att driftsätta och hantera alla analyser, marknadsförings- och annonstaggar som behövs för att driva relevanta kundupplevelser.  Se [Implementera mål med hjälp av Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25). |
| Dynamic Tag Management (DTM) | Se [Bästa praxis för implementering av mål med hjälp av guiden](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html)för dynamisk tagghantering.   Viktigt: [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) är den föredragna, aktuella metoden för implementering av Target och biblioteket at.js. Använd Launch för nya målimplementeringar. Följande guide gäller befintliga klienter som använder en DTM-implementering.   Tänk på följande när du använder en DTM-integrering: <ul><li>Bibliotekshantering: Använd värdalternativet&quot;Anpassad&quot; för att använda at.js. Automatisk hantering stöds för närvarande inte. </li></ul> |
| Adobe Experience Manager (AEM) Cloud Service | Den AEM Cloud Servicen gör det möjligt att skapa A/B-tester och Experience Targeting-aktiviteter i det AEM arbetsflödet. Stöder at.js med Adobe Experience Manager 6.2 med FP-11577 (eller senare). Mer information finns i [Integrera med Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) och välja AEM. |
| AEM Experience Fragments | Med upplevelsefragment som skapats i AEM i Target-aktiviteter kan ni kombinera användarvänligheten och kraften hos AEM med kraftfulla funktioner för automatiserad intelligens (AI) och maskininlärning (ML) i Target för att testa och personalisera upplevelser i stor skala.  AEM samlar allt innehåll och alla resurser på en central plats för att understödja er personaliseringsstrategi. AEM gör det enkelt att skapa innehåll för datorer, surfplattor och mobila enheter på en och samma plats utan att behöva skriva kod. Du behöver inte skapa sidor för alla enheter - AEM justerar automatiskt varje upplevelse med ditt innehåll.  Se [AEM upplevelsefragment](/help/c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8). |

## Integreringar som inte stöds {#section_8EFCAED418DC42E0B07F95924819EAC2}

| Integrering | Detaljer |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | Det var integreringen som skickade kampanj- och recept-ID till [!DNL SiteCatalyst] via sidanropet så att du kunde rapportera i [!DNL SiteCatalyst] användargränssnittet. Den här funktionen ersätts av A4T. |
| [!DNL Legacy Target to SiteCatalyst Integration] | Detta var den integrering som gjorde att mbox-anrop namngavs `"SiteCatalyst: Event"` och `"SiteCatalyst: Purchase"` så att ni kunde bygga framgångsmått och användarprofiler baserade på variabler och props. Den här funktionen ersätts av A4T och P&amp;A. |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | Det här var integreringen som gjorde ett front-end API-anrop för att hämta AAM segment och sedan skicka dem som mbox-parametrar för varje mbox-anrop på sidan. |

## Tredjepartsintegreringar {#section_EE599839CCAD49DD97640E5EDAD9082E}

| Integrering | Detaljer |
|--- |--- |
| Andra tagghanterare | at.js bör fungera med tagghanteringsplattformar som inte är Adobe, men var försiktig med att använda anpassade integreringsfunktioner som andra leverantörer har utvecklat. Deras integreringar kan vara beroende av interna mbox.js-funktioner som inte längre finns i at.js. |
| Tredjepartsleverantörer av data (t.ex. Demandbase, Bluekai, API:er för väder) | Många tredjepartsdataleverantörer som används som komplement till Target-användarprofilering kan integreras med funktionen at.js [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers) . |