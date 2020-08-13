---
description: Ta bort cookies i målwebbläsaren så att du kan validera alla dina upplevelser.
title: Ta bort Adobe Target cookie
feature: privacy and security
topic: Standard
uuid: 6e95ee4d-dbf2-4432-8abe-cfd9bc928f0c
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# Ta bort målcookien{#delete-the-target-cookie}

Du kan ta bort din webbläsarcookie (mbox) så att du kan validera alla dina upplevelser under testningen. [!DNL Target]

Om det inte finns någon [!DNL Target] cookie (mbox) betraktas du som en ny besökare och får en ny upplevelse. Det finns flera sätt att ta bort din mbox utan att ta bort alla webbläsarcookies.

>[!NOTE]
>
>Följande instruktioner är korrekta för de webbläsare och versioner som visas. Sök på Internet efter instruktioner om din webbläsare eller version.

## Ta bort målcookien från Google Chrome

Version 84.0.4147.105

1. Klicka på menyn **Krom** > **Inställningar**.
1. Klicka på fliken **Sekretess och säkerhet** .
1. Klicka på **Cookies och andra webbplatsdata**.
1. Klicka på **Visa alla cookies och webbplatsdata**.
1. Expandera `adobe.com` avsnittet, markera **mbox** -cookien och klicka sedan på borttagningsikonen (X).

## Ta bort målcookie från Mozilla Firefox

Version 79.0

### Ta bort alla cookies som är associerade med `adobe.com`

1. Klicka på **Firefox** -menyn > **Inställningar**.
1. Klicka på fliken **Sekretess och säkerhet** .
1. Klicka på **Hantera data** under **cookies och platsdata**.
1. Markera `adobe.com` platsen och klicka sedan på **Ta bort markerade**.

   >[!NOTE]
   >
   >Detta tar bort alla cookies som är associerade med `adobe.com` platsen. Om du vill ta bort en enskild cookie för en webbplats följer du instruktionerna nedan.

### Ta bort en enskild cookie (mbox)

1. I Firefox klickar du på **Verktyg** > **Webbutvecklare** > **Lagringsinspektör**.
1. Klicka på fliken **Avancerat** .
1. Navigera till den webbsida som innehåller den cookie som du vill ta bort.
1. Expandera avsnittet **Cookies** och klicka sedan på `https://experience.adobe.com`.
1. Högerklicka på **mbox** -cookien och klicka sedan på **Ta bort**.

## Ta bort målcookien från Microsoft Edge

Version 84.0.522.52

1. Klicka på menyn **Microsoft Edge** > **Inställningar**.
1. Klicka på fliken **Webbplatsbehörigheter** .
1. Klicka på **Cookies och webbplatsdata**.
1. Klicka på **Visa alla cookies och webbplatsdata**.
1. Expandera `adobe.com` avsnittet, markera **mbox** -cookien och klicka sedan på borttagningsikonen (X).

## Ta bort målcookien från Apple Safari

Version 13.1.2

### Ta bort alla cookies som är associerade med `adobe.com`

1. Klicka på **Safari** -menyn > **Inställningar**.
1. Klicka på fliken **Sekretess** .
1. Klicka på **Hantera webbplatsdata**.
1. Markera webbplatserna för de cookies som du vill ta bort och klicka sedan på **Ta bort**.

   >[!NOTE]
   >
   >Detta tar bort alla cookies som är associerade med `adobe.com` platsen. Om du vill ta bort en enskild cookie för en webbplats följer du instruktionerna nedan.

### Ta bort en enskild cookie (mbox)

1. Klicka på **Safari** -menyn > **Inställningar**.
1. Klicka på fliken **Avancerat** .
1. Välj menyn **Visa framkallning i menyraden** .
1. Navigera till den webbsida som innehåller den cookie som du vill ta bort.
1. Klicka på menyn **Framkalla** > **Visa webbkontroll**.
1. Klicka på fliken **Lagring** .
1. Expandera avsnittet **Cookies** och klicka sedan på `www.adobe.com`.
1. Högerklicka på **mbox** -cookien och klicka sedan på **Ta bort**.
