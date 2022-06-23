---
keywords: integrering med at.js;integreringar som stöds;integreringar som inte stöds;integreringar från tredje part
description: Se integreringarna som stöds (och inte stöds) av Adobe [!DNL Target] at.js, inklusive Analytics för [!DNL Target] (A4T), Experience Cloud ID-tjänsten med mera.
title: Vilka integreringar stöder .js?
feature: at.js
role: Developer
exl-id: 148c744d-2a2b-40f8-964b-c51283ae7d1c
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%

---

# at.js-integreringar

Information om vanliga integreringar med [!DNL Target] och deras supportstatus med at.js.

Om du har ett övertygande behov av en integrering som inte stöds eller nämns här, kan du kontakta din kontorepresentant eller konsult.

## Integreringar som stöds {#section_3B44A970D3FB42D1973701452C868B55}

| Integrering | Detaljer |
|--- |--- |
| Analyser för mål (A4T) | Se [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE). |
| Profiler och målgrupper (P&amp;A) | Se [Målgrupper](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) i *Användarhandbok för bastjänster*. |
| Experience Cloud ID-tjänst | Se [Dokumentation för Adobe Experience Cloud ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| Taggar i [!DNL Adobe Experience Platform] | Taggar i [!DNL Adobe Experience Platform] är nästa generations tagghanteringsfunktioner från [!DNL Adobe]. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och reklamtaggar som behövs för att skapa relevanta kundupplevelser. Se [Implementera [!DNL Target] använda [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/). |
| Adobe Experience Manager (AEM) Cloud Service | Med AEM Cloud Service kan du skapa A/B-tester och Experience Targeting-aktiviteter i AEM arbetsflöde. Stöder at.js med Adobe Experience Manager 6.2 med FP-11577 (eller senare). Mer information finns i [Integrera med Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) och välja AEM. |
| AEM Experience Fragments | Med upplevelsefragment som skapats i AEM i Target-aktiviteter kan ni kombinera användarvänligheten och kraften hos AEM med kraftfulla funktioner för automatiserad intelligens (AI) och maskininlärning (ML) i Target för att testa och personalisera upplevelser i stor skala.  AEM samlar allt innehåll och alla resurser på en central plats för att understödja er personaliseringsstrategi. AEM gör det enkelt att skapa innehåll för datorer, surfplattor och mobila enheter på en och samma plats utan att behöva skriva kod. Du behöver inte skapa sidor för alla enheter - AEM justerar automatiskt varje upplevelse med ditt innehåll.  Se [AEM upplevelsefragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8). |

## Integreringar som inte stöds {#section_8EFCAED418DC42E0B07F95924819EAC2}

| Integrering | Detaljer |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | Det här var integreringen som skickade kampanj- och recept-ID till [!DNL SiteCatalyst] via ett sidsamtal så att du kan rapportera i  [!DNL SiteCatalyst] Gränssnitt. Den här funktionen ersätts av A4T. |
| [!DNL Legacy Target to SiteCatalyst Integration] | Det här var integreringen som gjorde namngivna mbox-anrop `"SiteCatalyst: Event"` och `"SiteCatalyst: Purchase"` så att ni kan bygga framgångsvärden och användarprofiler baserade på variabler och props. Den här funktionen ersätts av A4T och P&amp;A. |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | Det här var integreringen som gjorde ett front-end API-anrop för att hämta AAM segment och sedan skicka dem som mbox-parametrar för varje mbox-anrop på sidan. |

## Tredjepartsintegreringar {#section_EE599839CCAD49DD97640E5EDAD9082E}

| Integrering | Detaljer |
|--- |--- |
| Andra tagghanterare | at.js bör fungera med tagghanteringsplattformar som inte är Adobe, men var försiktig med att använda anpassade integreringsfunktioner som andra leverantörer har utvecklat. Deras integreringar kan vara beroende av interna mbox.js-funktioner som inte längre finns i at.js. |
| Tredjepartsleverantörer av data (t.ex. Demandbase, Bluekai, API:er för väder) | Många tredjepartsdataleverantörer som används som komplement till Target-användarprofilering kan integreras med hjälp av at.js [Dataleverantörer](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}. |
