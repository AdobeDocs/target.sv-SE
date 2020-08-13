---
keywords: Implementation;mbox.js non javascript;redirector;costs per click;revenue per click
description: Använd en omdirigerare på liknande sätt som du använder en mbox i dina tester.
title: Arbeta med regissörer
feature: email implementation
subtopic: Getting Started
topic: Standard
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---


# Arbeta med regissörer{#work-with-redirectors}

Använd en omdirigerare på liknande sätt som du använder en mbox i dina tester.

Omdirigeringar skapas med en särskild omdirigerings-URL som läser in en omdirigeringsruta (omdirigerare) till ditt konto. Använd den här omdirigeraren på liknande sätt som du använder en mbox i dina tester. Skicka URL:en för omdirigeraren till annonsnätverket som annonsens mållänk.

Använd omdirigeraren för att göra följande:

* Spåra klick från era webbannonser till er webbplats
* Skapa en central rapport för att spåra klick för att visa annonser i flera annonsnätverk
* Variera displayannonser och destinationer

   Samma banderoller visas till exempel på din hemsida, kategorisida och produktsida.

* Hitta den landningssida som leder till flest konverteringar

Mer information om hur du bestämmer rätt konfiguration finns i [Icke-JavaScript-baserade implementeringar](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Skapa en omdirigerare {#redirector}

Innan du kan använda en omdirigering måste du skapa den.

1. Bestäm annonsens målvariationer, inklusive standarddestinationen.
1. Skapa URL:en för omdirigeraren.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Var `yourclientcode` är företagets kundkod. Ditt företags klientkod är endast liten och har inga specialtecken.

      Klientkoden finns längst upp på [!UICONTROL Administration > Implementation] sidan i [!DNL Target] gränssnittet.

   * `redirectorlink_456` är namnet på den omdirigeringsruta som visas i ditt konto och som ska användas i kampanjer och tester.

      Omdirigeringar fungerar annorlunda jämfört med andra rutor, men visas precis som andra mbox-rutor i ditt konto. Namnge omdirigeraren så att den enkelt kan särskiljas från standardtypsrutorna i ditt konto.  Du bör börja med namnet på mbox med &quot;redirectorlink&quot;.

   * Var `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` är standarddestinationen.

      Detta måste vara URL-kodat och måste vara en absolut referens. Du kan använda [HTML URL-kodningsreferens](https://www.w3schools.com/tags/ref_urlencode.asp) för att snabbt koda dina URL-adresser.

      >[!IMPORTANT]
      >
      >Observera att med Redirector kan du utsättas för en risk för ett Open Redirect-fel. För att undvika obehörig användning av omdirigeringslänkar av tredje part rekommenderar vi att du använder &quot;auktoriserade värdar&quot; för att tillåtslista standarddomänerna för omdirigering av URL. Target använder värdar för att tillåtslista domäner som du vill tillåta omdirigeringar till. Mer information finns i [Skapa Tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till Target](/help/administrating-target/hosts.md#allowlist) i *Hosts*.

1. Validera omdirigeraren.
   1. *Bästa praxis* för säkerhet: Se till att domänen som används i omdirigeraren är tillåtslista, vilket anges ovan. Om du använder en domän som inte är tillåtslista kommer Adobe att blockera alla anrop till den domänen för att förhindra att skadliga aktörer använder omdirigeraren för att dirigera om till potentiellt skadliga domäner.
   1. Infoga URL:en för omdirigeraren i en webbläsare och uppdatera.
   1. Logga in på ditt konto, uppdatera din mbox-lista och verifiera att den nya omdirigeraren är listad som en mbox.
1. Om du ska testa olika destinationer för en annons skapar du [Omdirigeringserbjudanden](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) för varje version.
1. Skapa kampanjen.

   Se [Icke-JavaScript-baserade implementeringar](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) för rätt konfiguration för att uppnå dina mål.
1. Fullständig kvalitetskontroll av kampanjen.

   Skapa en dummy-sida med en `<a href>` som innehåller URL:en för omdirigeraren. Exempel:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Kontrollera att alla upplevelser, standardinnehåll och rapporter fungerar som förväntat i alla webbläsartyper, för alla dina miljöer.

   >[!NOTE]
   >
   >* Omdirigeringar stöds inte av funktionen Förhandsvisa erbjudande eller Bläddra efter mbox. Förhandsgranska upplevelser direkt i en webbläsare.
   >* `mboxDebug` fungerar inte med Redirectors.


1. Skicka den fullständiga URL:en för omdirigeraren till ditt Display Ad Network som annonsmål.

## Använd en omdirigering för att skicka kostnader per klick och intäkt per klick {#concept_3078EF48E9C44B34992D62AAB9628853}

Information om hur du använder en omdirigering för att plocka kostnader per klick och intäkter per klick.

### Löpande kostnader per klick {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Använd en omdirigerare för att skicka kostnaden per klick.

>[!NOTE]
>
>Det bästa sättet är att fastställa kostnadsvärdet med hjälp av **poängen per besök** .

Lägg till `&mboxPageValue=-value` i URL:en. Observera det negativa värdet.

Exempel: För en kostnad på 1,10 cent per klick:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### Passningsintäkt per klick {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Använd en omdirigerare för att skicka intäkten per klick.

>[!NOTE]
>
>Det bästa sättet är att fastställa intäktsvärdet med hjälp av **poängen per besök** .

Lägg till `&mboxPageValue=value` i URL:en.

Exempel: För en intäkt på 1,10 cent per klick.

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
