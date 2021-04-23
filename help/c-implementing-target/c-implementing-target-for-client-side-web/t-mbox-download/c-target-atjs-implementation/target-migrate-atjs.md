---
keywords: Mål;at.js;migrera till at.js;beredskap;revision at.js;integration at.js
description: Lär dig hur du migrerar till at.js, det nya implementeringsbiblioteket för Adobe [!DNL Target] som är utformat för både vanliga webbimplementeringar och Single Page-program (SPA).
title: Migrera till at.js från mbox.js
feature: at.js
role: Developer
exl-id: d612ca74-521b-437e-aa9a-b1065e460d45
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Migrera till at.js från mbox.js

Att migrera från mbox.js till at.js i [!DNL Adobe Target] är en enkel process.

Följ de här stegen för att migrera från [!DNL mbox.js] till [!DNL at.js] och för att kontrollera migreringen:

1. Bestäm organisationens [webbläsarstöd](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100) krav.
1. Kontrollera webbplatsens aktuella [!DNL mbox.js]-implementering för funktioner som inte stöds av [!DNL at.js].

   När du granskar implementeringen bör du kontrollera följande:

   **Vilka typer av rutor använder du för närvarande?**

   | Typ | Detaljer |
   |--- |--- |
   | Automatiskt skapad global mbox | Den automatiskt skapade globala mbox skapas när den enda raden med Target-kod på din plats är filen mbox.js. Filen genererar automatiskt ett mbox-anrop. |
   | Global, tom mboxCreate | Vi rekommenderar att du växlar till den automatiskt skapade globala mbox. |
   | FigursättningsrutaSkapa | Migreringen ska vara enkel, förutsatt att `mboxCreate()` föregås av `<div class="mboxDefault"></div>`. |
   | mboxUpdate | Migreringen ska vara enkel när `mboxUpdate()` används tillsammans med `mboxDefine()` eller `mboxCreate()`. `mboxUpdate()` uppdaterar inte den automatiskt skapade globala mbox eller en mbox som ursprungligen skapades av  `getOffer()`. Under dessa omständigheter bör en kombination av `getOffer()` och `applyOffer()` användas för att ersätta `mboxUpdate()` vid migrering till at.js. |
   | Anpassade kryssrutor, inklusive mboxTrack | Vi rekommenderar att du uppdaterar koden så att den använder `trackEvent()`. |

   >[!NOTE]
   >
   >Mer information om de olika funktioner som nämns i föregående tabell finns i [at.js-funktioner](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

   **Har du några anpassningar av din  [!DNL mbox.js] fil?**

   * mboxParameters()
   * mboxSupported()
   * mboxCookieDomain()
   * Extra Javascript
   * Andra platser

   De flesta av [mbox.js-objekten och -metoderna](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (till exempel `mbox`, `mboxCurrent`, `mboxFactoryDefault`, `mboxFactories`) stöds inte. Det kan finnas alternativa metoder för att uppnå det du försöker göra.

   **Har du  [!DNL mbox.js] några webbsidor?**

   Du kan inte använda både [!DNL at.js] och [!DNL mbox.js] på samma webbsida. Du kan dock använda de två JavaScript-biblioteken på två olika sidor på samma webbplats.

   Mbox-cookie är huvudsättet som Adobe sammanfogar besökaren från sida till sida. Som en del av QA-processen bör du bekräfta att cookien bevaras och läses korrekt när besökaren går fram och tillbaka mellan sidor med [!DNL at.js] och sidor med [!DNL mbox.js]. Se till att samma `mboxPC`- och `mboxSession`-värden skickas i mbox-anropen, oavsett vilken del av webbplatsen ( [!DNL at.js] eller [!DNL mbox.js]) som besökaren först får plats på och vilket avsnitt som ursprungligen ställer in cookien. Om du använder cookies från tredje part i din implementering måste du se till att dessa värden är desamma som när du bläddrar på webbplatsen.

   **Kan ni integrera  [!DNL Target] med andra Adobe-lösningar?**

   * Analyser (A4T)
   * Analyser (äldre integration)
   * AAM (serverdel)
   * AAM (äldre front)
   * AEM
   * Data Workbench

   Vissa av de äldre integreringarna stöds inte av [!DNL at.js]. Mer information finns på sidan [Integrationer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **Kan ni integrera  [!DNL Target] med verktyg från tredje part?**

   * Andra analysverktyg
   * Andra datahanteringsplattformar
   * Demandbase
   * Click-tale
   * Övriga

   Dessa integreringar kan behöva justeras för att fungera med [!DNL at.js]. Mer information finns på sidan [Integrationer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **Använder du en tagghanterare?**

   * Dynamisk tagghantering
   * Upptäck
   * Tealium
   * Signal/BrightTag

   Mer information finns i [at.js Integrations](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   >[!NOTE]
   >
   >Om du för närvarande inte använder en tagghanterare för att distribuera [!DNL Target] kan det nu vara ett bra tillfälle att överväga det. Adobe [Dynamic Tag Management](https://dtm.adobe.com) är kostnadsfritt för [!DNL Target]-kunder och är den metod som rekommenderas för att distribuera [!DNL Target]. Mer information finns i [Bästa metoder för att implementera Adobe Target med dynamisk tagghantering](https://experienceleague.adobe.com/docs/dtm/implementing/overview.html).

1. Kontrollera att alla aktuella aktiviteter och integreringar fungerar som förväntat.

   Här är några saker du kan göra när du testar för att bekräfta att [!DNL at.js] fungerar som väntat:

   * Se till att alla dina aktuella aktiviteter fungerar med det nya JavaScript-biblioteket.
   * Bekräfta att alla [integreringar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) och [plugin-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) fungerar som förväntat.
   * Se till att du känner dig bekväm med [felsökning](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) med de metoder som är tillgängliga med [!DNL at.js].

**Möjliga problem vid migrering till at.** jsVissa kunder har rapporterat följande problem efter migreringen till at.js:

* Vissa VEC-aktiviteter som har byggts på en sida med [!DNL mbox.js] kan behöva uppdateras för att fungera med [!DNL at.js].

   Det här problemet uppstår oftast på webbplatser som inte använder många id- eller klassattribut i HTML-element. Du kan bekräfta om du har problem genom att läsa in sidan och avgöra om upplevelsen levereras som förväntat genom att läsa in sidan med `?mboxDebug=true` och granska konsolsatserna.

   ![](assets/mboxdebug.png)
I dessa fall kan elementväljarna börja med något som

   ```
   HTML > BODY > DIV:nth-of-type(2)
   ```

   och byggdes med förväntan att [!DNL mbox.js] lade till ett extra `<div>`-element högst upp på sidan. Eftersom [!DNL at.js] inte lägger till ett `<div>`-element överst på sidan, fungerar väljaren inte längre med [!DNL at.js].

   Problemet kan åtgärdas genom att aktiviteten i VEC återskapas på URL:en med [!DNL at.js] eller genom att väljaren uppdateras manuellt med alternativet **[!UICONTROL </> Code]** > **[!UICONTROL Modifications]** i VEC.

   För att åtgärda detta bör du subtrahera 1 från det n:te typnumret i det första DIV-elementet efter BODY. I ovanstående exempel blir den redigerade koden:

   ```
   HTML > BODY > DIV:nth-of-type(1)
   ```

   Mer information om hur du använder kodredigeraren finns i [Kodredigeraren](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5).

* Eftersom alla rutor nu är asynkrona blockerar de inte sidåtergivning eller returnerar i den ordning som de utlöses. Mer information finns i&quot;Asynkrona överväganden&quot; i [at.js-begränsningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#concept_FA99E4D6EC274552BF45E01AFB76CCAE).
