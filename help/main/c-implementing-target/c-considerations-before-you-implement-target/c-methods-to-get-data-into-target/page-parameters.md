---
keywords: implementera;implementera;konfigurera;konfigurera;sidparametrar
description: Hämta data till [!DNL Target] med sidparametrar.
title: Hur får jag in data på [!DNL Target] Använda sidparametrar?
feature: Implementation
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Sidparametrar

Sidparametrar (kallas även&quot;mbox parameters&quot;) är namn/värde-par som skickas direkt via sidkod och som inte lagras i besökarens profil för framtida bruk.

Sidparametrar är användbara när du vill skicka siddata till Target som inte behöver lagras med besökarens profil för framtida målinriktning. Dessa värden används i stället för att beskriva sidan eller den åtgärd som användaren utförde på den specifika sidan.

## Format

Sidparametrar skickas till Target via ett serveranrop som ett strängnamn/värde-par. Parameternamn och värden kan anpassas (även om det finns &quot;reserverade namn&quot; för vissa användningsområden).

### Exempel

* `page=productPage`

* `categoryId=homeLoans`

## Exempel på användningsområden

* **Produktsidor**: Skicka information om den specifika produkten som visas (den här metoden är hur Recommendations fungerar)
* **Beställningsinformation**: Skicka order-ID, orderTotal o.s.v. för ordersamling
* **Kategoritillhörighet**: Skicka kategorivisad information till Target för att skapa kunskap om användarens tillhörighet till särskilda webbplatskategorier
* **data från tredje part**: Skicka information från externa datakällor, som till exempel leverantörer av väderanpassning, kontodata (till exempel DemandBase), demografiska data (till exempel Experience) och mycket mer.

## Fördelar med metoden

Data skickas till Target i realtid och kan användas på samma server för att anropa de data som de kommer i.

## Caveats

* Kräver uppdatering av sidkod (direkt eller via ett tagghanteringssystem).
* Om data måste användas för att rikta in sig på en efterföljande sida/server-anrop måste de översättas till ett profilskript.
* Frågesträngar får endast innehålla tecken enligt [IETF-standard (Internet Engineering Task Force)](https://www.ietf.org/rfc/rfc3986.txt) .

   Förutom de tecken som nämns på IETF-webbplatsen tillåter Target följande tecken i frågesträngar:

   ```< > # % " { } | \ ^ [ ] ` ```

   Allt annat måste vara url-kodat. Standarden anger följande format ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), enligt nedan:

   ![](assets/ietf1.png)

   Eller hela listan för enkelhet:

   ![](assets/ietf2.png)

## Exempel på koder

targetPageParamsAll (bifogar parametrarna till alla mbox-anrop på sidan):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (lägger till parametrarna i den globala mbox på sidan):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

## Länkar till relevant information

Recommendations: [Implementering enligt sidtyp](/help/main/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Orderbekräftelse: [Spåra konverteringar](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Kategoritillhörighet: [Kategoritillhörighet](/help/main/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)