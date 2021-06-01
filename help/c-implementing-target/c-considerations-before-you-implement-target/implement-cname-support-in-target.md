---
keywords: klientvård;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicering;domain control validation;dcv
description: Arbeta med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i Adobe [!DNL Target] för att hantera annonsblockerande problem eller ITP-relaterade cookie-principer.
title: Hur använder jag CNAME i Target?
feature: Integritet och säkerhet
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 0327f4450ad7b764b01091a106e3dfd3160ffbaf
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 0%

---

# CNAME och Adobe Target

Instruktioner för hur du arbetar med [!DNL Adobe] Client Care för att implementera stöd för CNAME (Canonical Name) i [!DNL Adobe Target]. Använd CNAME för att hantera annonsblockeringsproblem eller ITP-relaterade (Intelligent Tracking Prevention) cookie-principer. Med CNAME anropas en domän som ägs av kunden i stället för en domän som ägs av [!DNL Adobe].

## Begär CNAME-stöd i Target

1. Bestäm listan med värdnamn som du behöver för ditt SSL-certifikat (se Vanliga frågor och svar nedan).

1. För varje värdnamn skapar du en CNAME-post i din DNS som pekar på det vanliga [!DNL Target] värdnamnet `clientcode.tt.omtrdc.net`.

   Om klientkoden till exempel är &quot;namnkund&quot; och det föreslagna värdnamnet är `target.example.com` ser din DNS CNAME-post ut ungefär så här:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >AdobeCertificateAuthority, DigiCert, kan inte utfärda ett certifikat förrän det här steget har slutförts. Därför kan [!DNL Adobe] inte uppfylla din begäran om en CNAME-implementering förrän det här steget är klart.

1. [Fyll i det här ](/help/assets/FPC_Request_Form.xlsx) formuläret och inkludera det när du  [öppnar en Adobe Client Care-biljett som begär CNAME-stöd](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe [!DNL Target] klientkod:
   * Värdnamn för SSL-certifikat (exempel: `target.example.com target.example.org`):
   * Inköpare av SSL-certifikat (Adobe rekommenderas starkt, se Vanliga frågor och svar): Adobe/kund
   * Om kunden köper certifikatet, även kallat &quot;Bring Your Own Certificate&quot; (BYOC), fyll i dessa ytterligare uppgifter:
      * Certifikatorganisation (exempel: Exempel på Company Inc):
      * Organisationsenhet för certifikat (valfritt, exempel: Marknadsföring):
      * Certifikatland (exempel: USA):
      * Certifikatstatus/region (exempel: Kalifornien):
      * Ort för certifikat (exempel: San Jose):

1. Om [!DNL Adobe] köper certifikatet fungerar [!DNL Adobe] tillsammans med DigiCert för att köpa och distribuera certifikatet på Adobe produktionsservrar.

   Om kunden köper certifikatet (BYOC) skickar [!DNL Adobe] Client Care CSR-begäran (Certificate Signing Request) till dig. Använd CSR när du köper certifikatet via den valfria certifikatutfärdaren. När certifikatet har utfärdats skickar du en kopia av certifikatet och eventuella mellanliggande certifikat till [!DNL Adobe] Client Care för distribution.

   [!DNL Adobe] Client Care meddelar dig när implementeringen är klar.

1. Uppdatera `serverDomain` till nya CNAME i at.js.

## Vanliga frågor

Följande information besvarar vanliga frågor om att begära och implementera CNAME-stöd i [!DNL Target]:

### Kan jag tillhandahålla mitt eget certifikat (ta med ditt eget certifikat eller BYOC)?

Du kan ange ett eget certifikat. [!DNL Adobe] rekommenderar dock inte den här metoden. Hanteringen av SSL-certifikatets livscykel är enklare för både [!DNL Adobe] och du om [!DNL Adobe] köper och kontrollerar certifikatet. SSL-certifikaten måste förnyas varje år. Därför måste [!DNL Adobe] Client Care kontakta dig varje år för att få ett nytt certifikat i tid. Vissa kunder kan få svårt att snabbt få fram ett förnyat certifikat. Implementeringen av [!DNL Target] äventyras när certifikatet upphör att gälla eftersom webbläsare nekar anslutningar.

>[!IMPORTANT]
>
>Om du begär en [!DNL Target]-implementering av ditt eget certifikat för CNAME ansvarar du för att tillhandahålla förnyade certifikat till [!DNL Adobe] Client Care varje år. Om du tillåter att ditt CNAME-certifikat förfaller innan [!DNL Adobe] kan distribuera ett förnyat certifikat resulterar det i ett driftstopp för din specifika [!DNL Target]-implementering.

### Hur länge till mitt nya SSL-certifikat upphör att gälla?

Certifikat som utfärdats före den 1 september 2020 är tvååriga certifikat. Certifikat som utfärdas den 1 september 2020 eller senare är ettåriga certifikat. Du kan läsa mer om flytten till ettårscertifikat [här](https://www.digicert.com/position-on-1-year-certificates).

### Vilka värdnamn ska jag välja? Hur många värdnamn per domän ska jag välja?

[!DNL Target] CNAME-implementeringar kräver bara ett värdnamn per domän i SSL-certifikatet och i kundens DNS. Adobe rekommenderar ett värdnamn. Vissa kunder kräver fler värdnamn per domän för sina egna syften (till exempel testning i mellanlagring), vilket stöds.

De flesta kunder väljer ett värdnamn som `target.example.com`. Adobe rekommenderar att du följer den här metoden, men i slutändan är det ditt val. Begär inte ett värdnamn för en befintlig DNS-post. Om du gör det uppstår en konflikt och det tar längre tid att lösa din [!DNL Target] CNAME-begäran.

### Jag har redan en CNAME-implementering för [!DNL Adobe Analytics], kan vi använda samma certifikat eller värdnamn?

Nej, [!DNL Target] kräver ett separat värdnamn och certifikat.

### Påverkas min nuvarande implementering av [!DNL Target] av ITP 2.x?

I en Safari-webbläsare navigerar du till den webbplats där du har ett JavaScript-bibliotek. [!DNL Target] Om du ser en [!DNL Target]-cookie som angetts i en CNAME-kontext, till exempel `analytics.company.com`, påverkas du inte av ITP 2.x.

ITP-problem kan lösas för [!DNL Target] med endast en [!DNL Analytics] CNAME. Du behöver bara en separat [!DNL Target] CNAME i annonsblockerande scenarier där [!DNL Target] är blockerad.

Mer information om ITP finns i [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Vilken typ av tjänstavbrott kan jag förvänta mig när CNAME-implementeringen distribueras?

Det uppstår inga avbrott i tjänsten när certifikatet distribueras (inklusive certifikatförnyelse).

När du har ändrat värdnamnet i [!DNL Target]-implementeringskoden (`serverDomain` in at.js) till det nya CNAME-värdnamnet (`target.example.com`), behandlar webbläsare återkommande besökare som nya besökare. Returnerade besökares profildata går förlorade eftersom den tidigare cookien inte är tillgänglig under det gamla värdnamnet (`clientcode.tt.omtrdc.net`). Den tidigare cookien är inte tillgänglig på grund av säkerhetsmodeller i webbläsaren. Denna störning inträffar endast vid den första brytningen till den nya CNAME. Certifikatförnyelser har inte samma effekt eftersom värdnamnet inte ändras.

### Vilken nyckeltyp och certifikatsignaturalgoritm används för min CNAME-implementering?

Alla certifikat är RSA SHA-256 och nycklarna är RSA 2048-bitars som standard. Nyckelstorlekar som är större än 2 048 bitar stöds för närvarande inte.

### Hur verifierar jag att CNAME-implementeringen är klar för trafik?

Använd följande kommandouppsättning (i kommandoradsterminalen macOS eller Linux med bash och curl 7.49+):

1. Klistra in den här basfunktionen i terminalen:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Klistra in det här kommandot (ersätta `target.example.com` med ditt värdnamn):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Om implementeringen är klar visas utdata som nedan. Den viktiga delen är att alla rader innehåller `CN=target.example.com`, som matchar det önskade värdnamnet. Om några rader innehåller `CN=*.tt.omtrdc.net` är implementeringen **inte** klar.

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge36.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Validera din nya DNS CNAME med en annan begäran om att inaktivera DNS, som även ska visa `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Om det här kommandot misslyckas men kommandot `validateEdgeFpsslSni` lyckas väntar du tills DNS-uppdateringarna är helt spridda. DNS-poster har en associerad [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) som anger cacheförfallotid för DNS-svar för dessa poster. Därför kan du behöva vänta åtminstone så länge som TTL:erna är klara. Du kan använda kommandot `dig target.example.com` eller [G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) för att leta upp dina specifika TTL-värden.

### Hur använder jag en länk för avanmälan med CNAME?

Om du använder CNAME bör länken för avanmälan innehålla parametern &quot;client=`clientcode`:
`https://my.cname.domain/optout?client=clientcode`.

Ersätt `clientcode` med din klientkod och lägg sedan till texten eller bilden som ska länkas till [avanmälnings-URL](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## Kända begränsningar

* QA-läget är inte fast när du har CNAME och at.js 1.x eftersom det baseras på en cookie från tredje part. Du kan komma runt problemet genom att lägga till förhandsgranskningsparametrarna i varje URL som du navigerar till. QA-läget är fast när du har CNAME och at.js 2.x.
* För närvarande fungerar inte `overrideMboxEdgeServer`-inställningen korrekt med CNAME när du använder at.js-versioner före at.js 1.8.2 och at.js 2.3.1. Om du använder en äldre version av at.js bör den här inställningen anges som `false` för att undvika misslyckade begäranden. Du kan också överväga att [uppdatera at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) till en nyare version som stöds.
* När du använder CNAME blir det mer sannolikt att storleken på cookie-huvudet för [!DNL Target] anrop ökar. [!DNL Adobe] rekommenderar att kakstorleken hålls under 8 kB.
