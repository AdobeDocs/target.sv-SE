---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Information om hur du arbetar med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i Adobe Target.
title: CNAME och Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: a2e4a4d1036d2c56d752d808054f6f4b4ab1d411

---


# CNAME och Adobe Target {#cname-and-adobe-target}

Instruktioner om hur du arbetar med Adobe Client Care för att implementera stöd för CNAME (Canonical Name) i [!DNL Adobe Target]. För att på bästa sätt hantera annonsblockeringsproblem, eller ITP-relaterade cookie-regler, används en CNAME så att samtal görs till en domän som ägs av kunden i stället för till en domän som ägs av Adobe.

## Begär CNAME-stöd

Utför följande steg för att begära CNAME-stöd i [!DNL Target]:

1. Adobes certifikatutfärdare (DigiCert) måste verifiera att Adobe har behörighet att generera certifikat under din domän.

   DigiCert anropar den här processen DCV ( [Domain Control Validation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) ), och Adobe kommer inte att kunna generera något certifikat under din domän förrän processen är slutförd.

   I DCV används några metoder, och det finns några saker du kan göra innan du öppnar en Adobe Client Care-biljett (steg 3) för att snabba upp DCV-processen:

   * DigiCert kommer först att testa e-postmetoden, där de skickar e-post till adresser som finns i domänens WHOIS-information, samt förbestämda e-postadresser (admin, administratör, webbmaster, värdmaster och postmaster `@[domain_name]`). Mer information finns i dokumentationen [för](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) DCV-metoder.

      DigiCert ger följande rekommendation för att påskynda DCV-e-postprocessen:

      &quot;Kontrollera att din registrator/WHOIS-leverantör inte har maskerat eller tagit bort [relevanta e-postadresser]. Om de är det, ta reda på om de tillhandahåller ett sätt (t.ex. anonymiserad e-postadress, webbformulär) för dig att tillåta [certifikatutfärdare] att få tillgång till din domäns WHOIS-data.&quot;

   * Om DCV-e-postmetoden inte är ett alternativ för dig är nästa metod DNS TXT-metoden, där du lägger till en DNS TXT-post i domänen med ett hash-värde. Denna TXT-post anger för DigitalCert att Adobe har behörighet att generera certifikatet. Om du behöver använda den här metoden ska du meddela Adobe Client Care när du öppnar en biljett (steg 3). Detta snabbar upp DCV-processen.

1. Skapa en CNAME-post i domänens DNS som pekar på det vanliga värdnamnet `clientcode.tt.omtrdc.net`. Om klientkoden till exempel är namngiven kund och det värdnamn som föreslås är `target.example.com`, bör din DNS CNAME-post se ut ungefär så här:

   ```
   target.example.com  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Öppna en [Adobe Client Care-biljett där du får CNAME-support](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) för dina [!DNL Target] samtal.

   Adobe arbetar tillsammans med DigitalCert för att köpa och driftsätta ditt certifikat på Adobes produktionsservrar. DigiCert kommer att initiera DCV-processen och Adobe Client Care meddelar dig när implementeringen är klar.

1. När du har slutfört de föregående uppgifterna och Adobe Client Care har meddelat dig att implementeringen är klar, måste du uppdatera `serverDomain` till nya CNAME i at.js.

## Vanliga frågor

Följande information besvarar vanliga frågor om att begära och implementera CNAM-stöd i [!DNL Target]:

### Kan jag tillhandahålla mitt eget certifikat? I så fall, hur är det?

Ja, du kan ange ett eget certifikat för att göra det:

1. Hoppa över steg 1 ovan, men slutför steg 2 och 3. När du öppnar en kundtjänstbiljett från Adobe (steg 3) ska du tala om för dem att du kommer att ge dem ett eget certifikat.

   Adobe genererar och skickar en CSR-fil (Certificate Signing Request).

1. Använd CSR för att köpa certifikatet via den valda certifikatutfärdaren.

1. Skicka det nya offentliga certifikatet till Adobe. Adobe-representanter kommer att distribuera det offentliga certifikatet på sina produktionsservrar.

1. Slutför steg 4 när Adobe Client Care har meddelat dig att implementeringen är klar.

### Jag har redan en CNAME-implementering för [!DNL Adobe Analytics], kan vi använda samma certifikat eller värdnamn?

Nej, [!DNL Target] kräver ett separat värdnamn och certifikat.

### Påverkas min nuvarande implementering av Target av ITP 2.1 eller 2.2?

I en Safari-webbläsare navigerar du till den webbplats där du har ett Target JavaScript-bibliotek. Om du ser en Target-cookie som angetts i samband med en CNAME, till exempel `analytics.company.com`, påverkas du inte av ITP 2.1 eller 2.2.

ITP-problem kan lösas för Target med bara en CNAME för analys. Du behöver bara ett separat mål-CNAME om det gäller annonsblockerande scenarier där Target är blockerat.

Mer information om ITP finns i [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Hur verifierar jag att CNAME-implementeringen är klar för trafik?

Använd följande kommandouppsättning (i MacOS- eller Linux-kommandoradsterminal med bas och vändning 7.49+):

1. Klistra först in den här basfunktionen i terminalen:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..33}}.tt.omtrdc.net; do
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
   mboxedge33.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Validera din nya DNS CNAME med en annan skrivbegäran som även ska visa `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Om det här kommandot misslyckas men kommandot ovan `validateEdgeFpsslSni` lyckas kanske du måste vänta tills DNS-uppdateringarna är helt spridda.
