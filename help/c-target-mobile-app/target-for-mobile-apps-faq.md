---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: Frågor och svar om Adobe Target för mobilappar.
title: Vanliga frågor och svar om Adobe Target för mobilappar
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 9646a1434d499a595c9c8140e0fece7b48c9955a
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---


# Mål för mobilappar - frågor och svar

Lista med vanliga frågor om [!DNL Target] mobilappar.

## Ska jag använda [!DNL Adobe Experience Platform Launch] för att distribuera SDK, eller kan jag distribuera SDK utan att använda [!DNL Launch]?

SDK är tillgängligt på [Adobe Marketing Cloud Git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Om du inte använder [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)måste du hantera din egen inställningsfil och hantera den i appen.

## Vilka SDK:er finns tillgängliga idag?

Adobe Experience Platform Mobile SDK:er har för närvarande stöd för iOS, Android och React. Mer information finns i handboken [för](https://aep-sdks.gitbook.io/docs/)Adobe Experience Cloud-plattformens mobila SDK:er.

## Vilken frekvens har den platsbaserade funktionen för verifiering av latitud och longitud?

Mer information finns i dokumentationen [till](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places.

## Behöver jag at.js för att Adobe Experience Platform Mobile SDK:er ska fungera?

Nej, du behöver inte at.js för att använda SDK:n för mobilen. at.js är JavaScript- [!DNL Target] biblioteket för webbplatser. Adobe Experience Platform Mobile SDK:er är för mobilappar.

## Är Target Mobile bara en funktionalitet i Adobe Target Premium Product SKU?

För Adobe Target Standard-kunder kan du endast använda våra mobila SDK:er för A/B Test- och Experience Targeting-aktiviteter (XT). Om du vill använda rekommendationer eller AI-funktioner i mobilappen behöver du en [Adobe Target Premium](/help/c-intro/intro.md#premium) -licens.

## Finns det någon mobilappsintegrering mellan mobilaktiviteterna Adobe Experience Manager (AEM) och Target?

Det står på vår färdplan, men det finns ingen tidslinje än. För närvarande kan du dela JSON- [upplevelsefragment](/help/c-experiences/c-manage-content/aem-experience-fragments.md) från AEM till Target och det kan finnas möjlighet att sedan använda dem i en mobilappsaktivitet.
