---
keywords: klientvård;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicering;domain control validation;dcv
description: Arbeta med [!DNL Adobe] Kundtjänst för att implementera stöd för CNAME (Canonical Name) i [!DNL Adobe Target] för att hantera annonsblockerande problem.
title: Hur använder jag CNAME i Target?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 0%

---

# CNAME och [!DNL Target]

Instruktioner för att arbeta med [!DNL Adobe] Kundtjänst för att implementera stöd för CNAME (Canonical Name) i [!DNL Adobe Target]. Använd CNAME för att hantera annonsblockeringsproblem eller ITP-relaterade (Intelligent Tracking Prevention) cookie-principer. Med CNAME sker samtal till en domän som ägs av kunden i stället för till en domän som ägs av [!DNL Adobe].

## Begär CNAME-stöd i [!DNL Target]

1. Bestäm listan med värdnamn som du behöver för ditt SSL-certifikat (se Vanliga frågor och svar nedan).

1. För varje värdnamn skapar du en CNAME-post i din DNS som pekar på din vanliga [!DNL Target] värdnamn `clientcode.tt.omtrdc.net`.

   Om klientkoden till exempel är &quot;namnkund&quot; och det föreslagna värdnamnet är `target.example.com`ser din DNS CNAME-post ut ungefär som:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]Certifikatutfärdaren DigiCert kan inte utfärda ett certifikat förrän det här steget har slutförts. Därför [!DNL Adobe] kan inte slutföra din begäran om en CNAME-implementering förrän det här steget är slutfört.

1. [Fyll i det här formuläret](/help/main/assets/FPC_Request_Form.xlsx) och inkludera det när du [öppna ett [!DNL Adobe] Kundtjänstbiljett som begär CNAME-support](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * [!DNL Adobe Target] klientkod:
   * Värdnamn för SSL-certifikat (exempel: `target.example.com target.example.org`):
   * Inköpare av SSL-certifikat ([!DNL Adobe] rekommenderas varmt (se Frågor och svar): Adobe/kund
   * Om kunden köper certifikatet, även kallat &quot;Bring Your Own Certificate&quot; (BYOC), fyll i dessa ytterligare uppgifter:
      * Certifikatorganisation (exempel: Exempel på Company Inc):
      * Organisationsenhet för certifikat (valfritt, exempel: Marknadsföring):
      * Certifikatland (exempel: USA):
      * Certifikatstatus/region (exempel: Kalifornien):
      * Ort för certifikat (exempel: San Jose):

1. If [!DNL Adobe] köper certifikatet, [!DNL Adobe] fungerar med DigiCert för att köpa och distribuera ditt certifikat på [!DNL Adobe]Produktionsservrar.

   Om kunden köper certifikatet (BYOC) [!DNL Adobe] Client Care skickar CSR-begäran (Certificate Signing Request). Använd CSR när du köper certifikatet via den valfria certifikatutfärdaren. När certifikatet har utfärdats skickar du en kopia av certifikatet och eventuella mellanliggande certifikat till [!DNL Adobe] Kundtjänst för driftsättning.

   [!DNL Adobe] Client Care meddelar dig när implementeringen är klar.

1. Uppdatera `serverDomain` ([dokumentation](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)) till den nya CNAME-värdnamnet och uppsättningen `overrideMboxEdgeServer` till `false` ([dokumentation](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)) i din at.js-konfiguration.

## Vanliga frågor

Följande information besvarar vanliga frågor om att begära och implementera CNAME-stöd i [!DNL Target]:

### Kan jag tillhandahålla mitt eget certifikat (ta med ditt eget certifikat eller BYOC)?

Du kan ange ett eget certifikat. Men [!DNL Adobe] rekommenderar inte den här metoden. Hanteringen av SSL-certifikatets livscykel är enklare för båda [!DNL Adobe] och du om [!DNL Adobe] köper och kontrollerar certifikatet. SSL-certifikaten måste förnyas varje år. Därför [!DNL Adobe] Kundtjänst måste kontakta dig varje år för att få ett nytt certifikat i tid. Vissa kunder kan få svårt att snabbt få fram ett förnyat certifikat. Dina [!DNL Target] implementeringen äventyras när certifikatet upphör att gälla eftersom webbläsare inte tillåter anslutningar.

>[!IMPORTANT]
>
>Om du begär en [!DNL Target] CNAME-implementering med eget certifikat, du ansvarar för att tillhandahålla förnyade certifikat för [!DNL Adobe] Kundtjänst varje år. Tillåt att ditt CNAME-certifikat förfaller före [!DNL Adobe] kan distribuera ett förnyat certifikat och resultera i ett driftstopp för din specifika [!DNL Target] implementering.

### Hur länge till mitt nya SSL-certifikat upphör att gälla?

Alla [!DNL Adobe]-köpta certifikat gäller i ett år. Se [DigiCert&#39;s article on 1-year certificates](https://www.digicert.com/blog/position-on-1-year-certificates) för mer information.

### Vilka värdnamn ska jag välja? Hur många värdnamn per domän ska jag välja?

[!DNL Target] CNAME-implementeringar kräver bara ett värdnamn per domän i SSL-certifikatet och i kundens DNS. [!DNL Adobe] rekommenderar ett värdnamn per domän. Vissa kunder kräver fler värdnamn per domän för sina egna syften (till exempel testning i mellanlagring), vilket stöds.

De flesta kunder väljer ett värdnamn som `target.example.com`. [!DNL Adobe] rekommenderar att du följer den här metoden, men valet är i slutändan ditt. Begär inte ett värdnamn för en befintlig DNS-post. Om du gör det uppstår en konflikt och det tar längre tid att lösa dina [!DNL Target] CNAME-begäran.

### Jag har redan en CNAME-implementering för [!DNL Adobe Analytics]kan jag använda samma certifikat eller värdnamn?

Nej, [!DNL Target] kräver ett separat värdnamn och certifikat.

### Är min nuvarande implementering av [!DNL Target] påverkas av ITP 2.x?

Apple ITP (Intelligent Tracking Prevention) version 2.3 innehåller funktionen för hantering av CNAME-insvepning, som kan upptäcka [!DNL Adobe Target] CNAME-implementeringar och reducerar cookie-utgångsdatum till sju dagar. För närvarande [!DNL Target] har ingen lösning för ITP:s hantering av CNAME-insvepning. Mer information om ITP finns i [Apple Intelligent Tracking Prevention (ITP) 2.x](https://developer.adobe.com/target/before-implement/privacy/apple-itp-2x/).

### Vilken typ av tjänstavbrott kan jag förvänta mig när CNAME-implementeringen distribueras?

Det uppstår inga avbrott i tjänsten när certifikatet distribueras (inklusive certifikatförnyelse).

När du har ändrat värdnamnet i [!DNL Target] implementeringskod (`serverDomain` in at.js) till den nya CNAME-värdnamnet (`target.example.com`) behandlas återkommande besökare som nya besökare i webbläsare. Returnerade besökares profildata går förlorade eftersom den tidigare cookien inte är tillgänglig under det gamla värdnamnet (`clientcode.tt.omtrdc.net`). Den tidigare cookien är inte tillgänglig på grund av säkerhetsmodeller i webbläsaren. Denna störning inträffar endast vid den första brytningen till den nya CNAME. Certifikatförnyelser har inte samma effekt eftersom värdnamnet inte ändras.

### Vilken nyckeltyp och certifikatsignaturalgoritm används för min CNAME-implementering?

Alla certifikat är RSA SHA-256 och nycklarna är RSA 2048-bitars som standard. Nyckelstorlekar som är större än 2 048 bitar stöds för närvarande inte.

### Hur verifierar jag att CNAME-implementeringen är klar för trafik?

Använd följande kommandouppsättning (i kommandoradsterminalen i macOS eller Linux, med bash och curl >=7.49):

1. Kopiera och klistra in basfunktionen i terminalen eller klistra in funktionen i den grundläggande startskriptfilen (vanligen `~/.bash_profile` eller `~/.bashrc`) så att funktionen är tillgänglig för alla terminalsessioner:

   ```
   function adobeTargetCnameValidation {
     local hostname="$1"
     if [ -z "$hostname" ]; then
       echo "ERROR: no hostname specified"
       return 1
     fi
   
     local service="Adobe Target CNAME implementation"
     local edges="31 32 34 35 36 37 38"
     local edgeDomain="tt.omtrdc.net"
     local edgeFormat="mboxedge%d%s.$edgeDomain"
     local shardFormat="-alb%02d"
     local shards=5
     local shardsFoundCount=0
     local shardsFound
     local shardsFoundOutput
     local curlRegex="subject:.*CN=|expire date:|issuer:"
     local curlValidation="SSL certificate verify ok"
     local curlResponseValidation='"OK"'
     local curlEndpoint="/uptime?mboxClient=uptime3"
     local url="https://$hostname$curlEndpoint"
     local sslLabsUrl="https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=$hostname"
     local success="✅"
     local failure="🚫"
     local info="🔎"
     local rule="="
     local horizontalRule="$(seq ${COLUMNS:-30} | xargs printf "$rule%.0s")"
     local miniRule="$(seq 5 | xargs printf "$rule%.0s")"
     local curlVersion="$(curl --version | head -1 | cut -d' ' -f2 )"
     local curlVersionRequired=">=7.49"
     local edgeCount="$(wc -w <<< "$edges" | tr -d ' ')"
     local edge
     local shard
     local currEdgeShard
     local dnsOutput
     local cnameExists
     local endToEndTestSucceeded
     local curlResult
   
     for shard in $(seq $shards); do
       if [ "$shardsFoundCount" -eq 0 ]; then
         for edge in $edges; do
           if [ "$shard" -eq 1 ]; then
             currEdgeShard="$(printf "$edgeFormat" "$edge" "")"
           else
             currEdgeShard="$(
               printf "$edgeFormat" "$edge" "$(
                 printf -- "$shardFormat" "$shard"
               )"
             )"
           fi
           curlResult="$(curl -vsm20 --connect-to "$hostname:443:$currEdgeShard:443" "$url" 2>&1)"
           if grep -q "$curlValidation" <<< "$curlResult"; then
             shardsFound+=" $currEdgeShard"
             if grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundCount=$((shardsFoundCount+1))
               shardsFoundOutput+="\n\n$miniRule $success $hostname [edge shard: $currEdgeShard] $miniRule\n"
             else
               shardsFoundOutput+="\n\n$miniRule $failure $hostname [edge shard: $currEdgeShard] $miniRule\n"
             fi
             shardsFoundOutput+="$(grep -E "$curlRegex" <<< "$curlResult" | sort)"
             if ! grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundOutput+="\nERROR: unexpected HTTP response from this shard using $url"
             fi
           fi
         done
       fi
     done
   
     echo
     echo "$horizontalRule"
     echo
     echo "$service validation for hostname $hostname:"
     dnsOutput="$(dig -t CNAME +short "$hostname" 2>&1)"
     if grep -qFi ".$edgeDomain" <<< "$dnsOutput"; then
       echo "$success $hostname passes DNS CNAME validation"
       cnameExists=true
     else
       echo -n "$failure $hostname FAILED DNS CNAME validation -- "
       if [ -n "$dnsOutput" ]; then
         echo -e "$dnsOutput is not in the subdomain $edgeDomain"
       else
         echo "required DNS CNAME record pointing to <target-client-code>.$edgeDomain not found"
       fi
     fi
   
     curlResult="$(curl -vsm20 "$url" 2>&1)"
     if grep -q "$curlValidation" <<< "$curlResult"; then
       if grep -q "$curlResponseValidation" <<< "$curlResult"; then
         echo -en "$success $hostname passes TLS and HTTP response validation"
         if [ -n "$cnameExists" ]; then
           echo
         else
           echo " -- the DNS CNAME is not pointing to the correct subdomain for ${service}s with Adobe-managed certificates" \
             "(bring-your-own-certificate implementations don't have this requirement), but this test passes as configured"
         fi
         endToEndTestSucceeded=true
       else
         echo -n "$failure $hostname FAILED HTTP response validation --" \
           "unexpected response from $url -- "
         if [ -n "$cnameExists" ]; then
           echo "DNS is NOT pointing to the correct shard, notify Adobe Client Care"
         else
           echo "the required DNS CNAME record is missing, see above"
         fi
       fi
     else
   
       echo -n "$failure $hostname FAILED TLS validation -- "
       if [ -n "$cnameExists" ]; then
         echo "DNS is likely NOT pointing to the correct shard or there's a validation issue with the certificate or" \
           "protocols, see curl output below and optionally SSL Labs ($sslLabsUrl):"
         echo ""
         echo "$horizontalRule"
         echo "$curlResult" | sed 's/^/    /g'
         echo "$horizontalRule"
         echo ""
       else
         echo "the required DNS CNAME record is missing, see above"
       fi
     fi
   
     if [ "$shardsFoundCount" -ge "$edgeCount" ]; then
       echo -n "$success $hostname passes shard validation for the following $shardsFoundCount edge shards:"
       echo -e "$shardsFoundOutput"
       echo
   
       if [ -n "$cnameExists" ] && [ -n "$endToEndTestSucceeded" ]; then
         echo "$horizontalRule"
         echo ""
         echo "  For additional TLS/SSL validation, including detailed browser/client support,"
         echo "  see SSL Labs (click the first IP address if prompted):"
         echo ""
         echo "    $info  $sslLabsUrl"
         echo ""
         echo "  To check DNS propagation around the world, see whatsmydns.net:"
         echo ""
         echo "    $info  DNS A records:     https://whatsmydns.net/#A/$hostname"
         echo "    $info  DNS CNAME record:  https://whatsmydns.net/#CNAME/$hostname"
       fi
     else
       echo -n "$failure $hostname FAILED shard validation -- shards found: $shardsFoundCount," \
         "expected: $edgeCount"
       if bc -l <<< "$(cut -d. -f1,2 <<< "$curlVersion") $curlVersionRequired" 2>/dev/null | grep -q 0; then
         echo -n " -- insufficient curl version installed: $curlVersion, but this script requires curl version" \
           "$curlVersionRequired because it uses the curl --connect-to flag to bypass DNS and directly test" \
           "each Adobe Target edge shards' SNI confirguation for $hostname"
       fi
       if [ -n "$shardsFoundOutput" ]; then
         echo -e ":\n$shardsFoundOutput"
       fi
       echo
     fi
     echo
     echo "$horizontalRule"
     echo
   }
   ```

1. Klistra in det här kommandot (ersätter `target.example.com` med ditt värdnamn):

   ```
   adobeTargetCnameValidation target.example.com
   ```

   Om implementeringen är klar visas utdata som nedan. Den viktiga delen är att alla valideringsstatusrader visas `✅` i stället för `🚫`. Varje [!DNL Target] edge CNAME shard should show `CN=target.example.com`, som matchar det primära värdnamnet på det begärda certifikatet (ytterligare SAN-värdnamn på certifikatet skrivs inte ut i dessa utdata).

   ```
   $ adobeTargetCnameValidation target.example.com
   
   ==========================================================
   
   Adobe Target CNAME implementation validation for hostname target.example.com:
   ✅ target.example.com passes DNS CNAME validation
   ✅ target.example.com passes TLS and HTTP response validation
   ✅ target.example.com passes shard validation for the following 7 edge shards:
   
   ===== ✅ target.example.com [edge shard: mboxedge31-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge32-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge34-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge35-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge36-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge37-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge38-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ==========================================================
   
     For additional TLS/SSL validation, including detailed browser/client support,
     see SSL Labs (click the first IP address if prompted):
   
       🔎  https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=target.example.com
   
     To check DNS propagation around the world, see whatsmydns.net:
   
       🔎  DNS A records:     https://whatsmydns.net/#A/target.example.com
       🔎  DNS CNAME record:  https://whatsmydns.net/#CNAME/target.example.com
   
   ==========================================================
   ```

   >[!NOTE]
   >
   >Om det här verifieringskommandot misslyckas vid DNS-validering men du redan har gjort de nödvändiga DNS-ändringarna, kan du behöva vänta tills DNS-uppdateringarna har spridit sig helt. DNS-poster har en associerad [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) som anger cachens förfallotid för DNS-svar för dessa poster. Därför kan du behöva vänta åtminstone så länge som TTL:erna är klara. Du kan använda `dig target.example.com` kommando eller [G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) för att hitta dina specifika TTL:er. Information om hur du kontrollerar DNS-spridning över hela världen finns i [whatsmydns.net](https://whatsmydns.net/#CNAME).

### Hur använder jag en länk för avanmälan med CNAME?

Om du använder CNAME bör länken för avanmälan innehålla &quot;client=`clientcode` parameter, till exempel:
`https://my.cname.domain/optout?client=clientcode`.

Ersätt `clientcode` med klientkoden lägger du sedan till texten eller bilden som ska länkas till [avanmälnings-URL](https://developer.adobe.com/target/before-implement/privacy/privacy/).

## Kända begränsningar

* QA-läget är inte fast när du har CNAME och at.js 1.x eftersom det baseras på en cookie från tredje part. Du kan komma runt problemet genom att lägga till förhandsgranskningsparametrarna i varje URL som du navigerar till. QA-läget är fast när du har CNAME och at.js 2.x.
* När du använder CNAME blir det mer sannolikt att storleken på cookie-huvudet för [!DNL Target] antalet samtal ökar. [!DNL Adobe] rekommenderar att kakstorleken hålls under 8 kB.
