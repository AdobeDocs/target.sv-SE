---
keywords: cookie;cookies;delete cookie;delete target cookie;google chrome;chrome;mozilla firefox;firefox;microsoft edge;safari
description: Ta bort cookies i målwebbläsaren så att du kan validera alla dina upplevelser.
title: Ta bort Adobe Target cookie
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# Ta bort målcookien

Du kan ta bort din [!DNL Adobe Target] webbläsarcookie (mbox) så att du kan validera alla dina upplevelser under testningen.

Om det inte finns någon [!DNL Target]-cookie (mbox) betraktas du som en ny besökare och visas som en ny upplevelse. Det finns flera sätt att ta bort din mbox utan att ta bort alla webbläsarcookies.

>[!NOTE]
>
>Följande instruktioner är korrekta för de webbläsare och versioner som visas. Sök på Internet efter instruktioner om din webbläsare eller version.

## Ta bort målcookien från Google Chrome

Version 84.0.4147.105

1. Klicka på menyn **Chrome** > **Inställningar**.
1. Klicka på fliken **Sekretess och säkerhet**.
1. Klicka på **Cookies och andra webbplatsdata**.
1. Klicka på **Se alla cookies och webbplatsdata**.
1. Expandera avsnittet `adobe.com`, markera **mbox**-cookien och klicka sedan på borttagningsikonen (X).

## Ta bort målcookie från Mozilla Firefox

Version 79.0

### Ta bort alla cookies som är associerade med `adobe.com`

1. Klicka på menyn **Firefox** > **Inställningar**.
1. Klicka på fliken **Sekretess och säkerhet**.
1. Under **Cookies och Site Data** klickar du på **Hantera data**.
1. Markera `adobe.com`-platsen och klicka sedan på **Ta bort markerade**.

   >[!NOTE]
   >
   >Detta tar bort alla cookies som är associerade med `adobe.com`-webbplatsen. Om du vill ta bort en enskild cookie för en webbplats följer du instruktionerna nedan.

### Ta bort en enskild cookie (mbox)

1. I Firefox klickar du på **Verktyg** > **Webbutvecklare** > **Lagringsinspektör**.
1. Klicka på fliken **Avancerat**.
1. Navigera till den webbsida som innehåller den cookie som du vill ta bort.
1. Expandera avsnittet **Cookies** och klicka sedan på `https://experience.adobe.com`.
1. Högerklicka på **mbox**-cookien och klicka sedan på **Ta bort**.

## Ta bort målcookien från Microsoft Edge

Version 84.0.522.52

1. Klicka på menyn **Microsoft Edge** > **Inställningar**.
1. Klicka på fliken **Webbplatsbehörigheter**.
1. Klicka på **Cookies och platsdata**.
1. Klicka på **Se alla cookies och webbplatsdata**.
1. Expandera avsnittet `adobe.com`, markera **mbox**-cookien och klicka sedan på borttagningsikonen (X).

## Ta bort målcookien från Apple Safari

Version 13.1.2

### Ta bort alla cookies som är associerade med `adobe.com`

1. Klicka på menyn **Safari** > **Inställningar**.
1. Klicka på fliken **Sekretess**.
1. Klicka på **Hantera webbplatsdata**.
1. Markera webbplatserna för de cookies som du vill ta bort och klicka sedan på **Ta bort**.

   >[!NOTE]
   >
   >Detta tar bort alla cookies som är associerade med `adobe.com`-webbplatsen. Om du vill ta bort en enskild cookie för en webbplats följer du instruktionerna nedan.

### Ta bort en enskild cookie (mbox)

1. Klicka på menyn **Safari** > **Inställningar**.
1. Klicka på fliken **Avancerat**.
1. Välj **Visa menyn Framkalla i menyraden**.
1. Navigera till den webbsida som innehåller den cookie som du vill ta bort.
1. Klicka på menyn **Utveckla** > **Visa webbinspektören**.
1. Klicka på fliken **Lagring**.
1. Expandera avsnittet **Cookies** och klicka sedan på `www.adobe.com`.
1. Högerklicka på **mbox**-cookien och klicka sedan på **Ta bort**.
