---
keywords: multivariate test;mvt;mvt plan;multivariate test plan
description: Multivariata tester i Adobe Target kräver viss planering innan du kan skapa ett lyckat test.
title: Planera ett multivariata test i Adobe Target
feature: mvt
uuid: f286d08a-e11d-4a39-8c62-3eba99885299
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---


# Planera ett multivariata test{#plan-a-multivariate-test}

[!UICONTROL Multivariate Tests] (MVT) i [!DNL Adobe Target] kräver lite planering innan du kan skapa ett lyckat test.

MVT kräver tillräcklig trafik för att generera användbara resultat. Innan du konfigurerar testet bör du vara medveten om hur mycket trafik du normalt får, inklusive antalet visningar och konverteringar. Om du har den här informationen minskar risken för att du utformar ett test med krav som överskrider webbplatsens trafik.

Vi rekommenderar att elementen är oberoende av varandra. (Testa till exempel inte layouten och innehållet i samma test.)

Undersök HTML-koden för de sidor som du vill testa. Kontrollera att HTML-elementen på din webbplats inte har dubbla DOM ID:n. Duplicerade ID:n kan leda till att samma innehåll levereras till mer än en plats.

Planera att testa de element på sidan som kan ge betydande resultat. En banderoll eller en hjältebild kommer till exempel att leda till fler konverteringar än en sidfotsändring. Om du tar med mindre inflytelserika element i testet ökar bara mängden trafik och den tid som krävs för att testa de mer framträdande elementen på sidan.

Innan du skapar testet bör du skapa det innehåll du vill testa. Förstå skillnaderna i innehåll för varje erbjudande och skapa bilder, text och HTML-erbjudanden som du förväntar dig att använda i testet.

## Utbildningsvideo: Skapa multivariata tester (9:25) ![självstudiemärke](/help/assets/tutorial.png)

I den här videon visas hur du planerar och skapar ett multivariata test med hjälp av det guidade arbetsflödet i tre steg för Target.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)