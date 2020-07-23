---
keywords: global mbox;target classic;use global mbox from target classic
description: Som standard skapas en global mbox med namnet target-global-mbox, som används för att köra aktiviteter som skapas i Target Standard. Om du redan har skapat en global mbox på dina sidor för dina tidigare implementeringar kan du använda den mbox för dina Target Standarder.
title: Använd en global mbox från en äldre implementering
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Använd en global mbox från en äldre implementering{#use-a-global-mbox-from-a-legacy-implementation}

Som standard skapas en global mbox med namnet target-global-mbox, som används för att köra aktiviteter som skapas i Target Standard. Om du redan har skapat en global mbox på dina sidor för dina tidigare implementeringar kan du använda den mbox för dina Target Standarder.

>[!NOTE]
>
>Du kan bara ha en global mbox per konto.

Om du vill använda din befintliga globala mbox för både [!DNL Target Standard] och den gamla implementeringen måste du ange några parametrar.

1. Gå till [!DNL Target Standard]och klicka sedan på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   Som standard [!UICONTROL Auto Create Global Mbox] är aktiverad och den anpassade globala mbox namnges `target-global-mbox`.
1. Om du vill använda en befintlig mbox inaktiverar du [!UICONTROL Auto Create Global Mbox]och anger namnet på en tidigare skapad global mbox i [!UICONTROL Custom Global Mbox] fältet.

   I den [!UICONTROL Custom Global Mbox] nedrullningsbara listan visas alla kryssrutor på ditt konto. Om du vill använda en mbox som ännu inte finns skapar du mbox i Target Classic.
1. Klicka på **[!UICONTROL Save]**.

   Inställningarna för mbox.js för ditt konto uppdateras.
1. Hämta den nya filen mbox.js och referera till den på din webbplats.

   När du har uppdaterat din produktionsplats med den nya filen mbox.js är du redo att ange dina inställningar.
1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**.
1. I [!UICONTROL Global Mbox] fältet anger du namnet på den globala mbox du valde på sidan Implementering.
1. Klicka på **[!UICONTROL Submit]**.

   Alla befintliga aktiviteter uppdateras till att använda den angivna globala mbox, inklusive aktiviteter som tidigare har skapats och implementerats.
   **Felsökning av implementering** av global Mbox *Varför läses inte den globala mbox in, eller varför finns det fördröjning när den globala mbox läses in?*

Kontrollera att referensen mbox.js är det första JavaScript-anropet på sidan. Andra lösningar på det här problemet finns i Implementering av [Mbox.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).
