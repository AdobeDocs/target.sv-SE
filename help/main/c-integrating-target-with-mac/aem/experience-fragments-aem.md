---
keywords: upplevelse;json;aem;adobe experience manager;export till adobe target;experience fragments;fragments;XF
description: Lär dig hur du använder  [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] i [!DNL Adobe Target] aktiviteter.
title: Hur använder jag  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments]?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 0%

---

# AEM [!UICONTROL Experience Fragments]

Använd [!UICONTROL Experience Fragments] (XF) skapade i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target] aktiviteter för att underlätta optimering och personalisering.

## Överväganden

Tänk på följande när du arbetar med AEM [!UICONTROL Experience Fragments] i [!DNL Target]:

* Den här funktionen kräver att du är en [!DNL Adobe Experience Manager]-kund (AEM). Mer information finns i [Krav](#section_AE6F0971E1574B3AA324003599B96E5A) nedan.
* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är inte tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Du kan använda [!UICONTROL Experience Fragments] i [!DNL Target]-aktiviteter med [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) och [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

Mer information om AEM [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] finns i [AEM [!UICONTROL Experience Fragments] och Översikt över innehållsfragment](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Krav {#requirements}

Du måste ha tillgång till funktionen [!UICONTROL Experience Fragments] i [!DNL Target]. Dessutom måste du använda [!DNL AEM] as a Cloud Service eller [!DNL AEM] 6.4 (eller senare). Din kontorepresentant kan se till att du uppfyller kraven för den här funktionen:

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] eller [!DNL Adobe Target Premium]-konto

[!DNL Adobe Experience Manager] 6.3 och 6.4 har nått slutet av livscykeln och stöds inte längre (förutom för kunder som köpt utökad support).

Kontakta [Adobe Target kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du vill aktivera integreringen och ge dig autentiseringsinformation.

## Skapar och konfigurerar [!UICONTROL Experience Fragments] i [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Om du vill använda [!DNL AEM] [!UICONTROL Experience Fragments] i [!DNL Target] måste du utföra följande steg:

### Steg 1: Integrera [!DNL AEM] med [!DNL Target]

Mer information finns i:

* **AEM as a Cloud Service**: [Integrera med Adobe Target](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} i guiden för *Experience Manager as a Cloud Service*.
* **Adobe Developer**: [Integrering med Adobe Target med Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html?lang=sv-SE){target=_blank} i *dokumentationen för användarhandboken*.
* **[!DNL AEM]6.5**: [Gå med i Adobe Analytics och Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=sv-SE){target=_blank} i dokumentationen för *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Gå med i Adobe Analytics och Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=sv-SE){target=_blank} i dokumentationen för *Adobe Experience Manager 6.4*.

### Steg 2: Skapa upplevelsefragmentet

[!UICONTROL Experience Fragments] skapas i [!DNL AEM]. Mer information finns i:

* **AEM as a Cloud Service**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=sv-SE){target=_blank} i guiden för *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=sv-SE){target=_blank} i *Adobe Experience Manager 6.5* -dokumentationen.
* **[!DNL AEM]6.4**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=sv-SE){target=_blank} i *Adobe Experience Manager 6.4* -dokumentationen.

### Steg 3: Konfigurera [!DNL AEM] för att dela [!UICONTROL Experience Fragment] med [!DNL Target]

1. I [!DNL AEM] markerar du önskad [!UICONTROL Experience Fragment] eller dess mapp och klickar sedan på **[!UICONTROL Properties]**.
2. Klicka på fliken **[!UICONTROL Cloud Services]** och välj sedan **[!UICONTROL Cloud Service Configuration]** i listrutan **[!UICONTROL Adobe Target]**.

   I föregående steg förutsätts att någon i din organisation har skapat konfigurationen [!DNL Adobe Target].

3. Klicka på **[!UICONTROL Save & Close]**.

### Steg 4: Publicera [!UICONTROL Experience Fragment] och exportera den till [!DNL Target]

Beroende på din [!DNL AEM]-version kan du läsa följande länkar för steg-för-steg-instruktioner:

* **AEM as a Cloud Service**: [Exporterar [!UICONTROL Experience Fragments] till Adobe Target](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank} i guiden för *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [Exporterar en Experience Fragment till Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=sv-SE){target=_blank} i *Adobe Experience Manager 6.5* -dokumentationen.
* **[!DNL AEM]6.4**: [Exporterar en Experience Fragment till Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=sv-SE){target=_blank} i *Adobe Experience Manager 6.4* -dokumentationen.

## Använder [!UICONTROL Experience Fragments] i [!DNL Target] aktiviteter {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

När du har utfört de föregående åtgärderna visas [!UICONTROL Experience Fragment] på sidan [!UICONTROL Offers] i [!DNL Target].

[!DNL Target] söker för närvarande efter [!UICONTROL Experience Fragments] att importera var tionde minut. Den importerade [!UICONTROL Experience Fragment] bör vara tillgänglig om [!DNL Target] inom tio minuter, men den här tidsramen bör förkorta framtidens gång.

[!UICONTROL Experience Fragment] importeras till [!DNL Target] som ett HTML- eller JSON-erbjudande. Den &quot;primära&quot; versionen [!UICONTROL Experience Fragment] finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Experience Fragment] i [!DNL Target].

Du kan filtrera och söka efter [!UICONTROL HTML XFs] och [!UICONTROL JSON XFs] för att hjälpa dig att skilja mellan [!UICONTROL Experience Fragment] typer som exporteras till [!DNL Target].

![Filtrera efter Experience Fragment-typer: HTML eller JSON i målgränssnittet](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Du kan hålla markören över [!UICONTROL Experience Fragment] i listan och sedan klicka på ikonen [!UICONTROL View] ![Info &#x200B;](/help/main/assets/icons/InfoOutline.svg) för att se ytterligare information om [!UICONTROL Experience Fragment], inklusive dess [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path] och senaste ändringsinformation. Klicka på [!UICONTROL [!UICONTROL View Full Details]] om du vill se aktiviteterna som refererar till det här erbjudandet.

![Popup för information om Experience Fragment](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Du kan använda [!UICONTROL Experience Fragments] i [!DNL Target]-aktiviteter med [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) och [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

>[!TIP]
>
>Använd artificiell intelligens, maskininlärning och rekommendationer med [!UICONTROL Experience Fragments]:
>
>* Om du vill använda AI- och ML-funktionerna i [!DNL Target] fullt ut kan du välja [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) när du skapar en aktivitet.
>
>* [!UICONTROL Experience Fragments] stöds inte i [!DNL Recommendations]-aktiviteter. Om du vill använda [!UICONTROL Experience Fragments] som rekommendationer kan du skapa en [!UICONTROL A/B Test]-aktivitet (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) eller en [!UICONTROL Experience Targeting] (XT)-aktivitet och [ta med rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

**För att använda [!UICONTROL Experience Fragments] med VEC:**

1. I [!DNL Target], när du skapar eller redigerar en upplevelse i [&#x200B; Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), klickar du på den plats på sidan där du vill infoga [!DNL AEM]-innehåll och sedan på **[!UICONTROL Replace Content]** > **[!UICONTROL Experience Fragment]** för att visa dialogrutan [!UICONTROL Experience Fragment].

   I dialogrutan [!UICONTROL Experience Fragment] visas innehållet som skapats i [!DNL AEM] och som nu är internt tillgängligt inifrån [!DNL Target].

   >[!NOTE]
   >
   >Alternativet [!UICONTROL Replace Content] är inte tillgängligt för bilder. Om du vill använda det här alternativet med en bild klickar du på behållarelementet som innehåller den önskade bilden.

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Markera önskad [!UICONTROL Experience Fragment] och klicka sedan på **[!UICONTROL Add]**.
1. Slutför konfigurationen av aktiviteten.

   Mer information om hur du konfigurerar de olika aktivitetstyperna finns i följande avsnitt:

   * **A/B-test:** [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Automatisk allokering:** [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Automatiskt mål:** [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):** [Skapa en Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Experience Targeting (XT):** [Skapa en Experience Targeting-aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Rekommendationer i A/B-test eller XT-aktivitet:** [Rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Experience Fragments] som exporterats som JSON i [!DNL Target] kan inte användas i aktiviteter som skapats med VEC. Endast HTML [!UICONTROL Experience Fragments] stöds i VEC-baserade aktiviteter. Om du vill använda JSON [!UICONTROL Experience Fragments] använder du dem i aktiviteter som skapats med [formulärbaserad upplevelsedisposition](/help/main/c-experiences/form-experience-composer.md).

**För att förbruka [!UICONTROL Experience Fragments] med [!UICONTROL Form-based Experience Composer]:**

1. I [!DNL Target], när du skapar eller redigerar en upplevelse i [&#x200B; formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), väljer du den plats på sidan där du vill infoga [!DNL AEM]-innehåll, klickar på ikonen **[!UICONTROL More Details]** ( ![Mer information &#x200B;](/help/main/assets/icons/MoreSmall.svg) ) och väljer sedan **[!UICONTROL Change Experience Fragment]** för att visa dialogrutan [!UICONTROL Change Experience Fragment].

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   I dialogrutan [!UICONTROL Experience Fragment] visas innehållet som skapats i [!DNL AEM] och som nu är internt tillgängligt inifrån [!DNL Target].

1. Markera önskad [!UICONTROL Experience Fragment] och klicka sedan på **[!UICONTROL Add]**.
1. Slutför konfigurationen av aktiviteten.

## Ytterligare information

* [!DNL Target] söker för närvarande efter [!UICONTROL Experience Fragments] att importera var tionde minut. Den importerade [!UICONTROL Experience Fragment] bör vara tillgänglig om [!DNL Target] inom tio minuter, men den här tidsramen bör förkorta framtidens gång.
* [!UICONTROL Experience Fragment] importeras till [!DNL Target] som ett HTML- eller JSON-erbjudande. Den &quot;primära&quot; versionen [!UICONTROL Experience Fragment] finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Experience Fragment] i [!DNL Target].
* Du kan inte skapa [!UICONTROL Experience Fragments] med [!DNL Adobe Developer]. Skapa [!UICONTROL Experience Fragments] med AEM, enligt beskrivningen ovan.
* Om du uppdaterar [!UICONTROL Experience Fragment] i AEM måste [!UICONTROL Experience Fragment] publiceras och exporteras till [!DNL Target] igen så att [!DNL Target] kan använda de senaste ändringarna.

## Tar bort klientlibs och överflödiga HTML från [!UICONTROL Experience Fragments] som exporterats till [!UICONTROL Target]

När du använder [!UICONTROL Experience Fragment] erbjudanden med [!DNL Target] på en sida som levereras av AEM innehåller målsidan redan nödvändiga klientbibliotek. Observera också att det inte heller behövs några ovidkommande HTML-element i erbjudandet.

Ibland kapslar hela HTML-sidor in [!UICONTROL Experience Fragment] och orsakar problem. Kontrollera att [!UICONTROL Experience Fragment] är en liten del av HTML och inte en fullständig HTML-sida med HTML, HEAD, BODY osv.

Mer information finns i följande blogginlägg: [AEM 6.5: Ta bort clientlibs från [!UICONTROL Experience Fragments] exporterade till Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser/){target=_blank}.

## Utbildningsvideo: Använda AEM [!UICONTROL Experience Fragments] med [!DNL Adobe Target]

I följande video visas hur du konfigurerar och använder [!UICONTROL Experience Fragments]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Funktionen [!DNL AEM] för deplink som diskuterades vid 4:54 har tagits bort.

Mer detaljerad information finns i [Använda [!UICONTROL Experience Fragments] med Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=sv-SE) på sidan *AEM Sites videor och självstudiekurser*.
