---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Versionsinformationen innehåller information om funktioner, förbättringar, korrigeringar och kända fel för varje version av Adobe Target Standard och Target Premium.
title: 'Versionsinformation om Adobe Target (aktuell) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 1befd131034805ba81e4d68e7e976fd290041d52

---


# Versionsinformation för mål (aktuell){#target-release-notes-current}

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje Target Standard- och Target Premium-version. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!NOTE]
>
>* **borttagning** av mbox.js: 30 augusti 2020 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Se *Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js* nedan om du vill ha information om hur du registrerar dig för en kommande utvecklarchatt om det här ämnet.
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.


Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

## Adobe Target-verktyget för kompetensutveckling: Utvecklarchatt, migrera Adobe Target mbox.js till at.js {#skill-builder}

Träffa David Son, Adobe Target Product Manager, och berätta om fördelarna med att migrera mbox.js till at.js. Hör de senaste at.js-uppdateringarna, läs om de förbättrade funktionerna och hur de är anpassade till större trender inom teknologiområdet, samt några praktiska tips som ser till att du får ut så mycket av Target när du migrerar från mbox.js till at.js. Adobe Target-utvecklare vill inte missa detta!

Tisdag 5 maj 08:00 - 09:00 (PDT)

[Anmäl dig nu!](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target at.js (25 mars 2020)

Följande nya versioner av JavaScript-biblioteken Target at.js är tillgängliga:

* at.js version 2.3.0
* at.js version 1.8.1

Mer information finns [i versionsinformationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)för at.js.

## Target Standard/Premium 20.2.1 (23 mars 2020)

>[!IMPORTANT]
>
>Se informationen ovan om borttagningen av mbox.js.

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Korrigerade ett problem som hindrade kunder från att välja en samling när de gjorde en katalogsökning. (TGT-36230)
* Korrigerade ett problem där ett villkor som skapats via API, men som inte refererats av en aktivitet som skapats i målgränssnittet, felaktigt kunde tas bort från gränssnittet. (TGT-35917)
* Implementerade säkerhetsförbättringar i Content Security Policy (CSP). (TGT-36190)
* Korrigerade ett problem som gjorde att &quot;NaN%&quot; visades när procentfältet för attributviktning drog åt vänster. (TGT-36211)
* Löste lokaliseringsproblem så att gränssnittstext på olika språk visas korrekt.
* Vi har standardiserat listan med tillgängliga mätvärden från Adobe Analytics for Target-aktiviteter (A4T) genom att ta bort Adobe Analytics-mått som inte stöds i den aktuella versionen av Adobe Analytics API:er. Detta gör att vi kan utöka vår A4T-support i framtida Adobe Target-versioner.

   Följande ändringar har gjorts:

   * &quot;Genomsnittlig tid spenderad på sidan&quot; har ersatts med &quot;Genomsnittlig tid spenderad på webbplatsen.&quot; Alla aktiviteter som använder detta som mått för det primära målmåttet kommer att ha &quot;Genomsnittlig tid spenderad på platsen&quot; (Obs! anges i minuter i stället för sekunder) väljs som primärt målmått nästa gång aktiviteten redigeras.
   * &quot;Besökare&quot; har ersatts med &quot;unika besökare&quot;. Alla aktiviteter som använder det här måttet som primärt målmått kommer att ha &quot;Unika besökare&quot; valt som primärt målmått nästa gång aktiviteten redigeras.

* Följande mått har tagits bort och kan inte längre väljas som primärt målmått när en ny A4T-aktivitet skapas.

   | Inaktuella mått | Föreslagna ersättningsmått |
   |--- |--- |
   | Dagliga besökare, timbesökare, månatliga besökare, kvartalsbesök, veckobesökare och årsbesök | Unika besökare |
   | Genomsnittligt besöksdjup | Ej tillämpligt. Ej rekommenderat som primärt målmått |
   | Bots | Ej tillämpligt. Ej rekommenderat som primärt målmått |
   | Kraschfrekvens för mobiler, genomsnittlig tidigare sessionslängd för mobilappar, genomsnittlig rankning för mobilappsbutik, kraschfrekvens för mobilappsprestanda, genomsnittlig klassificering för mobilappsbutik | Ej tillämpligt. Ej rekommenderat som primärt målmått |

## Adobe Experience Cloud-navigering (22 februari 2019)

* När du loggar in på [!DNL Adobe Experience Cloud]sidan kommer du till den nya rubriknavigeringen. Den ser ut ungefär som den tidigare navigeringen med det svarta fältet högst upp, men har följande förbättringar:

   * Enklare att växla mellan [!DNL Identity Management System] (IMS)-organisationer eller till en annan lösning.
   * Förbättrad användarhjälp: Sökresultaten är bland annat resultat från [!DNL Target] produktdokumentationen, communityforum och mer videoinnehåll, vilket gör det enklare att få tillgång till mer innehåll för att få ut så mycket som möjligt [!DNL Target]. Vi har också lagt till en funktion för feedback direkt på [!UICONTROL Hjälp] -menyn, som gör det enklare att rapportera problem eller dela med dig av dina idéer.

   * Förbättrad feedback för NPS (Net Promoter Score) så att undersökningen inte stör arbetsflödet.
   * Förbättrat inloggningsflöde. Tidigare landade alla [!DNL Target] kunder på landningssidan Target efter att ha klickat på [!DNL Target] ikonen i sidhuvudet. På den här sidan kan kunderna sedan gå vidare med [!DNL Target Standard/Premium], [!DNL Search&Promote]eller [!DNL Recommendations Classic]enligt nedan:

      ![Landningssida](/help/r-release-notes/assets/landing.png)

      Vi eliminerade den här landningssidan för alla våra kunder. Du dirigeras nu alltid direkt till sidan [!UICONTROL Aktivitetslista] genom att klicka på [!DNL Target] ikonen i det nya sidhuvudsnavigeringsfältet.

      Om du använder [!DNL Recommendations Classic]kan du antingen gå direkt till lösningen eller gå från den korta länken på fliken [!UICONTROL Rekommendationer] , som visas nedan:

      ![Recs Classic deep link](/help/r-release-notes/assets/recs-classic.png)

      Om du använder [!DNL Search&Promote]måste du gå direkt till URL:en [för sökning och befordran](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1). Sökvägen som ska nås [!DNL Search&Promote] inifrån [!DNL Adobe Target] har tagits bort helt.

   * Meddelanden för [!DNL Target] är för närvarande inte tillgängliga i listrutan [!UICONTROL Meddelanden] i sidhuvudet.
   >[!NOTE]
   >
   >Som en del av utrullningen av det nya navigeringsfältet kommer du även att märka vissa URL-ändringar. Alla tidigare länkar med bokmärken fortsätter att fungera, men vi rekommenderar att du bokmärker nya länkar för snabbare öppning.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation - Målserversidans API:er](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Versionsinformation om Adobe Target-serversidans API:er. |
| [Versionsinformation - Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Versionsinformation om Adobe Target Node.js SDK. |
| [Versionsinformation - mål-Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Versionsinformation om Adobe Target Java SDK. |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringar i alla versioner av Adobe Target at.js JavaScript-biblioteket. |
| [versionsinformation för mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | På den här sidan visas ändringar för varje version av mbox.js.<br>Observera att mbox.js-biblioteket inte längre utvecklas. Alla kunder bör migrera från mbox.js till at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och versionsinformation för Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som kanske inte finns med i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](../r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation om Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud-lösningarna.<br>Mer information finns i Versionsinformation om [Experience Cloud](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html). |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdateringslista för Adobe-prioritet | Om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar registrerar du dig för produktuppdateringen Adobe Priority:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om målversionerna för den aktuella månaden, inklusive förhandsversionsinformation, finns på sidan [Viktigt om](/help/r-release-notes/target-release-notes.md) mål - Förhandsversion. |
