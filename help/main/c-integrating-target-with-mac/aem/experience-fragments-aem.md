---
keywords: upplevelse;json;aem;adobe experience manager;export till adobe target;experience fragments;fragments;XF
description: Lär dig använda [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] in [!DNL Adobe Target] verksamhet.
title: Hur jag använder [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments]?
feature: Integrations
source-git-commit: 47e1c7290011c21fd0710280d35c862a81b4f558
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# AEM [!UICONTROL Experience Fragments]

Använd [!UICONTROL Experience Fragments] (XF) skapade i [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] aktiviteter för att underlätta optimering och personalisering.

## Överväganden

Tänk på följande när du arbetar med AEM [!UICONTROL Experience Fragments] in [!DNL Target]:

* Den här funktionen kräver att du är en [!DNL Adobe Experience Manager] (AEM) kund. Mer information finns i [Krav](#section_AE6F0971E1574B3AA324003599B96E5A) nedan.
* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] är inte tillgängliga för följande aktivitetstyper:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Du kan konsumera [!UICONTROL Experience Fragments] in [!DNL Target] aktiviteter som använder [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) och [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

Mer information om AEM [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments], se [AEM [!UICONTROL Experience Fragments] och Översikt över innehållsfragment](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Krav {#requirements}

Du måste etableras med [!UICONTROL Experience Fragments] funktionalitet inom [!DNL Target]. Dessutom måste du använda [!DNL AEM] as a Cloud Service eller [!DNL AEM] 6.4 (eller senare). Din kontorepresentant kan se till att du uppfyller kraven för den här funktionen:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] eller [!DNL Adobe Target Premium] konto

[!DNL Adobe Experience Manager] 6.3 och 6.4 har nått slutet av livscykeln och stöds inte längre (förutom för kunder som köpt utökad support).

Kontakt [Adobe Target kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att aktivera integreringen och ge dig autentiseringsinformation.

## Skapa och konfigurera [!UICONTROL Experience Fragments] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

För att kunna använda [!DNL AEM] [!UICONTROL Experience Fragments] in [!DNL Target]måste du utföra följande steg:

### Steg 1: Integrera [!DNL AEM] med [!DNL Target]

Mer information finns i:

* **AEM as a Cloud Service**: [Integrera med Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} i *Experience Manager as a Cloud Service* guide.
* **Adobe I/O**: [Integrering med Adobe Target med Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank} i *Administrera användarhandbok* dokumentation.
* **[!DNL AEM]6.5**: [Gå med i Adobe Analytics och Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en){target=_blank} i *Adobe Experience Manager 6.5* dokumentation.
* **[!DNL AEM]6.4**: [Gå med i Adobe Analytics och Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank} i *Adobe Experience Manager 6.4* dokumentation.

### Steg 2: Skapa Experience Fragment

[!UICONTROL Experience Fragments] skapas i [!DNL AEM]. Mer information finns i:

* **AEM as a Cloud Service**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} i *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM]6.5**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en){target=_blank} i *Adobe Experience Manager 6.5* dokumentation.
* **[!DNL AEM]6.4**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en){target=_blank} i *Adobe Experience Manager 6.4* dokumentation.

### Steg 3: Konfigurera [!DNL AEM] för att dela [!UICONTROL Experience Fragment] med [!DNL Target]

1. Från [!DNL AEM]markerar du [!UICONTROL Experience Fragment] eller dess mapp klickar du på **[!UICONTROL Properties]**.
2. Klicka på **[!UICONTROL Cloud Services]** -fliken och sedan från **[!UICONTROL Cloud Service Configuration]** nedrullningsbar lista, välja **[!UICONTROL Adobe Target]**.

   I föregående steg förutsätts att någon i din organisation har skapat [!DNL Adobe Target] konfiguration.

3. Klicka på **[!UICONTROL Save & Close]**.

### Steg 4: Publicera [!UICONTROL Experience Fragment] och exportera till [!DNL Target]

Beroende på din [!DNL AEM] version, se följande länkar för stegvisa instruktioner:

* **AEM as a Cloud Service**: [Exporterar [!UICONTROL Experience Fragments] till Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} i *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM]6.5**: [Exportera ett Experience Fragment till Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} i *Adobe Experience Manager 6.5* dokumentation.
* **[!DNL AEM]6.4**: [Exportera ett Experience Fragment till Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank} i *Adobe Experience Manager 6.4* dokumentation.

## Använda [!UICONTROL Experience Fragments] in [!DNL Target] verksamhet {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

När du har utfört de föregående uppgifterna [!UICONTROL Experience Fragment] visas på [!UICONTROL Offers] sida in [!DNL Target].

[!DNL Target] söker för närvarande efter [!UICONTROL Experience Fragments] för att importera var tionde minut. Den importerade [!UICONTROL Experience Fragment] bör vara tillgänglig i [!DNL Target] inom tio minuter, men den här tidsramen bör korta av framåtgången.

The [!UICONTROL Experience Fragment] importeras till [!DNL Target] som ett HTML- eller JSON-erbjudande. The [!UICONTROL Experience Fragment] &quot;primär&quot; version finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Experience Fragment] in [!DNL Target].

Du kan filtrera och söka efter [!UICONTROL HTML XFs] och [!UICONTROL JSON XFs] för att hjälpa dig att skilja mellan [!UICONTROL Experience Fragment] typer som exporteras till [!DNL Target].

![Filtrera efter Experience Fragment-typer: HTML eller JSON i målgränssnittet](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Du kan hovra över en [!UICONTROL Experience Fragment] i listan och klickar sedan på [!UICONTROL View] icon ![Ikonen Info](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) om du vill ha mer information om [!UICONTROL Experience Fragment], inklusive [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path]och senaste ändringsinformation. Klicka på [!UICONTROL Offer Usage] om du vill se aktiviteterna som refererar till erbjudandet.

![Popup för information om Experience Fragment](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Du kan konsumera [!UICONTROL Experience Fragments] in [!DNL Target] aktiviteter som använder [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) och [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>Använd artificiell intelligens, maskininlärning och rekommendationer med [!UICONTROL Experience Fragments]:
>
>* Använd [!DNL Target] AI- och ML-funktionalitet kan du välja [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) när en aktivitet skapas.
>
>* [!UICONTROL Experience Fragments] stöds inte i [!DNL Recommendations] verksamhet. Använd [!UICONTROL Experience Fragments] för rekommendationer kan du skapa en [!UICONTROL A/B Test] aktivitet (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) eller en [!UICONTROL Experience Targeting] (XT) och [inkludera rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Förbruka [!UICONTROL Experience Fragments] med VEC:**

1. I [!DNL Target]när du skapar eller redigerar en upplevelse i [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)klickar du på den plats på sidan där du vill infoga [!DNL AEM] väljer du ett alternativ för att visa [!UICONTROL Choose an Experience Fragment] lista.

   * [!UICONTROL Insert Before]
   * [!UICONTROL Insert After]
   * [!UICONTROL Swap with Experience Fragment]

   The [!UICONTROL Experience Fragment] listan visar innehållet som skapats i [!DNL AEM] som nu är inbyggda i [!DNL Target].

   >[!NOTE]
   >
   >The [!UICONTROL Swap with Experience Fragment] är inte tillgängligt för bilder. Om du vill använda det här alternativet med en bild klickar du på behållarelementet som innehåller den önskade bilden.

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Markera önskat [!UICONTROL Experience Fragment]och sedan klicka **[!UICONTROL Done]**.
1. Slutför konfigurationen av aktiviteten.

   Mer information om hur du konfigurerar de olika aktivitetstyperna finns i följande avsnitt:

   * **A/B-test:** [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Automatisk fördelning:** [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Automatiskt mål:** [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):** [Skapa en Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Experience Targeting (XT):** [Skapa en upplevelseinriktad aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations i A/B Test eller XT:** [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Experience Fragments] exporterad som JSON i [!DNL Target] får inte användas i aktiviteter som skapats med VEC, endast HTML [!UICONTROL Experience Fragments] stöds i VEC-baserade aktiviteter. Om du vill använda JSON [!UICONTROL Experience Fragments], använda dem i aktiviteter som skapats med [Formulärbaserad upplevelsedisposition](/help/main/c-experiences/form-experience-composer.md).

**Förbruka [!UICONTROL Experience Fragments] med [!UICONTROL Form-based Experience Composer]:**

1. I [!DNL Target]när du skapar eller redigerar en upplevelse i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)väljer du den plats på sidan där du vill infoga [!DNL AEM] innehåll, markera **[!UICONTROL Change Experience Fragment]** för att visa [!UICONTROL Choose an Experience Fragment] lista.

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   The [!UICONTROL Experience Fragment] listan visar innehållet som skapats i [!DNL AEM] som nu är inbyggda i [!DNL Target].

1. Markera önskat [!UICONTROL Experience Fragment]och sedan klicka **[!UICONTROL Save]**.
1. Slutför konfigurationen av aktiviteten.

## Ytterligare information

* [!DNL Target] söker för närvarande efter [!UICONTROL Experience Fragments] för att importera var tionde minut. Den importerade [!UICONTROL Experience Fragment] bör vara tillgänglig i [!DNL Target] inom tio minuter, men den här tidsramen bör korta av framåtgången.
* The [!UICONTROL Experience Fragment] importeras till [!DNL Target] som ett HTML- eller JSON-erbjudande. The [!UICONTROL Experience Fragment] &quot;primär&quot; version finns kvar i [!DNL AEM]. Du kan inte redigera [!UICONTROL Experience Fragment] in [!DNL Target].
* Du kan inte skapa [!UICONTROL Experience Fragments] använda [!DNL Adobe I/O]. Skapa [!UICONTROL Experience Fragments] med hjälp av AEM, vilket förklaras ovan.
* Om du uppdaterar [!UICONTROL Experience Fragment] AEM [!UICONTROL Experience Fragment] måste publiceras och exporteras till [!DNL Target] igen så [!DNL Target] kan använda de senaste ändringarna.

## Ta bort ClientLibs och ovidkommande HTML från [!UICONTROL Experience Fragments] exporterat till [!UICONTROL Target]

När du använder [!UICONTROL Experience Fragment] erbjudanden med [!DNL Target] på en sida som levereras av AEM innehåller målsidan redan alla nödvändiga klientbibliotek. Observera också att det inte heller är nödvändigt att erbjuda ovidkommande HTML-element.

Ibland radbryts hela HTML-sidor [!UICONTROL Experience Fragment] och skapa problem. Se till att [!UICONTROL Experience Fragment] är en liten bit HTML och inte en hel HTML-sida med HTML, HEAD, BODY osv.

Mer information finns i följande blogginlägg: [AEM 6.5: Tar bort ClientLibs från [!UICONTROL Experience Fragments] exporterat till mål](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Utbildningsvideo: Använda AEM [!UICONTROL Experience Fragments] med [!DNL Adobe Target]

I följande video visas hur du konfigurerar och använder [!UICONTROL Experience Fragments]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>The [!DNL AEM] Funktionen för deplink, som diskuterades 4:54, har tagits bort.

Mer detaljerad information finns i [Använda [!UICONTROL Experience Fragments] med Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) på *AEM Sites Videos och Tutorials* sida.