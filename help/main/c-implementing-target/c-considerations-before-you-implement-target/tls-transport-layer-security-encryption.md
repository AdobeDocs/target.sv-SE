---
keywords: tls;tls 1.0;transport layer security;encryption;tls 1.1;tls 1.2
description: Lär dig mer [!DNL Target] använder TLS-protokollet (Transport Layer Security) för att upprätthålla högsta säkerhetsstandard och främja säkerheten för dina kunddata.
title: Hur [!DNL Target] Vill du använda TLS för att tillhandahålla säkerhet?
feature: Privacy & Security
role: Developer
exl-id: 964a642a-830a-4556-a92a-d300670cd2fa
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 0%

---

# TLS-krypteringsändringar (Transport Layer Security)

Information om förändringar i hur [!DNL Adobe] och [!DNL Adobe Target] använda TLS (Transport Layer Security) för att upprätthålla högsta säkerhetsstandard och främja säkerheten för kunddata.

TLS (Transport Layer Security) är det vanligaste säkerhetsprotokoll som används idag för webbläsare och andra program som kräver att data utbyts på ett säkert sätt över ett nätverk. Adobe har standarder för att uppfylla säkerhetskraven som kräver att äldre protokoll upphör att gälla och kräver att TLS 1.2 används för att få den senaste och säkraste versionen att använda.

>[!IMPORTANT]
>
>Efter den 1 mars 2020 har Adobe Target inte längre stöd för TLS 1.1-kryptering för Visual Experience Composer (VEC), Enhanced Experience Composer (EEC), aktivitetsleverans, API:er osv. Uppgradera till TLS 1.2 före 1 mars 2020 för att undvika problem.

Vi förväntar oss inte att detta ska ha någon större inverkan på kunddata eller rapportering.

## Visual Experience Composer (VEC) med Enhanced Experience Composer (EEC) aktiverat {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

TLS 1.2 är standard från och med 1 mars 2020 och TLS 1.1 stöds inte längre.

Adobe kommer att flytta kunder i faser till TLS 1.2. För dem vars domäner redan är 1.2-kompatibla kommer vi att flytta dem till TLS 1.2 utan att du behöver göra några ändringar. De flesta kunddomäner har redan stöd för TLS 1.2. Om din domän inte stöder TLS 1.2 behåller vi dessa domäner på TLS 1.1 som i dag (till mars 2020).

Du bör inte ställas inför något problem under den här migreringsfasen. Om VEC har slutat läsa in en plats som tidigare fungerade, [öppna en kundtjänstbiljett](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) som anger att migreringen är en möjlig orsak.

Om du däremot är en av de kunder som har TSL 1.1 utan stöd för TLS 1.2 bör du planera för att flytta dina domäner/din infrastruktur till TLS 1.2. Vi kommer att fortsätta att stödja TLS 1.1-protokollet fram till 1 mars 2020. Från och med 1 mars 2020 stöder inte Target TLS 1.1-protokollet som ska användas för VEC via funktionen Enhanced Experience Composer.

Även om vi rekommenderar alla att vara med på TLS 1.2 framåt, om du är ny kund men gör det *NOT* för TLS 1.2, kontakta kundtjänst och informera dem om att ni behöver använda TLS 1.1 för Enhanced Experience Composer. Men planera för att gå över till TLS 1.2 eftersom du inte heller kommer att få stöd efter 1 mars 2020.

## Aktivitetsleverans {#section_46CA5943E4354B259014C2BF340AECD6}

Från och med 1 mars 2020 har målservrar inte längre stöd för TLS 1.1. Den här ändringen innebär att målservrar inte längre accepterar förfrågningar från besökare med äldre enheter eller webbläsare som inte stöder TLS 1.2 (eller senare). Därför kommer äldre enheter och webbläsare som bara stöder TLS 1.1 (eller som standard stöder TLS 1.1) inte att få aktivitetsinnehåll från Adobe Target. Webbplatsens standardinnehåll återges.

Några av de äldre enheterna och webbläsarna som påverkas är:

* Google Chrome (Chrome för Android) version 29 och tidigare
* Opera Browser (Opera Mobile) version 12.17 och tidigare
* Mozilla Firefox (Firefox for Mobile) version 26 och tidigare
* Android 4.3 och tidigare versioner
* Internet Explorer 8-10 i Windows 7 och tidigare
* Internet Explorer 10 på Windows Phone 8.0
* Safari 6.0.4/OS X10.8.4 och tidigare versioner

När du planerar för den här ändringen bör du tänka på följande (observera att 1 mars 2020-datumet påverkar alla dessa punkter):

* Du måste se till att din standardwebbplats är klar på ett sätt som kan användas för kompatibla enheter och webbläsare.
* Tänk på att antalet besökare i dina Target-rapporter potentiellt kan se en obetydlig minskning av antalet besökare.
* Du kan behöva ändra målgrupper som skapats specifikt för äldre enheter eller webbläsare som inte stöder TLS 1.2. Leverans till dessa enheter och webbläsare fungerar inte längre.

Mer information om vilka webbläsare som stöds och vilka versioner som stöds finns i [Webbläsare som stöds](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## Adobe [!DNL Target] API:er {#section_88797FA5434049EC89F908853CC76903}

Från och med 1 mars 2020 har mål-API:er inte längre stöd för TLS 1.1-kryptering. Kunder som har åtkomst till API bör verifiera att de inte kommer att påverkas.

* API-klienter som använder Java 7 med standardinställningar behöver ändras för att stödja TLS 1.2. Mer information finns i &quot; [Ändra standardversion för TLS-protokoll för klientslutpunkter: TLS 1.0 till TLS 1.2](https://www.java.com/en/configure_crypto.html)&quot; på Java-webbplatsen.
* API-klienter som använder Java 8 bör inte påverkas eftersom standardinställningen är TLS 1.2.
* API-klienter som använder andra ramverk måste kontakta sina leverantörer för att få information om TLS 1.2-stödet.

## Tillgång till Experience Cloud Solutions-gränssnitt {#section_748870ADE77B4CBEB18518DC784E64E5}

Eftersom gränssnittet Target Standard/Premium redan kräver en [modern webbläsare](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), vi förutser inga problem. Om du inte kan ansluta till Target bör du uppgradera webbläsaren till den senaste versionen.

## Kontrollera vilken TLS-version webbläsaren använder {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Så här kontrollerar du TLS-versionen på din webbplats med Google Chrome:

1. Öppna den berörda webbplatsen i Chrome.
1. Klicka på Fler verktyg > Utvecklarverktyg på menyn Krom (de tre lodräta ellipserna).

   ![Verktyg för Chrome Developer](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. Öppna fliken Säkerhet och granska sedan TLS-versionsinformationen under Connection:

   ![TLS - versionsinformation](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>Dessa instruktioner är aktuella från och med publiceringen och kan komma att ändras. En snabb Internetsökning bör hjälpa dig om instruktionerna ändras.  Andra webbläsare har liknande steg.

## Förväntat beteende med webbläsare som stöder TLS-versioner under 1.2 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

I det här avsnittet beskrivs vad du kan förvänta dig av webbläsare som stöder TLS-versioner under 1.2 endast när du använder en at.js-implementering. I det här avsnittet beskrivs också vad som ska förväntas med webbläsare som stöder TLS 1.2.

### Centrala slutpunkter

| JavaScript-implementering | Detaljer |
|--- |--- |
| at.js | Med TLS 1.0 eller TLS 1.1 aktiverat:<ul><li>Med hjälp av webbläsarens utvecklingsverktyg visas&quot;200 OK&quot; på fliken Nätverk. Detta innebär att begäran har slutförts.</li><li>Användaren ser meddelandet&quot;Kan inte ansluta säkert till den här sidan&quot;. Meddelandet förklarar att detta kan bero på att webbplatsen använder föråldrade eller osäkra TLS-säkerhetsinställningar.</li><li>Inga konsolfel visas.</li></ul>Med TLS 1.2 aktiverat:<ul><li>filen at.js hämtas.</li></ul> |

### Kantslutpunkter

| JavaScript-implementering | Detaljer |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | Med TLS 1.0 eller TLS 1.1 aktiverat:<ul><li>Med hjälp av webbläsarens utvecklingsverktyg visas&quot;200 OK&quot; på fliken Nätverk. Detta innebär att begäran har slutförts.</li><li>Användaren ser meddelandet&quot;Kan inte ansluta säkert till den här sidan&quot;. Meddelandet förklarar att detta kan bero på att webbplatsen använder föråldrade eller osäkra TLS-säkerhetsinställningar.</li><li>Inga konsolfel visas.</li><li>Standardinnehåll hanteras.</li></ul>Med TLS 1.2 aktiverat:<ul><li>Erbjudandet gäller.</li></ul> |
| at.js | Med TLS 1.0 eller TLS 1.1 aktiverat:<ul><li>Med hjälp av webbläsarens utvecklingsverktyg visas&quot;200 OK&quot; på fliken Nätverk. Detta innebär att begäran har slutförts.</li><li>Användaren ser meddelandet&quot;Kan inte ansluta säkert till den här sidan&quot;. Meddelandet förklarar att detta kan bero på att webbplatsen använder föråldrade eller osäkra TLS-säkerhetsinställningar.</li><li>Inga konsolfel visas.</li><li>Standardinnehåll hanteras.</li></ul>Med TLS 1.2 aktiverat:<ul><li>Erbjudandet gäller.</li></ul> |

### Aktivitet som riktar sig till användare som har webbläsarversion (Internet Explorer, version 6, 7 eller 8)

>[!NOTE]
>
>Målgrupperna slutar att fungera.

| JavaScript-implementering | Detaljer |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | Plattforms-SDK stöds inte i tidigare versioner än version 10 av Internet Explorer. |
| at.js | at.js stöds inte i tidigare versioner än version 10 av Internet Explorer. |