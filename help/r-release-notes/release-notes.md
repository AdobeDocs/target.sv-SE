---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Versionsinformationen innehåller information om funktioner, förbättringar, korrigeringar och kända fel för varje version av Adobe Target Standard och Target Premium.
title: 'Versionsinformation om Adobe Target (aktuell) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 51abcafed1641d073b38800d0fea756df92b3685

---


# Versionsinformation för mål (aktuell){#target-release-notes-current}

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje Target Standard- och Target Premium-version. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!NOTE]
>
>* **Ändringar** i TLS-stödet: Från och med 1 mars 2020 kommer Target att inaktivera stödet för kryptering med TLS 1.1 och TLS 1.0. TLS (Transport Layer Security) är det vanligaste säkerhetsprotokoll som används idag för webbläsare och andra program som kräver att data utbyts på ett säkert sätt över ett nätverk. Den här ändringen krävs för att uppfylla den allmänt accepterade standarden för säkerhetsefterlevnad i TLS 1.2 eller senare. Kontrollera vilken TLS-version du använder just nu. Om versionen är lägre än 1.2 implementerar du ändringarna före 1 mars 2020 för att fortsätta använda Target som förväntat.
   >
   >   
   Detaljerad information om möjliga konsekvenser och vilka åtgärder du kan behöva vidta för att uppdatera implementeringen finns i [TLS-krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)(Transport Layer Security).
   >
   >
* **borttagning** av mbox.js: 30 augusti 2020 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.
   >
   >
* Numren inom parentes är avsedda för intern [!DNL Adobe] användning.


## Summit Live: Digital Experience Conference {#summit}

Adobe Summit har blivit en virtuell händelse! Adobe tar alla steg framåt med en livebaserad digital upplevelse från och med 31 mars 2020. Den här liveupplevelsen kommer att innehålla vår huvudadress för Keynote, mini-keynotes med de senaste trenderna och framstegen, insikter om branschledarnas framgångar och sessioner.

* **Se inledningsanförandet live**: Lyssna på trender och nya produkter som förändrar branschen från bekvämligheten var du än är.
* **Upptäck fler än 100 nyheter vid behov:** Få kostnadsfri tillgång till över hundra on demand-seminarier från Adobe, kunder och partners.
* **Toppvärde i framtiden**: Besök vår speciella gäst Chelsea Handler och se den senaste experimentella tekniken från våra labb - på Adobe Sneaks.

Om du vill registrera dig för kostnadsfri åtkomst till hela det digitala evenemanget går du till [The Digital Experience Conference: Summit](https://www.adobe.com/summit.html) page.

## Target Standard/Premium 20.2.1 (17 mars 2020)

>[!IMPORTANT]
>
>Se informationen ovan om borttagningen av mbox.js.

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Korrigerade ett problem som hindrade kunder från att välja en samling när de gjorde en katalogsökning. (TGT-36230)
* Korrigerade ett problem där ett villkor som skapats via API, men som inte refererats av en aktivitet som skapats i målgränssnittet, felaktigt kunde tas bort från gränssnittet. (TGT-35917)
* Implementerade säkerhetsförbättringar i Content Security Policy (CSP). (TGT-36190)
* Korrigerade ett problem som gjorde att &quot;NaN%&quot; visades när procentfältet för attributviktning drog åt vänster. (TGT-36211)
* Löste lokaliseringsproblem så att gränssnittstext på olika språk visas korrekt.
* Följande Adobe Analytics-mått stöds inte längre för Analytics for Target (A4T) från och med Target-versionen från mars 2020:
   * averagevisitdepth
   * botar
* Följande mått stöds inte längre och konverteras automatiskt till nya versioner av måttet första gången en användare ändrar en aktivitet som innehåller måttet:

   | Inaktuellt mått | Nytt mått |
   |--- |--- |
   | `averagetimespentonpage` | `averagetimespentonsite` (Obs! mätt i minuter i stället för sekunder) |
   | `instances` | `occurrences` |
   | `singleaccess` | `singlepagevisits` |
   | `uniquevisitors` | `visitors` |
   | `visitorsdaily`, `visitorshourly`, `visitorsmonthly`, `visitorsquarterly`, `visitorsweekly`, `visitorsyearly` | `visitors` |

## Adobe Experience Cloud-navigering (22 februari 2019)

* När du loggar in på [!DNL Adobe Experience Cloud]sidan kommer du till den nya rubriknavigeringen. Den ser ut ungefär som den tidigare navigeringen med det svarta fältet högst upp, men har följande förbättringar:

   * Enklare att växla mellan [!DNL Identity Management System] (IMS)-organisationer eller till en annan lösning.
   * Förbättrad användarhjälp: Sökresultaten är bland annat resultat från [!DNL Target] produktdokumentationen, communityforum och mer videoinnehåll, vilket gör det enklare att få tillgång till mer innehåll för att få ut så mycket som möjligt [!DNL Target]. Vi har också lagt till en funktion för feedback direkt på [!UICONTROL Help] menyn, vilket gör det enklare att rapportera problem eller dela med dig av dina idéer.

   * Förbättrad feedback för NPS (Net Promoter Score) så att undersökningen inte stör arbetsflödet.
   * Förbättrat inloggningsflöde. Tidigare landade alla [!DNL Target] kunder på landningssidan Target efter att ha klickat på [!DNL Target] ikonen i sidhuvudet. På den här sidan kan kunderna sedan gå vidare med [!DNL Target Standard/Premium], [!DNL Search&Promote]eller [!DNL Recommendations Classic]enligt nedan:

      ![Landningssida](/help/r-release-notes/assets/landing.png)

      Vi eliminerade den här landningssidan för alla våra kunder. Du kommer nu alltid direkt till [!UICONTROL Activities List] sidan genom att klicka på [!DNL Target] ikonen i det nya sidhuvudsnavigeringsfältet.

      Om du använder [!DNL Recommendations Classic]kan du antingen gå direkt till lösningen eller gå från den korta länken som skapas på [!UICONTROL Recommendations] fliken enligt nedan:

      ![Recs Classic deep link](/help/r-release-notes/assets/recs-classic.png)

      Om du använder [!DNL Search&Promote]måste du gå direkt till URL:en [för sökning och befordran](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1). Sökvägen som ska nås [!DNL Search&Promote] inifrån [!DNL Adobe Target] har tagits bort helt.

   * Meddelanden för [!DNL Target] är för närvarande inte tillgängliga i [!UICONTROL Notifications] listrutan i sidhuvudet.
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
