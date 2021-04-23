---
keywords: global mbox;target classic;use global mbox from target classic
description: Lär dig hur du använder en äldre global mbox för dina Adobe [!DNL Target] aktiviteter om du redan har skapat en global mbox på dina sidor för dina tidigare implementeringar.
title: Kan jag använda en global mbox från en äldre implementering?
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Använd en global mbox från en äldre implementering

Som standard skapar [!DNL Target] en global mbox med namnet target-global-mbox, som används för att köra aktiviteter som skapats i [!DNL Target]. Om du redan har skapat en global mbox på sidorna för dina tidigare implementeringar kan du använda den mbox för dina [!DNL Target]-aktiviteter.

>[!NOTE]
>
>Du kan bara ha en global mbox per konto.

Om du vill använda din befintliga globala mbox för både [!DNL Target] och den gamla implementeringen måste du ange några parametrar.

1. Gå till [!DNL Target] och klicka sedan på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   Som standard är **[!UICONTROL Page load enabled (Auto-create global mbox]** aktiverat och den anpassade globala mbox heter `target-global-mbox`.

1. Om du vill använda en befintlig mbox inaktiverar du **[!UICONTROL Page load enabled (Auto-create global mbox]** och anger namnet på en tidigare skapad global mbox i fältet **[!UICONTROL Global Mbox]**.

   I listrutan [!UICONTROL Global Mbox] visas alla kryssrutor i ditt konto. Om du vill använda en mbox som ännu inte finns skapar du mbox-filen.

1. Klicka på **[!UICONTROL Save]**.

   Inställningarna för mbox.js för ditt konto uppdateras.

1. Hämta den nya filen at.js och referera till den på din webbplats.

   Alla befintliga aktiviteter uppdateras till att använda den angivna globala mbox, inklusive aktiviteter som tidigare har skapats och implementerats.

## Felsöka global mbox-implementering

Följande vanliga frågor och svar kan användas för att felsöka din globala mbox-implementering:

### Varför läses inte den globala mbox in, eller varför finns det fördröjning i inläsningen av den globala mbox när sidan läses in?

Kontrollera att referensen at.js är det första JavaScript-anropet på sidan. Andra lösningar på det här problemet finns i [Vanliga frågor och svar om den globala rutan](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
