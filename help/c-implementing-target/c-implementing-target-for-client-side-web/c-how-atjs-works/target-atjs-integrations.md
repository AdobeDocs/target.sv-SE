---
keywords: integrering med at.js;integreringar som stöds;integreringar som inte stöds;integreringar från tredje part
description: Se vilka integreringar som stöds (och inte stöds) av Adobe [!DNL Target] at.js, including Analytics for [!DNL Target] (A4T), Experience Cloud ID-tjänsten med mera.
title: Vilka integreringar stöder .js?
feature: at.js
role: Developer
exl-id: 148c744d-2a2b-40f8-964b-c51283ae7d1c
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 0%

---

# at.js-integreringar

Information om vanliga integreringar med [!DNL Target] och deras supportstatus med at.js.

Om du har ett övertygande behov av en integrering som inte stöds eller nämns här, kan du kontakta din kontorepresentant eller konsult.

## Integreringar som stöds {#section_3B44A970D3FB42D1973701452C868B55}

| Integrering | Detaljer |
|--- |--- |
| Analyser för mål (A4T) | Se [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE). |
| Profiler och målgrupper (P&amp;A) | Se [Målgrupper](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) i *Användarhandbok för bastjänster*. |
| Experience Cloud ID-tjänst | Läs [dokumentationen för Adobe Experience Cloud ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| Taggar i [!DNL Adobe Experience Platform] | Taggar i [!DNL Adobe Experience Platform] är nästa generation av tagghanteringsfunktioner från [!DNL Adobe]. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och annonstaggar som behövs för att skapa relevanta kundupplevelser. Se [Implementera [!DNL Target] med [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25). |
| Adobe Experience Manager (AEM) Cloud Service | Den AEM Cloud Servicen gör det möjligt att skapa A/B-tester och Experience Targeting-aktiviteter i det AEM arbetsflödet. Stöder at.js med Adobe Experience Manager 6.2 med FP-11577 (eller senare). Mer information finns i [Integrera med Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) och välj AEM. |
| AEM Experience Fragments | Med upplevelsefragment som skapats i AEM i Target-aktiviteter kan ni kombinera användarvänligheten och kraften hos AEM med kraftfulla funktioner för automatiserad intelligens (AI) och maskininlärning (ML) i Target för att testa och personalisera upplevelser i stor skala.  AEM samlar allt innehåll och alla resurser på en central plats för att understödja er personaliseringsstrategi. AEM gör det enkelt att skapa innehåll för datorer, surfplattor och mobila enheter på en och samma plats utan att behöva skriva kod. Du behöver inte skapa sidor för alla enheter - AEM justerar automatiskt varje upplevelse med ditt innehåll.  Se [AEM upplevelsefragment](/help/c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8). |

## Integreringar som inte stöds {#section_8EFCAED418DC42E0B07F95924819EAC2}

| Integrering | Detaljer |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | Det här var integreringen som skickade kampanj- och recept-ID till [!DNL SiteCatalyst] via sidanropet så att du kunde rapportera i användargränssnittet för [!DNL SiteCatalyst]. Den här funktionen ersätts av A4T. |
| [!DNL Legacy Target to SiteCatalyst Integration] | Detta var den integration som gjorde att mbox-anrop med namnen `"SiteCatalyst: Event"` och `"SiteCatalyst: Purchase"` kunde skapas så att du kunde bygga framgångsmått och användarprofiler baserat på var och props. Den här funktionen ersätts av A4T och P&amp;A. |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | Det här var integreringen som gjorde ett front-end API-anrop för att hämta AAM segment och sedan skicka dem som mbox-parametrar för varje mbox-anrop på sidan. |

## Tredjepartsintegreringar {#section_EE599839CCAD49DD97640E5EDAD9082E}

| Integrering | Detaljer |
|--- |--- |
| Andra tagghanterare | at.js bör fungera med tagghanteringsplattformar som inte är Adobe, men var försiktig med att använda anpassade integreringsfunktioner som andra leverantörer har utvecklat. Deras integreringar kan vara beroende av interna mbox.js-funktioner som inte längre finns i at.js. |
| Tredjepartsleverantörer av data (t.ex. Demandbase, Bluekai, API:er för väder) | Många tredjepartsdataleverantörer som används som komplement till Target-användarprofileringen kan integreras med funktionen at.js [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers). |
