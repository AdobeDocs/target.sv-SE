---
keywords: cookie;cookies;delete cookie;delete target cookie;google chrome;chrome;mozilla firefox;firefox;microsoft edge;safari
description: Lär dig hur du tar bort [!DNL Target] webbläsarcookies så att ni kan validera era upplevelser.
title: Hur tar jag bort [!DNL Target] Cookie?
feature: Privacy & Security
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Ta bort [!DNL Target] cookie

Du kan ta bort [!DNL Adobe Target] webbläsar-cookie (mbox) så att du kan validera alla dina upplevelser under testningen.

Om det inte finns något [!DNL Target] cookie (mbox) betraktas du som en ny besökare och visas som en ny upplevelse. Det finns flera sätt att ta bort din mbox utan att ta bort alla webbläsarcookies.

>[!NOTE]
>
>Följande instruktioner är korrekta för de webbläsare och versioner som visas. Sök på Internet efter instruktioner om din webbläsare eller version.

## Ta bort [!DNL Target] cookie från Google Chrome

Version 84.0.4147.105

1. Klicka på **Krom** meny > **Inställningar**.
1. Klicka på **Integritet och säkerhet** -fliken.
1. Klicka **Cookies och andra webbplatsdata**.
1. Klicka **Se alla cookies och webbplatsdata**.
1. Expandera `adobe.com` väljer du **mbox** cookie och klicka sedan på borttagningsikonen (X).

## Ta bort [!DNL Target] cookie från Mozilla Firefox

Version 79.0

### Ta bort alla cookies som är associerade med `adobe.com`

1. Klicka på **Firefox** meny > **Inställningar**.
1. Klicka på **Integritet och säkerhet** -fliken.
1. Under **Cookies och webbplatsdata**, klicka **Hantera data**.
1. Välj `adobe.com` plats och klicka sedan på **Ta bort markerade**.

   >[!NOTE]
   >
   >Detta tar bort alla cookies som är kopplade till `adobe.com` webbplats. Om du vill ta bort en enskild cookie för en webbplats följer du instruktionerna nedan.

### Ta bort en enskild cookie (mbox)

1. I Firefox klickar du på **verktyg** > **Webbutvecklare** > **Lagringsinspektör**.
1. Klicka på **Avancerat** -fliken.
1. Navigera till den webbsida som innehåller den cookie som du vill ta bort.
1. Expandera **Cookies** -avsnittet och klicka sedan på `https://experience.adobe.com`.
1. Högerklicka på **mbox** cookie, klicka sedan på **Ta bort**.

## Ta bort [!DNL Target] cookie från Microsoft Edge

Version 84.0.522.52

1. Klicka på **Microsoft Edge** meny > **Inställningar**.
1. Klicka på **Webbplatsbehörigheter** -fliken.
1. Klicka **Cookies och webbplatsdata**.
1. Klicka **Se alla cookies och webbplatsdata**.
1. Expandera `adobe.com` väljer du **mbox** cookie och klicka sedan på borttagningsikonen (X).

## Ta bort [!DNL Target] cookie från Apple Safari

Version 13.1.2

### Ta bort alla cookies som är associerade med `adobe.com`

1. Klicka på **Safari** meny > **Inställningar**.
1. Klicka på **Integritet** -fliken.
1. Klicka **Hantera webbplatsdata**.
1. Markera webbplatserna för de cookies som du vill ta bort och klicka sedan på **Ta bort**.

   >[!NOTE]
   >
   >Detta tar bort alla cookies som är kopplade till `adobe.com` webbplats. Om du vill ta bort en enskild cookie för en webbplats följer du instruktionerna nedan.

### Ta bort en enskild cookie (mbox)

1. Klicka på **Safari** meny > **Inställningar**.
1. Klicka på **Avancerat** -fliken.
1. Välj **Visa menyn Framkalla i menyraden** alternativ.
1. Navigera till den webbsida som innehåller den cookie som du vill ta bort.
1. Klicka på **Utveckla** meny > **Visa webbinspektör**.
1. Klicka på **Lagring** -fliken.
1. Expandera **Cookies** -avsnittet och klicka sedan på `www.adobe.com`.
1. Högerklicka på **mbox** cookie, klicka sedan på **Ta bort**.
