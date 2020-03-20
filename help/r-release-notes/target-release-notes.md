---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL-versionerna av Adobe Target.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e8d57a7288eddac2ec11d4c32c3c31ea77ab542e

---


# Versionsinformation för mål (prerelease){#target-release-notes-prerelease}

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande [!DNL Adobe Target] versionerna.

**Senast uppdaterad: 20 mars 2020**

>[!NOTE]
>
>* Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Information om den aktuella versionen finns i [Versionsinformation](release-notes.md)för mål. Informationen på de här sidorna kan vara densamma, eller så kan den variera beroende på när releaserna släpps.
   >
   >
* Numren inom parentes är avsedda för intern [!DNL Adobe] användning.
   >
   >
* **Ändringar** i TLS-stödet: Från och med 1 mars 2020 kommer Target att inaktivera stödet för kryptering med TLS 1.1 och TLS 1.0. TLS (Transport Layer Security) är det vanligaste säkerhetsprotokoll som används idag för webbläsare och andra program som kräver att data utbyts på ett säkert sätt över ett nätverk. Den här ändringen krävs för att uppfylla den allmänt accepterade standarden för säkerhetsefterlevnad i TLS 1.2 eller senare. Kontrollera vilken TLS-version du använder just nu. Om versionen är lägre än 1.2 implementerar du ändringarna före 1 mars 2020 för att fortsätta använda Target som förväntat.
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

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
