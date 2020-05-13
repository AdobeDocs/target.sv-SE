---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Information om hur du arbetar med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i Adobe Target.
title: CNAME och Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 1bcfa02632a13cf1f20a618abb07cae41b49d5ec
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 0%

---


# CNAME och Adobe Target {#cname-and-adobe-target}

Instruktioner för hur du arbetar med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i [!DNL Adobe Target]. För att på bästa sätt hantera annonsblockeringsproblem, eller ITP-relaterade cookie-regler, används en CNAME så att samtal görs till en domän som ägs av kunden i stället för till en domän som ägs av Adobe.

## Begär CNAME-stöd

Utför följande steg för att begära CNAME-stöd i [!DNL Target]:

1. Adobes certifikatutfärdare (DigiCert) måste verifiera att Adobe har behörighet att generera certifikat under din domän.

   DigiCert anropar den här processen DCV ( [Domain Control Validation)](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/), och Adobe kommer inte att kunna generera ett certifikat under din domän förrän den här processen har slutförts för minst en av följande DCV-metoder:

   * Den snabbaste DCV-metoden är DNS CNAME-metoden, där du lägger till en DNS CNAME-post (som innehåller en token) i domänen som pekar på DigiCert-värdnamnet (`dcv.digicert.com`) för DCV. Den här CNAME-posten anger för DigitalCert att Adobe har behörighet att generera certifikatet. Adobe Client Care skickar instruktionerna med nödvändiga DNS-poster. Ett exempel:

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >* Dessa DCV-tokens upphör att gälla efter 30 dagar. Adobe Client Care kommer då att kontakta dig med uppdaterade tokens. Innan du skickar din begäran bör du förbereda dig för att göra de här DNS-ändringarna på alla begärda domäner så att du kan lösa din CNAME-begäran så snabbt som möjligt.
         >
         >
      * Om din domän har [DNS CAA-poster](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)måste du lägga till `digicert.com` om den inte redan har lagts till. Den här DNS-posten anger vilka certifikatutfärdare som har behörighet att utfärda certifikat för domänen. Den resulterande DNS-posten skulle se ut så här: `example.com. IN CAA 0 issue "digicert.com"`. Du kan använda [verktygslådan](https://toolbox.googleapps.com/apps/dig/#CAA) i G Suite för att avgöra om rotdomänen har en befintlig CAA-post. Du kan läsa mer om hur DigitalCert hanterar CAA-poster [här](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check).


   * DigiCert testar också e-postmetoden, i vilken det skickar e-postmeddelanden till adresser som finns i domänens WHOIS-information och till förbestämda e-postadresser (admin, administratör, webbmaster, värdmaster och postmaster `@[domain_name]`). Mer information finns i dokumentationen [för](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) DCV-metoder.

      DigiCert ger följande rekommendation för att påskynda DCV-e-postprocessen:

      &quot;Kontrollera att din registrator/WHOIS-leverantör inte har maskerat eller tagit bort [relevanta e-postadresser]. Om de är det, ta reda på om de tillhandahåller ett sätt (t.ex. anonymiserad e-postadress, webbformulär) för dig att tillåta [certifikatutfärdare] att få tillgång till din domäns WHOIS-data.&quot;

1. Skapa en CNAME-post i domänens DNS som pekar på det vanliga värdnamnet `clientcode.tt.omtrdc.net`. Om klientkoden till exempel är namngiven kund och det värdnamn som föreslås är `target.example.com`, bör din DNS CNAME-post se ut ungefär så här:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Öppna en [Adobe Client Care-biljett där du får CNAME-support](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) för dina [!DNL Target] samtal.

   Adobe arbetar tillsammans med DigitalCert för att köpa och driftsätta ditt certifikat på Adobes produktionsservrar. DigiCert kommer att initiera DCV-processen och Adobe Client Care meddelar dig när implementeringen är klar.

1. När du har slutfört de föregående uppgifterna och Adobe Client Care har meddelat dig att implementeringen är klar, måste du uppdatera `serverDomain` till nya CNAME i at.js.

## Vanliga frågor

Följande information besvarar vanliga frågor om att begära och implementera CNAME-stöd i [!DNL Target]:

### Kan jag tillhandahålla mitt eget certifikat (även&quot;insert-your-own-certificate&quot; eller&quot;BYOC&quot;)? I så fall, hur är det?

Ja, du kan ange ett eget certifikat; rekommenderas dock inte. Hanteringen av SSL-certifikatets livscykel är mycket enklare för både Adobe och dig när Adobe köper och kontrollerar certifikatet. SSL-certifikaten måste förnyas varje år, vilket innebär att Adobe Client Care måste kontakta dig varje år för att skicka ett nytt certifikat till Adobe i tid. Vissa kunder kan få svårt att producera ett förnyat certifikat varje år, vilket äventyrar deras [!DNL Target] implementering eftersom webbläsare kommer att neka anslutningar när certifikatet upphör att gälla.

>[!IMPORTANT]
>
>Tänk på att om du begär en CNAME-implementering med [!DNL Target] ditt eget certifikat ansvarar du för att ge förnyade certifikat till Adobe Client Care varje år. Om du tillåter att ditt CNAME-certifikat upphör att gälla innan Adobe kan distribuera ett förnyat certifikat kommer det att resultera i ett driftstopp för din specifika [!DNL Target] implementering.

1. Hoppa över steg 1 ovan, men slutför steg 2 och 3. När du öppnar en kundtjänstbiljett från Adobe (steg 3) ska du tala om för dem att du kommer att ge dem ett eget certifikat.

   Adobe genererar och skickar en CSR-fil (Certificate Signing Request).

1. Använd CSR för att köpa certifikatet via den valda certifikatutfärdaren.

1. Skicka det nya offentliga certifikatet till Adobe. Adobe-representanter kommer att distribuera det offentliga certifikatet på sina produktionsservrar.

1. Slutför steg 4 när Adobe Client Care har meddelat dig att implementeringen är klar.

### Hur länge till mitt nya SSL-certifikat upphör att gälla?

Certifikat som utfärdats före den 1 september 2020 är tvååriga certifikat. Certifikat som utfärdas den 1 september 2020 eller senare kommer att vara ettåriga certifikat. Du kan läsa mer om övergången till ettårscertifikat [här](https://www.digicert.com/position-on-1-year-certificates).

### Vilka värdnamn ska jag välja? Hur många värdnamn per domän ska jag välja?

[!DNL Target] CNAME-implementeringar kräver bara ett värdnamn per domän i SSL-certifikatet och i kundens DNS, så det är vad vi rekommenderar. Vissa kunder kan behöva ytterligare värdnamn per domän för sina egna syften (till exempel testning i mellanlagring), vilket stöds.

De flesta kunder väljer ett värdnamn som `target.example.com`det, så det är vad vi rekommenderar, men valet är i slutändan ditt. Var noga med att inte begära ett värdnamn för en befintlig DNS-post, eftersom det skulle orsaka en konflikt och fördröja matchningen av din [!DNL Target] CNAME-begäran.

### Jag har redan en CNAME-implementering för [!DNL Adobe Analytics], kan vi använda samma certifikat eller värdnamn?

Nej, [!DNL Target] kräver ett separat värdnamn och certifikat.

### Påverkas min nuvarande implementering av Target av ITP 2.x?

I en Safari-webbläsare navigerar du till den webbplats där du har ett Target JavaScript-bibliotek. Om du ser en Target-cookie som angetts i samband med en CNAME, till exempel `analytics.company.com`, påverkas du inte av ITP 2.x.

ITP-problem kan lösas för Target med bara en CNAME för analys. Du behöver bara ett separat mål-CNAME om det gäller annonsblockerande scenarier där Target är blockerat.

Mer information om ITP finns i [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Kan Adobe/DigiCert skicka DCV-e-postmeddelanden till en annan e-postadress `<someone>@example.com`?

Nej, DigiCert (eller någon certifikatutfärdare) tillåter inte att endast personer med en e-postadress under en domän auktoriserar ett SSL-certifikat under samma domän, såvida inte den e-postadressen också ingår i domänens WHOIS-information eller den förbestämda listan med adresser (se ovan). Detta garanterar att bara behöriga personer kan godkänna DCV för en viss domän. Om detta inte är möjligt för dig rekommenderar vi att du använder DNS CNAME DCV-metoden (se ovan).

### Hur verifierar jag att CNAME-implementeringen är klar för trafik?

Använd följande kommandouppsättning (i MacOS- eller Linux-kommandoradsterminal med bas och vändning 7.49+):

1. Klistra först in den här basfunktionen i terminalen:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
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
   mboxedge17.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge21.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge22.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge26.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge28.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge29.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge30.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
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
