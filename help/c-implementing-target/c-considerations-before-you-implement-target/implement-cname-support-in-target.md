---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Information om hur du arbetar med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i Adobe Target.
title: CNAME och Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b4b51eabee1b3cac9933ecfc6c94e0de02abb633
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 0%

---


# CNAME och Adobe Target {#cname-and-adobe-target}

Instruktioner för hur du arbetar med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i [!DNL Adobe Target]. För att på bästa sätt hantera annonsblockeringsproblem, eller ITP-relaterade cookie-regler, används en CNAME så att samtal görs till en domän som ägs av kunden i stället för till en domän som ägs av Adobe.

## Begär CNAME-stöd

Utför följande steg för att begära CNAME-stöd i [!DNL Target]:

1. Avgör listan med värdnamn som du behöver för ditt SSL-certifikat (se Vanliga frågor och svar).

1. För varje värdnamn skapar du en CNAME-post i din DNS som pekar på ditt vanliga [!DNL Target] värdnamn `clientcode.tt.omtrdc.net`.

   Om klientkoden till exempel är &quot;namnkund&quot; och det värdnamn som föreslås är `target.example.com`, bör din DNS CNAME-post se ut ungefär så här:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >* Adobes certifikatutfärdare, DigiCert, kan inte utfärda ett certifikat förrän det här steget har slutförts. Därför kan Adobe inte fullfölja din begäran om CNAME-implementering förrän detta steg är klart.


1. Fyll i följande formulär och inkludera det när du [öppnar en Adobe Client Care-biljett som begär CNAME-support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe- [!DNL Target] kundkod:
   * Värdnamn för SSL-certifikat (exempel: `target.example.com target.example.org`):
   * Inköpare av SSL-certifikat (Adobe rekommenderas, se Frågor och svar): Adobe/kund
   * Om kunden köper certifikatet (även kallat BYOC), fyll i dessa ytterligare uppgifter:
      * Certifikatorganisation (exempel: Exempel på Company Inc):
      * Organisationsenhet för certifikat (valfritt, exempel: Marknadsföring):
      * Certifikatland (exempel: USA):
      * Certifikatstatus/region (exempel: Kalifornien):
      * Ort för certifikat (exempel: San Jose):

1. Om Adobe köper certifikatet arbetar Adobe tillsammans med DigiCert för att köpa och distribuera certifikatet på Adobes produktionsservrar.

   Om kunden köper certifikatet (BYOC) skickar Adobe Client Care CSR-filen (Certificate Signing Request) till dig, som du måste använda när du köper certifikatet via den valfria certifikatutfärdaren. När certifikatet har utfärdats måste du skicka en kopia av certifikatet och eventuella mellanliggande certifikat tillbaka till Adobe Client Care för distribution.

   Adobe Client Care meddelar dig när implementeringen är klar.

1. När du har slutfört de föregående uppgifterna och Adobe Client Care har meddelat dig att implementeringen är klar, måste du uppdatera `serverDomain` till nya CNAME i at.js.

## Vanliga frågor

Följande information besvarar vanliga frågor om att begära och implementera CNAME-stöd i [!DNL Target]:

### Kan jag tillhandahålla mitt eget certifikat (även&quot;insert-your-own-certificate&quot; eller&quot;BYOC&quot;)?

Ja, du kan ange ett eget certifikat; rekommenderas dock inte. Hanteringen av SSL-certifikatets livscykel är mycket enklare för både Adobe och dig när Adobe köper och kontrollerar certifikatet. SSL-certifikaten måste förnyas varje år, vilket innebär att Adobe Client Care måste kontakta dig varje år för att skicka ett nytt certifikat till Adobe i tid. Vissa kunder kan få svårt att producera ett förnyat certifikat varje år, vilket äventyrar deras [!DNL Target] implementering eftersom webbläsare kommer att neka anslutningar när certifikatet upphör att gälla.

>[!IMPORTANT]
>
>Tänk på att om du begär en CNAME-implementering med [!DNL Target] ditt eget certifikat ansvarar du för att ge förnyade certifikat till Adobe Client Care varje år. Om du tillåter att ditt CNAME-certifikat upphör att gälla innan Adobe kan distribuera ett förnyat certifikat kommer det att resultera i ett driftstopp för din specifika [!DNL Target] implementering.

### Hur länge till mitt nya SSL-certifikat upphör att gälla?

Certifikat som utfärdats före den 1 september 2020 är tvååriga certifikat. Certifikat som utfärdas den 1 september 2020 eller senare kommer att vara ettåriga certifikat. Du kan läsa mer om övergången till ettårscertifikat [här](https://www.digicert.com/position-on-1-year-certificates).

### Vilka värdnamn ska jag välja? Hur många värdnamn per domän ska jag välja?

[!DNL Target] CNAME-implementeringar kräver bara ett värdnamn per domän i SSL-certifikatet och i kundens DNS, så det är vad vi rekommenderar. Vissa kunder kan behöva ytterligare värdnamn per domän för sina egna syften (till exempel testning i mellanlagring), vilket stöds.

De flesta kunder väljer ett värdnamn som `target.example.com`det, så det är vad vi rekommenderar, men valet är i slutändan ditt. Var noga med att inte begära ett värdnamn för en befintlig DNS-post, eftersom det skulle orsaka en konflikt och fördröja matchningen av din [!DNL Target] CNAME-begäran.

### Jag har redan en CNAME-implementering för [!DNL Adobe Analytics], kan vi använda samma certifikat eller värdnamn?

Nej, [!DNL Target] kräver ett separat värdnamn och certifikat.

### Påverkas min nuvarande implementering av Target av ITP 2.x?

I en Safari-webbläsare navigerar du till den webbplats där du har ett Target JavaScript-bibliotek. Om du ser en Target-cookie som angetts i samband med en CNAME, till exempel `analytics.company.com`, påverkas du inte av ITP 2.x.

ITP-problem kan lösas för Target med bara en Analytics CNAME. Du behöver bara en separat Target CNAME om det gäller annonsblockerande scenarier där Target blockeras.

Mer information om ITP finns i [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Vilken typ av tjänstavbrott kan jag förvänta mig när CNAME-implementeringen distribueras?

Det uppstår inga avbrott i tjänsten när certifikatet distribueras (inklusive certifikatförnyelse). När du ändrar värdnamnet i din [!DNL Target] implementeringskod (`serverDomain` i at.js) till det nya CNAME-värdnamnet (`target.example.com`), kommer webbläsare att behandla återkommande besökare som nya besökare och deras profildata kommer att gå förlorade eftersom den tidigare cookien inte är tillgänglig under det gamla värdnamnet (`clientcode.tt.omtrdc.net`) på grund av säkerhetsmodeller i webbläsaren. Detta är en engångsavbrott endast på den initiala brytningen till den nya CNAME. Certifikatförnyelser har inte samma effekt eftersom värdnamnet inte ändras.

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

   Om implementeringen är klar bör du se utdata som nedan. Den viktiga delen är att alla rader visas, `CN=target.example.com`vilket matchar det önskade värdnamnet. Om något av dem visas `CN=*.tt.omtrdc.net`är implementeringen **inte** klar.

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

1. Validera din nya DNS CNAME med en annan skrivbegäran som även ska visa `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Om det här kommandot misslyckas men kommandot ovan `validateEdgeFpsslSni` lyckas kanske du måste vänta tills DNS-uppdateringarna är helt spridda. DNS-poster har en associerad [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) som anger cacheförfallotid för DNS-svar för dessa poster, så du kan behöva vänta minst så länge som dina TTL-värden är aktiva. Du kan använda `dig target.example.com` kommandot eller [verktygslådan](https://toolbox.googleapps.com/apps/dig/#CNAME) för G Suite för att leta upp dina specifika TTL-filer.

## Kända begränsningar

* QA-läget kommer inte att fastna när du har CNAME och at.js 1.x eftersom det är baserat på en cookie från tredje part. Du kan komma runt problemet genom att lägga till förhandsgranskningsparametrarna i varje URL som du navigerar till. QA-läget är fast när du har CNAME och at.js 2.x.
* För närvarande fungerar inte inställningen som den ska med CNAME. `overrideMboxEdgeServer` Detta bör anges som `false` för att undvika misslyckade begäranden.
