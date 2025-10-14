---
keywords: upplevelse;json;aem;adobe experience manager;export till adobe target;content fragments;fragments;CF;cf;headless;personalization;experiment
description: Lär dig hur du använder  [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments] i [!DNL Adobe Target] aktiviteter.
title: Hur använder jag  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Content Fragments]?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: b29614680b27c9c33f11eed85d8ab4feebc28b0d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# AEM [!UICONTROL Content Fragments]

Använd [!UICONTROL Content Fragments] (CF) skapade i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target] aktiviteter för att underlätta headless-personalisering och -experimenterande.

## Överväganden

Tänk på följande när du arbetar med AEM [!UICONTROL Content Fragments] i [!DNL Target]:

* Den här funktionen kräver att du är en [!DNL Adobe Experience Manager as a Cloud Service]-kund. Mer information finns i [Krav](#section_AE6F0971E1574B3AA324003599B96E5A) nedan.
* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är inte tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Du kan endast använda [!UICONTROL Content Fragments] i [!DNL Target]-aktiviteter med [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). Du *kan inte* förbruka [!UICONTROL Content Fragments] i [!DNL Target] aktiviteter som använder [!UICONTROL Visual Experience Composer] (VEC).

Mer information om AEM [!UICONTROL Content Fragments] och [!UICONTROL Experience Fragments] finns i [&#x200B; AEM [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] översikt](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Krav {#requirements}

Du måste använda [[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=sv-SE){target=_blank}. Din kontorepresentant kan se till att du uppfyller kraven för den här funktionen:

Kontakta [Adobe Target kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du vill aktivera integreringen och ge dig autentiseringsinformation.

## Konfigurerar och arbetar med [!UICONTROL Content Fragments] i [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Om du vill exportera [!UICONTROL Content Fragments] för användning i [!DNL Target]-aktiviteter måste du utföra några preliminära steg i AEM. Mer information finns i [Exportera innehållsfragment till Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=sv-SE){target=_blank} i *Experience Manager as a Cloud Service-dokumentationen*.

Mer information om att utforma, skapa, strukturera och publicera [!UICONTROL Content Fragments] finns i [[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=sv-SE){target=_blank} och [Arbeta med innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=sv-SE){target=_blank} i [Experience Manager as a Cloud Service-dokumentationen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=sv-SE){target=_blank}.

## Använder [!UICONTROL Content Fragments] i [!DNL Target] aktiviteter {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

När du har utfört de föregående åtgärderna visas [!UICONTROL Content Fragment] på sidan [!UICONTROL Offers] i [!DNL Target].

[!DNL Target] söker för närvarande efter [!UICONTROL Content Fragments] att importera var tionde minut. Den importerade [!UICONTROL Content Fragment] bör vara tillgänglig om [!DNL Target] inom tio minuter, men den här tidsramen bör förkorta framtidens gång.

[!UICONTROL Content Fragment] importeras till [!DNL Target] som ett JSON-erbjudande. Den &quot;primära&quot; versionen [!UICONTROL Content Fragment] finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Content Fragment] i [!DNL Target].

Du kan filtrera och söka efter [!UICONTROL HTML XFs], [!UICONTROL JSON XFs] och [!UICONTROL Content Fragments] för att hjälpa dig att skilja mellan olika erbjudandetyper som exporteras till [!DNL Target].

![Filtrera efter innehållets fragmenttyper: HTML eller JSON i målgränssnittet](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Du kan hålla markören över [!UICONTROL Experience Fragment] i listan och sedan klicka på ikonen [!UICONTROL View] ![Info &#x200B;](/help/main/assets/icons/InfoOutline.svg) för att se ytterligare information om [!UICONTROL Content Fragment], inklusive dess [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path] och senaste ändringsinformation. Klicka på [!UICONTROL [!UICONTROL View Full Details]] om du vill se aktiviteterna som refererar till det här erbjudandet.

Du kan endast använda [!UICONTROL Content Fragments] i [!DNL Target]-aktiviteter med [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). Du *kan inte* förbruka [!UICONTROL Content Fragments] i [!DNL Target] aktiviteter med [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Content Fragments] exporteras som JSON i [!DNL Target] och kan inte användas i aktiviteter som skapats med VEC.

>[!TIP]
>
>Använd artificiell intelligens, maskininlärning och rekommendationer med [!UICONTROL Content Fragments]:
>
>* Om du vill använda AI- och ML-funktionerna i [!DNL Target] fullt ut kan du välja [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) när du skapar en [!UICONTROL A/B Test]-aktivitet.
>
>* [!UICONTROL Content Fragments] stöds inte i [!DNL Recommendations]-aktiviteter. Om du vill använda [!UICONTROL Content Fragments] som rekommendationer kan du skapa en [!UICONTROL A/B Test]-aktivitet (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) eller en [!UICONTROL Experience Targeting] (XT)-aktivitet och [ta med rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

**För att förbruka [!UICONTROL Content Fragments] med [!UICONTROL Form-based Experience Composer]:**

1. I [!DNL Target], när du skapar eller redigerar en upplevelse i [&#x200B; formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), markerar du den plats på sidan där du vill infoga [!DNL AEM]-innehåll och väljer sedan **[!UICONTROL Change Content Fragment]** för att visa listan [!UICONTROL Choose a Content Fragment].

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   Listan [!UICONTROL Content Fragment] visar innehållet som skapats i [!DNL AEM] och som nu är internt tillgängligt inifrån [!DNL Target].

1. Markera önskad [!UICONTROL Content Fragment] och klicka sedan på **[!UICONTROL Save]**.
1. Slutför konfigurationen av aktiviteten.

## Ytterligare information

* [!DNL Target] söker för närvarande efter [!UICONTROL Content Fragments] att importera var tionde minut. Den importerade [!UICONTROL Content Fragment] bör vara tillgänglig om [!DNL Target] inom tio minuter, men den här tidsramen bör förkorta framtidens gång.
* [!UICONTROL Content Fragment] importeras till [!DNL Target] som ett JSON-erbjudande. Den &quot;primära&quot; versionen [!UICONTROL Content Fragment] finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Content Fragment] i [!DNL Target].
* Du kan inte skapa [!UICONTROL Content Fragments] med [!DNL Adobe I/O]. Skapa [!UICONTROL Content Fragments] med AEM, enligt beskrivningen ovan.
* Om du uppdaterar [!UICONTROL Content Fragment] i AEM måste [!UICONTROL Content Fragment] publiceras och exporteras till [!DNL Target] igen så att [!DNL Target] kan använda de senaste ändringarna.
