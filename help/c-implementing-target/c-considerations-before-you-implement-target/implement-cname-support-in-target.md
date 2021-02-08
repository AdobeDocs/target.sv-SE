---
keywords: klientvård;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicering;domain control validation;dcv
description: Arbeta med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i Adobe Target för att hantera annonsblockerande problem eller ITP-relaterade cookie-regler.
title: Hur använder jag CNAME i Target?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 0%

---


# CNAME och Adobe Target

Instruktioner för hur du arbetar med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i [!DNL Adobe Target]. För att på bästa sätt hantera annonsblockeringsproblem, eller ITP-relaterade cookie-policyer, används en CNAME så att anrop görs till en domän som ägs av kunden i stället för till en domän som ägs av Adobe.

## Begär CNAME-stöd

Utför följande steg för att begära CNAME-stöd i [!DNL Target]:

1. Avgör listan med värdnamn som du behöver för ditt SSL-certifikat (se Vanliga frågor och svar).

1. För varje värdnamn skapar du en CNAME-post i din DNS som pekar på det vanliga [!DNL Target] värdnamnet `clientcode.tt.omtrdc.net`.

   Om klientkoden till exempel är &quot;namnkund&quot; och det föreslagna värdnamnet är `target.example.com`, ska DNS CNAME-posten se ut ungefär så här:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >AdobeCertificateAuthority, DigiCert, kan inte utfärda ett certifikat förrän det här steget har slutförts. Därför kan Adobe inte uppfylla din begäran om CNAME-implementering förrän det här steget är klart.

1. [Fyll i det här ](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) formuläret och inkludera det när du  [öppnar en Adobe Client Care-biljett som begär CNAME-stöd](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe [!DNL Target] klientkod:
   * Värdnamn för SSL-certifikat (exempel: `target.example.com target.example.org`):
   * Inköpare av SSL-certifikat (Adobe rekommenderas starkt, se Vanliga frågor och svar): Adobe/kund
   * Om kunden köper certifikatet (även kallat BYOC), fyll i dessa ytterligare uppgifter:
      * Certifikatorganisation (exempel: Exempel på Company Inc):
      * Organisationsenhet för certifikat (valfritt, exempel: Marknadsföring):
      * Certifikatland (exempel: USA):
      * Certifikatstatus/region (exempel: Kalifornien):
      * Ort för certifikat (exempel: San Jose):

1. Om Adobe köper certifikatet arbetar Adobe tillsammans med DigiCert för att köpa och distribuera certifikatet på Adobe produktionsservrar.

   Om kunden köper certifikatet (BYOC) skickar Adobe Client Care CSR-begäran (Certificate Signing Request) till dig, som du måste använda när du köper certifikatet via den valfria certifikatutfärdaren. När certifikatet har utfärdats måste du skicka en kopia av certifikatet och eventuella mellanliggande certifikat tillbaka till Adobe Client Care för distribution.

   Adobe Client Care meddelar dig när implementeringen är klar.

1. När du har slutfört de föregående åtgärderna och Adobe Client Care har meddelat dig att implementeringen är klar, måste du uppdatera `serverDomain` till den nya CNAME-filen i at.js.

## Vanliga frågor

Följande information besvarar vanliga frågor om att begära och implementera CNAME-stöd i [!DNL Target]:

### Kan jag tillhandahålla mitt eget certifikat (även&quot;insert-your-own-certificate&quot; eller&quot;BYOC&quot;)?

Ja, du kan ange ett eget certifikat; rekommenderas dock inte. Hanteringen av SSL-certifikatets livscykel är mycket enklare för både Adobe och dig när Adobe köper och kontrollerar certifikatet. SSL-certifikaten måste förnyas varje år, vilket innebär att Adobe Client Care måste kontakta dig varje år för att skicka ett nytt certifikat till Adobe i tid. Vissa kunder kan få problem med att skapa ett förnyat certifikat i tid varje år, vilket äventyrar deras [!DNL Target]-implementering eftersom webbläsare kommer att neka anslutningar när certifikatet upphör att gälla.

>[!IMPORTANT]
>
>Tänk på att om du begär en [!DNL Target]-implementering av ditt eget certifikat för CNAME ansvarar du för att ge förnyade certifikat till Adobe Client Care varje år. Om du tillåter att ditt CNAME-certifikat upphör att gälla innan Adobe kan distribuera ett förnyat certifikat kommer det att resultera i ett driftavbrott för din specifika [!DNL Target]-implementering.

### Hur länge till mitt nya SSL-certifikat upphör att gälla?

Certifikat som utfärdats före den 1 september 2020 är tvååriga certifikat. Certifikat som utfärdas den 1 september 2020 eller senare kommer att vara ettåriga certifikat. Du kan läsa mer om flytten till ettårscertifikat [här](https://www.digicert.com/position-on-1-year-certificates).

### Vilka värdnamn ska jag välja? Hur många värdnamn per domän ska jag välja?

[!DNL Target] CNAME-implementeringar kräver bara ett värdnamn per domän i SSL-certifikatet och i kundens DNS, så det är vad vi rekommenderar. Vissa kunder kan behöva ytterligare värdnamn per domän för sina egna syften (till exempel testning i mellanlagring), vilket stöds.

De flesta kunder väljer ett värdnamn som `target.example.com`, så det är vad vi rekommenderar, men valet är i slutändan ditt. Var noga med att inte begära ett värdnamn för en befintlig DNS-post, eftersom det skulle orsaka en konflikt och fördröja matchningen av din [!DNL Target] CNAME-begäran.

### Jag har redan en CNAME-implementering för [!DNL Adobe Analytics], kan vi använda samma certifikat eller värdnamn?

Nej, [!DNL Target] kräver ett separat värdnamn och certifikat.

### Påverkas min nuvarande implementering av Target av ITP 2.x?

I en Safari-webbläsare navigerar du till den webbplats där du har ett Target JavaScript-bibliotek. Om du ser en Target-cookie som angetts i kontexten för en CNAME, till exempel `analytics.company.com`, påverkas du inte av ITP 2.x.

ITP-problem kan lösas för Target med bara en CNAME för analys. Du behöver bara ett separat mål-CNAME om det gäller annonsblockerande scenarier där Target är blockerat.

Mer information om ITP finns i [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Vilken typ av tjänstavbrott kan jag förvänta mig när CNAME-implementeringen distribueras?

Det uppstår inga avbrott i tjänsten när certifikatet distribueras (inklusive certifikatförnyelse). När du ändrar värdnamnet i [!DNL Target]-implementeringskoden (`serverDomain` in at.js) till det nya CNAME-värdnamnet (`target.example.com`), kommer webbläsare att behandla återkommande besökare som nya och deras profildata kommer att gå förlorade eftersom den föregående cookien inte är tillgänglig under det gamla värdnamnet (`clientcode.tt.omtrdc.net`) på grund av webbläsarsäkerhetsmodeller. Detta är en engångsavbrott endast på den initiala brytningen till den nya CNAME. Certifikatförnyelser har inte samma effekt eftersom värdnamnet inte ändras.

### Vilken nyckeltyp och certifikatsignaturalgoritm kommer att användas för min CNAME-implementering?

Alla certifikat är RSA SHA-256 och nycklarna är RSA 2048-bitars som standard. Nyckelstorlekar som är större än 2 048 bitar stöds för närvarande inte.

### Hur verifierar jag att CNAME-implementeringen är klar för trafik?

Använd följande kommandouppsättning (i MacOS- eller Linux-kommandoradsterminal med bas och vändning 7.49+):

1. Klistra först in den här basfunktionen i terminalen:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Klistra sedan in det här kommandot (ersätt `target.example.com` med ditt värdnamn):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Om implementeringen är klar bör du se utdata som nedan. Den viktiga delen är att alla rader visar `CN=target.example.com`, som matchar vårt önskade värdnamn. Om någon av dem visar `CN=*.tt.omtrdc.net` är implementeringen **inte** klar.

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
   >Om det här kommandot misslyckas men kommandot `validateEdgeFpsslSni` lyckas kanske du måste vänta tills DNS-uppdateringarna är helt spridda. DNS-poster har en associerad [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) som anger cacheförfallotid för DNS-svar för dessa poster, så du kan behöva vänta minst så länge som dina TTL-värden är aktiva. Du kan använda kommandot `dig target.example.com` eller [G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) för att leta upp dina specifika TTL-värden.

## Kända begränsningar

* QA-läget kommer inte att fastna när du har CNAME och at.js 1.x eftersom det är baserat på en cookie från tredje part. Du kan komma runt problemet genom att lägga till förhandsgranskningsparametrarna i varje URL som du navigerar till. QA-läget är fast när du har CNAME och at.js 2.x.
* För närvarande fungerar inte `overrideMboxEdgeServer`-inställningen korrekt med CNAME när du använder tidigare at.js-versioner än at.js 1.8.2 och at.js 2.3.1. Om du använder en äldre version av at.js ska den anges som `false` för att undvika misslyckade begäranden. Du kan också överväga att [uppdatera at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) till en nyare version som stöds.
* När du använder CNAME blir det mer sannolikt att storleken på cookie-huvudet för Target-anrop ökar. Vi rekommenderar att kakstorleken hålls under 8 kB.
