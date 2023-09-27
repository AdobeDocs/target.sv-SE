---
keywords: multivariat test;mvt;mvt plan;multivariate test plan
description: Lär dig planera en [!UICONTROL Multivariate Test] in [!DNL Adobe Target] så att du kan skapa ett lyckat test.
title: Hur planerar jag en [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---

# Planera en [!UICONTROL Multivariate Test]

[!UICONTROL Multivariate Tests] MVT-verksamhet [!DNL Adobe Target] kräver lite planering innan du kan skapa ett lyckat test.

MVT kräver tillräcklig trafik för att generera användbara resultat. Innan du konfigurerar testet bör du vara medveten om hur mycket trafik du normalt får, inklusive antalet visningar och konverteringar. Om du har den här informationen minskar du risken att skapa ett test med krav som överskrider webbplatsens trafik.

Elementen ska vara oberoende av varandra. Testa till exempel inte layouten och innehållet i samma test.

Undersök HTML-koden för de sidor som du vill testa. Se till att elementen i HTML på din webbplats inte har dubbla DOM ID:n. Duplicerade ID:n kan leda till att samma innehåll levereras till mer än en plats.

Planera att testa de element på sidan som kan ge betydande resultat. En banderoll eller en hjältebild kommer till exempel att leda till fler konverteringar än en sidfotsändring. Om du tar med mindre inflytelserika element i testet ökar bara mängden trafik och den tid som krävs för att testa de mer framträdande elementen på sidan.

Innan du skapar testet bör du skapa det innehåll du vill testa. Förstå skillnaderna i innehåll för varje erbjudande och skapa bilder, text och HTML som du förväntar dig att använda i testet.

## Utbildningsvideo: Skapa multivariata tester (9:25) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon visas hur du planerar och skapar ett multivariata test med [!DNL Target] guidat arbetsflöde i tre steg.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
