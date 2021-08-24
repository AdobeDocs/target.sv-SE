---
keywords: mobilapp;vanliga frågor;faq;target mobile app
description: Visa vanliga frågor och svar om Adobe [!DNL Target] för mobilappar.
title: Vilka är vanliga frågor om [!DNL Target] mobilappar?
feature: Implementera mobil
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# Mål för mobilappar - frågor och svar

Lista med vanliga frågor om [!DNL Target] för mobilappar.

## Ska jag använda taggar i [!DNL Adobe Experience Platform] för att distribuera SDK, eller kan jag distribuera SDK utan att använda [!DNL Launch]?

SDK är tillgängligt på [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Om du inte använder [taggar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) måste du hantera din egen inställningsfil och hantera den i din app.

## Vilka SDK:er finns tillgängliga idag?

Adobe Experience Platform Mobile SDK:er har för närvarande stöd för iOS, Android och React. Mer information finns i [Adobe Experience Cloud Platform Mobile SDKs guide](https://aep-sdks.gitbook.io/docs/).

## Vilken frekvens har den platsbaserade funktionen för verifiering av latitud och longitud?

Mer information finns i [dokumentationen för Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/).

## Behöver jag at.js för att Adobe Experience Platform Mobile SDK ska fungera?

Nej, du behöver inte at.js för att använda SDK:n för mobilen. at.js är JavaScript-biblioteket [!DNL Target] för webbplatser. Adobe Experience Platform SDK för mobiler är till för mobilappar.

## Är [!DNL Target] Mobile endast en funktion i Adobe [!DNL Target] Premium Product SKU?

Nej. För [!DNL Adobe Target Standard]-kunder kan du endast använda våra SDK:er för A/B Test och Experience Targeting (XT) med [!DNL Target Standard]-tillägget för mobilappar. Om du vill använda Recommendations- eller AI-baserade funktioner i mobilappen behöver du en [Adobe Target Premium](/help/c-intro/intro.md#premium)-licens.

## Finns det någon mobilappsintegrering mellan Adobe Experience Manager (AEM) och [!DNL Target] mobilaktiviteter?

Det står på vår färdplan, men det finns ingen tidslinje än. För närvarande kan du dela JSON [Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) från AEM till Target och det kan finnas en möjlighet att sedan använda dem i en mobilappsaktivitet.
