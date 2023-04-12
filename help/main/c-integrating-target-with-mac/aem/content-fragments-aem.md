---
keywords: upplevelse;json;aem;adobe experience manager;export till adobe target;content fragments;fragments;CF;cf;headless;personalization;experiment
description: Lär dig använda [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments] in [!DNL Adobe Target] verksamhet.
title: Hur jag använder [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Content Fragments]?
badgePrerelease: label="Prerelease"
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: e30c87476496f6103790dbb2fa0c3d60e4c26572
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# AEM [!UICONTROL Content Fragments]

Använd [!UICONTROL Content Fragments] (CF) skapad i [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] aktiviteter för att underlätta personalisering och experimenterande utan motstycke.

>[!NOTE]
>
>Den här funktionen är tillgänglig som en förhandsversion den 12 april 2023. Som en förhandsversion kan du experimentera med [!UICONTROL Content Fragments] i dev- och staging-miljöer, men inte i produktionsmiljöer.
>
>Den här funktionen kommer att vara tillgänglig för GA-versionen (General Availability) den 26 april 2023.

## Överväganden

Tänk på följande när du arbetar med AEM [!UICONTROL Content Fragments] in [!DNL Target]:

* Den här funktionen kräver att du är en [!DNL Adobe Experience Manager as a Cloud Service] kund. Mer information finns i [Krav](#section_AE6F0971E1574B3AA324003599B96E5A) nedan.
* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är inte tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Du kan konsumera [!UICONTROL Content Fragments] in [!DNL Target] aktiviteter som använder [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) endast. Du *inte* förbruka [!UICONTROL Content Fragments] in [!DNL Target] aktiviteter som använder [!UICONTROL Visual Experience Composer] (VEC).

Mer information om AEM [!UICONTROL Content Fragments] och [!UICONTROL Experience Fragments], se [AEM [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] översikt](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Krav {#requirements}

Du måste etableras med [!UICONTROL Content Fragments] funktionalitet inom [!DNL Target]. Dessutom måste du använda [[!DNL AEM] as a Cloud Service](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}. Din kontorepresentant kan se till att du uppfyller kraven för den här funktionen:

Kontakt [Adobe Target kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att aktivera integreringen och ge dig autentiseringsinformation.

## Konfigurera och arbeta med [!UICONTROL Content Fragments] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Exportera [!UICONTROL Content Fragments] att använda i [!DNL Target] -aktiviteter måste du utföra några preliminära steg i AEM. Mer information finns i [Exportera innehållsfragment till Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} i *as a Cloud Service dokumentation för Experience Manager*.

Mer information om att designa, skapa, strukturera och publicera [!UICONTROL Content Fragments], se [[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=en){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

## Använda [!UICONTROL Content Fragments] in [!DNL Target] verksamhet {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

När du har utfört de föregående uppgifterna [!UICONTROL Content Fragment] visas på [!UICONTROL Offers] sida in [!DNL Target].

[!DNL Target] söker för närvarande efter [!UICONTROL Content Fragments] för att importera var tionde minut. Den importerade [!UICONTROL Content Fragment] bör vara tillgänglig i [!DNL Target] inom tio minuter, men den här tidsramen bör korta av framåtgången.

The [!UICONTROL Content Fragment] importeras till [!DNL Target] som ett JSON-erbjudande. The [!UICONTROL Content Fragment] &quot;primär&quot; version finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Content Fragment] in [!DNL Target].

Du kan filtrera och söka efter [!UICONTROL HTML XFs], [!UICONTROL JSON XFs]och [!UICONTROL Content Fragments] för att hjälpa dig att skilja mellan olika erbjudandetyper som exporteras till [!DNL Target].

![Filtrera efter innehållets fragmenttyper: HTML eller JSON i målgränssnittet](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Du kan hovra över en [!UICONTROL Content Fragment] i listan och klickar sedan på [!UICONTROL View] icon ![Ikonen Info](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) om du vill ha mer information om [!UICONTROL Content Fragment], inklusive [!UICONTROL AEM path] och [!UICONTROL AEM deep link]. Klicka på [!UICONTROL Offer Usage] om du vill se aktiviteterna som refererar till erbjudandet.

![Popup för information om innehållsfragment](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Du kan konsumera [!UICONTROL Content Fragments] in [!DNL Target] aktiviteter som använder [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) endast. Du *inte* förbruka [!UICONTROL Content Fragments] in [!DNL Target] aktiviteter som använder [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Content Fragments] exporteras som JSON i [!DNL Target] och kan inte användas i aktiviteter som skapats med VEC.

>[!TIP]
>
>Använd artificiell intelligens, maskininlärning och rekommendationer med [!UICONTROL Content Fragments]:
>
>* Använd [!DNL Target] AI- och ML-funktionalitet kan du välja [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) när en [!UICONTROL A/B Test] aktivitet.
>
>* [!UICONTROL Content Fragments] stöds inte i [!DNL Recommendations] verksamhet. Använd [!UICONTROL Content Fragments] för rekommendationer kan du skapa en [!UICONTROL A/B Test] aktivitet (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) eller en [!UICONTROL Experience Targeting] (XT) och [inkludera rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Förbruka [!UICONTROL Content Fragments] med [!UICONTROL Form-based Experience Composer]:**

1. I [!DNL Target]när du skapar eller redigerar en upplevelse i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)väljer du den plats på sidan där du vill infoga [!DNL AEM] innehåll, markera **[!UICONTROL Change Content Fragment]** för att visa [!UICONTROL Choose a Content Fragment] lista.

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   The [!UICONTROL Content Fragment] listan visar innehållet som skapats i [!DNL AEM] som nu är inbyggda i [!DNL Target].

1. Markera önskat [!UICONTROL Content Fragment]och sedan klicka **[!UICONTROL Save]**.
1. Slutför konfigurationen av aktiviteten.

## Ytterligare information

* [!DNL Target] söker för närvarande efter [!UICONTROL Content Fragments] för att importera var tionde minut. Den importerade [!UICONTROL Content Fragment] bör vara tillgänglig i [!DNL Target] inom tio minuter, men den här tidsramen bör korta av framåtgången.
* The [!UICONTROL Content Fragment] importeras till [!DNL Target] som ett JSON-erbjudande. The [!UICONTROL Content Fragment] &quot;primär&quot; version finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Content Fragment] in [!DNL Target].
* Du kan inte skapa [!UICONTROL Content Fragments] använda [!DNL Adobe I/O]. Skapa [!UICONTROL Content Fragments] med hjälp av AEM, vilket förklaras ovan.
* Om du uppdaterar [!UICONTROL Content Fragment] AEM [!UICONTROL Content Fragment] måste publiceras och exporteras till [!DNL Target] igen så [!DNL Target] kan använda de senaste ändringarna.
