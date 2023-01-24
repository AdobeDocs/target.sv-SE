---
keywords: upplevelse;json;aem;adobe experience manager;export till adobe target;experience fragments;fragments;XF
description: Lär dig använda [!DNL Adobe Experience Manager] upplevelsefragment i [!DNL Adobe Target] verksamhet.
title: Hur jag använder [!DNL Adobe Experience Manager] (AEM) Upplev fragment?
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 358b1d97ba6b9e6ffa276f096596d09d7197b82b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# AEM upplevelsefragment

Använd upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] aktiviteter för att underlätta optimering eller personalisering.

>[!NOTE]
>
>Den här funktionen kräver att du är en [!DNL Adobe Experience Manager] (AEM) kund. Mer information finns i [Krav](#section_AE6F0971E1574B3AA324003599B96E5A) nedan.

Använda upplevelsefragment som skapats i [!DNL AEM] in [!DNL Target] gör att du kan kombinera användarvänligheten och kraften i [!DNL AEM] med kraftfulla funktioner för artificiell intelligens (AI) och maskininlärning (ML) i [!DNL Target] att testa och personalisera upplevelser i stor skala.

[!DNL AEM] sammanför allt innehåll och alla resurser på en central plats för att understödja er personaliseringsstrategi. [!DNL AEM] gör att du enkelt kan skapa innehåll för datorer, surfplattor och mobila enheter på en plats utan att skriva kod. Du behöver inte skapa sidor för alla enheter. [!DNL AEM] anpassar automatiskt varje upplevelse med ditt innehåll.

[!DNL Target] Med kan ni leverera personaliserade upplevelser i stor skala baserat på en kombination av regelbaserade och AI-drivna maskininlärningsstrategier som innehåller beteendevariabler, sammanhangsbaserade variabler och offlinevariabler. Med [!DNL Target]kan du enkelt konfigurera och köra [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) och [Multivariat](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) för att fastställa de bästa erbjudandena, innehållet och upplevelserna.

Experience fragments utgör ett stort steg framåt för att länka samman innehållsskapare och ansvariga för upplevelser med optimerings- och personaliseringsproffs som driver affärsresultat med [!DNL Target].

## Krav {#section_AE6F0971E1574B3AA324003599B96E5A}

Du måste ha funktionerna för upplevelsefragment i [!DNL Target]. Dessutom måste du använda [!DNL AEM] as a Cloud Service eller [!DNL AEM] 6.4 (eller senare). Din kontorepresentant kan se till att du uppfyller kraven för den här funktionen:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* [!DNL Adobe Target Standard] eller [!DNL Adobe Target Premium] konto.

>[!NOTE]
>
>[!DNL Adobe Experience Manager] 6.3 och 6.4 har nått slutet av livscykeln och stöds inte längre (förutom för kunder som köpt utökad support).

Kontakt [Adobe Target kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att aktivera integreringen och ge dig autentiseringsinformation.

## Skapa och konfigurera upplevelsefragment i [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

För att kunna använda [!DNL AEM] upplevelsefragment i [!DNL Target]måste du utföra följande steg:

### Steg 1: Integrera [!DNL AEM] med [!DNL Target]

Mer information finns i:

* **AEM as a Cloud Service**: [Integrera med Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} i *Experience Manager as a Cloud Service* guide.
* **Adobe I/O**: [Integrering med Adobe Target med Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank} i *Administrera användarhandbok* dokumentation.
* **[!DNL AEM]6.5**: [Gå med i Adobe Analytics och Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en){target=_blank} i *Adobe Experience Manager 6.5* dokumentation.
* **[!DNL AEM]6.4**: [Gå med i Adobe Analytics och Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank} i *Adobe Experience Manager 6.4* dokumentation.

### Steg 2: Skapa upplevelsefragmentet

Upplevelsefragment skapas i [!DNL AEM]. Mer information finns i:

* **AEM as a Cloud Service**: [Upplevelsefragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} i *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM]6.5**: [Upplevelsefragment](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en){target=_blank} i *Adobe Experience Manager 6.5* dokumentation.
* **[!DNL AEM]6.4**: [Upplevelsefragment](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en){target=_blank} i *Adobe Experience Manager 6.4* dokumentation.

### Steg 3: Konfigurera [!DNL AEM] för att dela upplevelsefragment med [!DNL Target]

1. Från [!DNL AEM], väljer önskat upplevelsefragment eller dess mapp och klickar sedan på **[!UICONTROL Properties]**.
2. Klicka på **[!UICONTROL Cloud Services]** -fliken och sedan från **[!UICONTROL Cloud Service Configuration]** nedrullningsbar lista, välja **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >I föregående steg förutsätts att någon i din organisation har skapat [!DNL Adobe Target] konfiguration.

3. Klicka på **[!UICONTROL Save & Close]**.

### Steg 4: Publicera upplevelsefragmentet och exportera det till [!DNL Target]

Beroende på din [!DNL AEM] version, se följande länkar för stegvisa instruktioner:

* **AEM as a Cloud Service**: [Exportera Experience Fragments till Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} i *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM]6.5**: [Exportera ett Experience Fragment till Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} i *Adobe Experience Manager 6.5* dokumentation.
* **[!DNL AEM]6.4**: [Exportera ett Experience Fragment till Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank} i *Adobe Experience Manager 6.4* dokumentation.

## Använda upplevelsefragment i [!DNL Target] verksamhet {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

När du har utfört de föregående åtgärderna visas upplevelsefragmentet på [!UICONTROL Offers] sida in [!DNL Target].

>[!NOTE]
>
>* [!DNL Target] letar efter upplevelsefragment som ska importeras var tionde minut. Det importerade upplevelsefragmentet ska vara tillgängligt i [!DNL Target] inom tio minuter, men den här tidsramen bör korta av framåtgången.
>
>* Upplevelsefragmentet importeras till [!DNL Target] som ett HTML- eller JSON-erbjudande. Den&quot;primära&quot; versionen av upplevelsefragmentet finns kvar i [!DNL AEM]. Du kan inte redigera upplevelsefragmentet i [!DNL Target].


Du kan filtrera och söka efter [!UICONTROL HTML XF] och [!UICONTROL JSON XF] som hjälper dig att skilja mellan upplevelsefragmenttyper som exporteras till [!DNL Target].

Du kan hovra över ett upplevelsefragment i listan och sedan klicka på [!UICONTROL View] icon ![Ikonen Visa](assets/icon_info.png) för att få mer information om upplevelsefragmentet, inklusive dess URL för offentlig leverans och dess [!DNL AEM] bana.

Du kan förbruka upplevelsefragment i [!DNL Target] aktiviteter som använder [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) eller [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Använd [!DNL Target] AI- och ML-funktionalitet kan du välja [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) när ett A/B-test skapades.
>
>Experience fragments stöds inte i [!DNL Recommendations] verksamhet. Men om du vill använda upplevelsefragment för rekommendationer kan du skapa en [!UICONTROL A/B Test] aktivitet (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) eller en [!UICONTROL Experience Targeting] (XT) och [inkludera rekommendationer som ett erbjudande](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

**Så här använder du upplevelsefragment med VEC:**

1. I [!DNL Target]när du skapar eller redigerar en upplevelse i [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)klickar du på den plats på sidan där du vill infoga [!DNL AEM] väljer du ett alternativ för att visa [!UICONTROL Choose an Experience Fragment] lista.

   * [!UICONTROL Insert Before]
   * [!UICONTROL Insert After]
   * [!UICONTROL Swap with Experience Fragment]

   The [!UICONTROL Experience Fragment] listan visar innehållet som skapats i [!DNL AEM] som nu är inbyggda i [!DNL Target].

   >[!NOTE]
   >
   >The [!UICONTROL Swap with Experience Fragment] är inte tillgängligt för bilder. Om du vill använda det här alternativet med en bild klickar du på behållarelementet som innehåller den önskade bilden.

   ![experience_fragment_list image](assets/experience_fragment_list.png)

1. Välj önskat upplevelsefragment och klicka sedan på **[!UICONTROL Done]**.
1. Slutför konfigurationen av aktiviteten.

   Mer information om hur du konfigurerar de olika aktivitetstyperna finns i följande avsnitt:

   * **A/B-test:** [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Automatisk fördelning:** [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Automatiskt mål:** [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):** [Skapa en Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Experience Targeting (XT):** [Skapa en upplevelseinriktad aktivitet](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Multivariata tester (MVT):** [Skapa ett multivariata test](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Skapa en Recommendations-aktivitet](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

>[!NOTE]
>
>Upplev fragment som exporterats som JSON i [!DNL Target] får inte användas i aktiviteter som skapats med VEC, endast HTML-upplevelsefragment stöds i VEC-baserade aktiviteter. Om du vill använda JSON-upplevelsefragment kan du använda dem i aktiviteter som skapats med [Formulärbaserad upplevelsedisposition](/help/main/c-experiences/form-experience-composer.md).

**Så här använder du upplevelsefragment med den formulärbaserade Experience Composer:**

1. I [!DNL Target]när du skapar eller redigerar en upplevelse i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)väljer du den plats på sidan där du vill infoga [!DNL AEM] innehåll, markera **[!UICONTROL Change Experience Fragment]** för att visa [!UICONTROL Choose an Experience Fragment] lista.

   ![experience_fragment_list image](assets/experience_fragment_list.png)

   The [!UICONTROL Experience Fragment] listan visar innehållet som skapats i [!DNL AEM] som nu är inbyggda i [!DNL Target].

1. Välj önskat upplevelsefragment och klicka sedan på **[!UICONTROL Save]**.
1. Slutför konfigurationen av aktiviteten.

## Överväganden {#considerations}

* [!DNL Target] letar efter upplevelsefragment som ska importeras var tionde minut. Det importerade upplevelsefragmentet ska vara tillgängligt i [!DNL Target] inom tio minuter, men den här tidsramen bör korta av framåtgången.
* Upplevelsefragmentet importeras till [!DNL Target] som ett HTML- eller JSON-erbjudande. Den primära versionen av upplevelsefragmentet finns kvar i [!DNL AEM]. Du kan inte redigera upplevelsefragmentet i [!DNL Target].
* Du kan inte skapa upplevelsefragment med [!DNL Adobe I/O]. Skapa upplevelsefragment med hjälp av AEM, vilket förklaras ovan.
* Om du uppdaterar ditt upplevelsefragment i AEM måste upplevelsefragmentet publiceras och exporteras till [!DNL Target] igen så [!DNL Target] kan använda de senaste ändringarna.

## Ta bort ClientLibs och ovidkommande HTML från Experience Fragments som exporterats till Target

När upplevelsefragment erbjuder med [!DNL Target] på en sida som levereras av AEM innehåller målsidan redan alla nödvändiga klientbibliotek. Observera också att det inte heller är nödvändigt att erbjuda ovidkommande HTML-element.

Ibland kan hela HTML-sidor omsluta upplevelsefragmentet och orsaka problem. Se till att upplevelsefragmentet är en liten bit HTML och inte en hel HTML-sida med HTML, HEAD, BODY osv.

Mer information finns i följande blogginlägg: [AEM 6.5: Ta bort ClientLibs från Experience Fragments som exporterats till Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Utbildningsvideo: Använda AEM upplevelsefragment med [!DNL Adobe Target]

I följande video visas hur du konfigurerar och använder upplevelsefragment:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>The [!DNL AEM] Funktionen för deplink, som diskuterades 4:54, har tagits bort.

Mer detaljerad information finns i [Använda Experience Fragments med Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) på *AEM Sites Videos och Tutorials* sida.
