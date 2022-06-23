---
keywords: mobilapp;vanliga frågor;faq;target mobile app
description: Visa vanliga frågor och svar om Adobe [!DNL Target] för mobilappar.
title: Vad ställs vanliga frågor om [!DNL Target] för mobilappar?
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Mål för mobilappar - frågor och svar

Lista med vanliga frågor om [!DNL Target] för mobilappar.

## Bör jag använda taggar i [!DNL Adobe Experience Platform] för att distribuera SDK, eller kan jag distribuera SDK utan att använda [!DNL Launch]?

SDK finns på [Adobe Marketing Cloud Git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Om du inte använder [taggar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)måste du hantera din egen inställningsfil och hantera den i din app.

## Vilka SDK:er finns tillgängliga idag?

Adobe Experience Platform Mobile SDK:er har för närvarande stöd för iOS, Android och React. Mer information finns i [Adobe Experience Cloud Platform Mobile SDKs guide](https://aep-sdks.gitbook.io/docs/).

## Vilken frekvens har den platsbaserade funktionen för verifiering av latitud och longitud?

Se [Dokumentation för Adobe Platser Service](https://experienceleague.adobe.com/docs/places/using/home.html) för mer information.

## Behöver jag at.js för att Adobe Experience Platform Mobile SDK ska fungera?

Nej, du behöver inte at.js för att använda SDK:n för mobilen. at.js är [!DNL Target] JavaScript-bibliotek för webbplatser. Adobe Experience Platform SDK för mobiler är till för mobilappar.

## Är [!DNL Target] Mobil en funktion i Adobe [!DNL Target] Premium Product SKU only?

Nej. För [!DNL Adobe Target Standard] -kunder kan du bara använda våra mobila SDK:er för A/B Test- och Experience Targeting-aktiviteter (XT) med [!DNL Target Standard] Mobilappstillägg. Om du vill använda Recommendations- eller AI-baserade funktioner i mobilappen behöver du en [Adobe Target Premium](/help/main/c-intro/intro.md#premium) licens.

## Finns det någon mobilappsintegrering mellan Adobe Experience Manager (AEM) och [!DNL Target] mobilaktiviteter?

Det står på vår färdplan, men det finns ingen tidslinje än. För närvarande kan du dela JSON [Upplevelsefragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) från AEM till Target och det kan finnas en möjlighet att sedan använda dem i en mobilappsaktivitet.
