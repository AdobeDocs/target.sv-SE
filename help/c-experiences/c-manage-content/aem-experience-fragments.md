---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: Information om hur du använder upplevelsefragment som skapats i Adobe Experience Manager (AEM) i Adobe Target-aktiviteter för att underlätta optimering eller personalisering.
title: Adobe Experience Manager (AEM) Experience fragments in Adobe Target
feature: aem
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 6278a01928fcb9dd0b34d7a8b5313f09f1e8da0f
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 0%

---


# AEM upplevelsefragment{#aem-experience-fragments}

Information om hur du använder upplevelsefragment som skapats i [!DNL Adobe Experience Manager] (AEM) i [!DNL Target] aktiviteter för att underlätta optimering eller personalisering.

>[!NOTE]
>
>Den här funktionen kräver att du är en [!DNL Adobe Experience Manager] ([!DNL AEM]) kund. Mer information finns i [Krav](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)nedan.

## Översikt {#section_95A91830530F493B81C5C9CDB9B783EA}

Genom att använda upplevelsefragment som skapats i [!DNL AEM] aktiviteter kan ni kombinera användarvänligheten och kraften i [!DNL Target] med kraftfulla funktioner för automatiserad intelligens (AI) och maskininlärning (ML) i [!DNL AEM] [!DNL Target] att testa och personalisera upplevelser i stor skala.

[!DNL AEM] sammanför allt innehåll och alla resurser på en central plats för att understödja er personaliseringsstrategi. [!DNL AEM] gör att du enkelt kan skapa innehåll för datorer, surfplattor och mobila enheter på en plats utan att skriva kod. Du behöver inte skapa sidor för alla enheter. [!DNL AEM] anpassar automatiskt varje upplevelse med ditt innehåll.

[!DNL Target] Med kan ni leverera personaliserade upplevelser i stor skala baserat på en kombination av regelbaserade och AI-drivna maskininlärningsstrategier som innehåller beteendevariabler, sammanhangsbaserade variabler och offlinevariabler. Med [!DNL Target] er kan ni enkelt konfigurera och köra [A/B-tester](/help/c-activities/t-test-ab/test-ab.md) och [multivariata](/help/c-activities/c-multivariate-testing/multivariate-testing.md) -aktiviteter (MVT) för att fastställa de bästa erbjudandena, innehållet och upplevelserna.

Experience fragments utgör ett stort steg framåt för att länka samman innehålls-/upplevelseskapare och chefer med proffsen för optimering och personalisering som driver affärsresultaten med [!DNL Target].

## Krav {#section_AE6F0971E1574B3AA324003599B96E5A}

Du måste ha tillgång till funktionerna för upplevelsefragment i [!DNL Target]. Dessutom måste du använda [!DNL AEM] 6.3 med lämpligt Service Pack eller [!DNL AEM] 6.4 (eller senare). Din kontorepresentant kan se till att du uppfyller kraven för den här funktionen:

* [!DNL Adobe Experience Manager] 6.4 (eller senare).
* [!DNL Adobe Experience Manager] 6.3 SP2 (eller senare).
* [!DNL Adobe Target Standard] eller [!DNL Adobe Target Premium] konto.
* Kontakta [Adobe Target kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att aktivera integreringen och ge dig autentiseringsinformation.

## Skapa och konfigurera upplevelsefragment i [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

För att kunna använda [!DNL AEM] upplevelsefragment i [!DNL Target]måste du utföra följande steg:

### Steg 1: Integrera [!DNL AEM] med [!DNL Target]

Mer information finns i:

* **[!DNL AEM]6.3**: [Gå med i Adobe Analytics och Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) i dokumentationen för _Adobe Experience Manager 6.3_ .
* **[!DNL AEM]6.4**: [Gå med i Adobe Analytics och Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) i dokumentationen för _Adobe Experience Manager 6.4_ .
* **[!DNL AEM]6.5**: [Gå med i Adobe Analytics och Adobe Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) i dokumentationen för *Adobe Experience Manager 6.5* .

### Steg 2: Skapa upplevelsefragmentet

Upplevelsefragment skapas i [!DNL AEM]. Mer information finns i:

* **[!DNL AEM]6.3**: [Upplev fragment](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) i dokumentationen till *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4**: [Upplev fragment](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) i dokumentationen till *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5**: [Upplev fragment](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) i dokumentationen till *Adobe Experience Manager 6.5* .

### Steg 3: Konfigurera [!DNL AEM] att dela upplevelsefragmentet med [!DNL Target]

1. I [!DNL AEM]väljer du önskat upplevelsefragment eller tillhörande mapp och klickar sedan på **[!UICONTROL Properties]**.
2. Klicka på **[!UICONTROL Cloud Services]** fliken och välj sedan i **[!UICONTROL Cloud Service Configuration]** listrutan **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >I föregående steg förutsätts att någon i organisationen har skapat [!DNL Adobe Target] konfigurationen.

3. Klicka på **[!UICONTROL Save & Close]**.

### Steg 4: Publicera upplevelsefragmentet och exportera det till [!DNL Target]

Beroende på vilken version du har kan du läsa följande länkar för steg-för-steg-instruktioner: [!DNL AEM]

* **[!DNL AEM]6.3**: [Exportera ett Experience Fragment till Target](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) i dokumentationen för *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4**: [Exportera ett Experience Fragment till Target](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) i dokumentationen för *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5**: [Exportera ett Experience Fragment till Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) i dokumentationen för *Adobe Experience Manager 6.5* .

## Använda upplevelsefragment i målaktiviteter {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

När du har utfört de föregående åtgärderna visas upplevelsefragmentet på [!UICONTROL Offers] sidan i [!DNL Target].

>[!NOTE]
>
>[!DNL Target] letar efter upplevelsefragment som ska importeras var tionde minut. Det importerade upplevelsefragmentet bör vara tillgängligt inom [!DNL Target] tio minuter, men den här tidsramen bör korta av framgången.

>[!IMPORTANT]
>
>Experience fragment importeras för närvarande till [!DNL Target] som ett HTML-erbjudande. Observera att den &quot;primära&quot; versionen för upplevelsefragmentet finns kvar i [!DNL AEM]. Du kan inte redigera upplevelsefragmentet i [!DNL Target].

Du kan hovra över ett upplevelsefragment i listan och sedan klicka på [!UICONTROL View] ikonen ![Visa](assets/icon_info.png) för att se ytterligare information om upplevelsefragmentet, inklusive dess URL för offentlig leverans av erbjudanden och dess [!DNL AEM] sökväg.

Du kan använda upplevelsefragment i [!DNL Target] aktiviteter med [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) eller den [formulärbaserade Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Om du vill utnyttja [!DNL Target] AI- och ML-funktionerna fullt ut kan du välja [Automatisk allokering](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) eller [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) när du skapar ett A/B-test.

**Så här använder du upplevelsefragment med VEC:**

1. När du [!DNL Target]skapar eller redigerar en upplevelse i [Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)klickar du på den plats på sidan där du vill infoga [!DNL AEM] innehåll. Välj sedan önskat alternativ för att visa [!UICONTROL Choose an Experience Fragment] listan.

   * [!UICONTROL Insert Before]
   * [!UICONTROL Insert After]
   * [!UICONTROL Swap with Experience Fragment]

   I [!UICONTROL Experience Fragment] listan visas allt innehåll som skapats i [!DNL AEM] och som nu är inbyggt tillgängligt inifrån [!DNL Target].

   >[!NOTE]
   >
   >Alternativet [!UICONTROL Swap with Experience Fragment] är inte tillgängligt för bilder. Om du vill använda det här alternativet med en bild klickar du på behållarelementet som innehåller den önskade bilden.

   ![](assets/experience_fragment_list.png)

1. Välj önskat upplevelsefragment och klicka sedan på **[!UICONTROL Done]**.
1. Slutför konfigurationen av aktiviteten.

   Mer information om hur du konfigurerar de olika aktivitetstyperna finns i följande avsnitt:

   * **A/B-test:** [Skapa ett A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Automatisk fördelning:** [Automatisk allokering](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Automatiskt mål:** [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):** [Skapa en Automated Personalization-aktivitet](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Experience Targeting (XT):** [Skapa en upplevelseinriktad aktivitet](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Multivariata tester (MVT):** [Skapa ett multivariata test](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Skapa en Recommendations-aktivitet](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**Så här använder du upplevelsefragment med den formulärbaserade Experience Composer:**

1. När du [!DNL Target]skapar eller redigerar en upplevelse i den [formulärbaserade Experience Composer](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)i markerar du den plats på sidan där du vill infoga [!DNL AEM] innehåll och väljer sedan **[!UICONTROL Change Experience Fragment]** att visa [!UICONTROL Choose an Experience Fragment] listan.

   ![](assets/experience_fragment_list.png)

   I [!UICONTROL Experience Fragment] listan visas allt innehåll som skapats i [!DNL AEM] och som nu är inbyggt tillgängligt inifrån [!DNL Target].

1. Välj önskat upplevelsefragment och klicka sedan på **[!UICONTROL Save]**.
1. Slutför konfigurationen av aktiviteten.

## Överväganden {#considerations}

* [!DNL Target] letar efter upplevelsefragment som ska importeras var tionde minut. Det importerade upplevelsefragmentet bör vara tillgängligt inom [!DNL Target] tio minuter, men den här tidsramen bör korta av framgången.
* Experience fragment importeras för närvarande till [!DNL Target] som ett HTML-erbjudande. Observera att den &quot;primära&quot; versionen för upplevelsefragmentet finns kvar i [!DNL AEM]. Du kan inte redigera upplevelsefragmentet i [!DNL Target].
* Du kan importera JSON-erbjudanden som upplevelsefragment till [!DNL Target]. Erbjudandena importeras dock som HTML-erbjudanden. JSON-erbjudanden (upplevelsefragment) stöds för närvarande inte helt i [!DNL Target] användargränssnittet.
* Du kan inte skapa upplevelsefragment med Adobe IO. Du måste skapa upplevelsefragment med AEM, vilket förklaras ovan.

## Utbildningsvideo: Använda AEM upplevelsefragment med Adobe Target ![självstudiemärke](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

I följande video visas hur du konfigurerar och använder upplevelsefragment:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Funktionen [!DNL AEM] för deplink, som diskuterades 4:54, har tagits bort.

Mer information finns i [Använda Experience Fragments med Adobe Target](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) på sidan *AEM Sites Videos och Tutorials* .
