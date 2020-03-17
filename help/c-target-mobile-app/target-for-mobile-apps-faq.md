---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: Frågor och svar om Adobe Target för mobilappar.
title: Vanliga frågor och svar om Adobe Target för mobilappar
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 4ce4cf754ec64ec54c72bcb0557f042a92f5a8e3

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

## Kan jag utnyttja målgrupper från Adobe Audience Manager (AAM) i VEC för mobilappar?

Ja, Adobe Experience Platform Mobile SDK:er är byggda för [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)och Target. Era målgrupper i Audience Manager delas med [!DNL Target].

## Finns det någon mobilappsintegrering mellan mobilaktiviteterna Adobe Experience Manager (AEM) och Target?

Det står på vår färdplan, men det finns ingen tidslinje än. För närvarande kan du dela JSON- [upplevelsefragment](/help/c-experiences/c-manage-content/aem-experience-fragments.md) från AEM till Target och det kan finnas möjlighet att sedan använda dem i en mobilappsaktivitet.

## Kan jag lägga till fler bilder med VEC eller endast ändra befintliga bilder?

Du kan för närvarande bara ändra befintliga bilder.
