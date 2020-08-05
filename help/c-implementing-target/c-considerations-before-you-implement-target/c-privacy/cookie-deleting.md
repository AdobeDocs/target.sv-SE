---
description: Ta bort cookies i målwebbläsaren så att du kan validera alla dina upplevelser.
title: Ta bort Adobe Target cookie
topic: Standard
uuid: 6e95ee4d-dbf2-4432-8abe-cfd9bc928f0c
translation-type: tm+mt
source-git-commit: 79bcd452a9faa0883272d2e686efd7c4ddfa34a2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---


# Ta bort målcookien{#delete-the-target-cookie}

Du kan ta bort din webbläsarcookie (mbox) så att du kan validera alla dina upplevelser under testningen. [!DNL Target]

Om det inte finns någon [!DNL Target] cookie (mbox) betraktas du som en ny besökare och får en ny upplevelse. Det finns flera sätt att ta bort dina [!DNL Target] cookies utan att ta bort alla dina webbläsarcookies.

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

1. Klicka på **Firefox** -menyn > **Inställningar**.
1. Klicka på fliken **Sekretess och säkerhet** .
1. Klicka på **Hantera data** under **cookies och platsdata**.
1. Markera `adobe.com` platsen och klicka sedan på **Ta bort markerade**.

   >[!NOTE]
   >
   >Detta tar bort alla cookies som är associerade med `adobe.com` platsen. Om du vill ta bort eller redigera enskilda cookies för en plats kan du göra det i [lagringsinspektören för utvecklingsverktygen](https://developer.mozilla.org/en-US/docs/Tools/Storage_Inspector). Den cookie du ska ta bort har namnet&quot;mbox&quot;.

## Ta bort målcookien från Microsoft Edge

Version 84.0.522.52

1. Klicka på menyn **Microsoft Edge** > **Inställningar**.
1. Klicka på fliken **Webbplatsbehörigheter** .
1. Klicka på **Cookies och webbplatsdata**.
1. Klicka på **Visa alla cookies och webbplatsdata**.
1. Expandera `adobe.com` avsnittet, markera **mbox** -cookien och klicka sedan på borttagningsikonen (X).

## Ta bort målcookien från Apple Safari

Version 13.1.2

1. Klicka på **Safari** -menyn > **Inställningar**.
1. Klicka på fliken **Sekretess** .
1. Klicka på **Hantera webbplatsdata**.
1. Markera webbplatserna för de cookies som du vill ta bort och klicka sedan på **Ta bort**.

>[!NOTE]
>
>Detta tar bort alla cookies som är associerade med `adobe.com` platsen. Om du vill ta bort en enskild cookie för en webbplats följer du instruktionerna nedan:

1. Klicka på **Safari** -menyn > **Inställningar**.
1. Klicka på fliken **Avancerat** .
1. Välj menyn **Visa framkallning i menyraden** .
1. Navigera till den webbsida som innehåller den cookie som du vill ta bort.
1. Klicka på menyn **Framkalla** > **Visa webbkontroll**.
1. Klicka på fliken **Lagring** .
1. Expandera avsnittet **Cookies** och klicka sedan på `www.adobe.com`.
1. Högerklicka på **mbox** -cookien och klicka sedan på **Ta bort**.