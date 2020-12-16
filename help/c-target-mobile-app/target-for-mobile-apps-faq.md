---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: Frågor och svar om Adobe Target för mobilappar.
title: Frågor och svar om Adobe Target för mobilappar
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---


# Mål för mobilappar - frågor och svar

Lista med vanliga frågor om [!DNL Target] för mobilappar.

## Ska jag använda [!DNL Adobe Experience Platform Launch] för att distribuera SDK, eller kan jag distribuera SDK utan att använda [!DNL Launch]?

SDK är tillgängligt på [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Om du inte använder [Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html) måste du hantera din egen inställningsfil och hantera den i din app.

## Vilka SDK:er finns tillgängliga idag?

Adobe Experience Platform Mobile SDK:er har för närvarande stöd för iOS, Android och React. Mer information finns i [Adobe Experience Cloud Platform Mobile SDKs guide](https://aep-sdks.gitbook.io/docs/).

## Vilken frekvens har den platsbaserade funktionen för verifiering av latitud och longitud?

Mer information finns i [dokumentationen för Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/).

## Behöver jag at.js för att Adobe Experience Platform Mobile SDK ska fungera?

Nej, du behöver inte at.js för att använda SDK:n för mobilen. at.js är JavaScript-biblioteket [!DNL Target] för webbplatser. Adobe Experience Platform SDK för mobiler är till för mobilappar.

## Är Target Mobile bara en funktion i Adobe Target Premium Product SKU?

Nej. För [!DNL Adobe Target Standard]-kunder kan du endast använda våra SDK:er för A/B Test och Experience Targeting (XT) med [!DNL Target Standard]-tillägget för mobilappar. Om du vill använda Recommendations- eller AI-baserade funktioner i mobilappen behöver du en [Adobe Target Premium](/help/c-intro/intro.md#premium)-licens.

## Finns det någon mobilappsintegrering mellan mobilaktiviteterna Adobe Experience Manager (AEM) och Target?

Det står på vår färdplan, men det finns ingen tidslinje än. För närvarande kan du dela JSON [Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) från AEM till Target och det kan finnas en möjlighet att sedan använda dem i en mobilappsaktivitet.
