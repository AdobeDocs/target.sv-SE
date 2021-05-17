---
keywords: Rikting;eec;visual experience disposition;felsök förbättrad experience disposition;felsökning
description: Lär dig hur du felsöker problem som ibland kan uppstå i Adobe [!DNL Target] Enhanced Experience Composer (EEC) under vissa förhållanden.
title: Hur felsöker jag problem som rör den förbättrade Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# Felsökning av problem relaterade till [!UICONTROL Enhanced Experience Composer]

Visningsproblem kan ibland uppstå i [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) under vissa förhållanden.

## EEG läser inte in en intern QA-URL som inte är tillgänglig på offentlig IP. {#section_D29E96911D5C401889B5EACE267F13CF}

Detta kan du lösa genom att tillåtslista följande IP-adresser. Dessa IP-adresser är för Adobe server som används som EEG-proxy. De behövs bara för aktivitetsredigering. Besökare på webbplatsen behöver inte tillåtslista dessa IP-adresser.

Be IT-teamet att tillåtslista följande IP-adresser:

* 52.55.99.45
* 52.51.238.221
* 52.193.67.35

Följande felmeddelande kan visas i [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Följande är orsaker till att du kan se det här felmeddelandet och åtgärda problemet:

* **Problem:** Din webbplatsdomän (ISP) blockerar  [!UICONTROL Enhanced Experience Composer].

   **Åtgärd:** Tillåtslista IP-adresserna som anges ovan.

* **Problem: IP-** adresserna är tillåtslista men webbplatsen stöder inte TLS version 1.2.  [!DNL Target] använder för närvarande standardkonfigurationen 1.2. Före  [!DNL Target] 18.4.1 (25 april 2018) hade standardkonfigurationen stöd för TLS 1.0. Mer information finns i  [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

   **Lösning:** Se följande fråga (The  [!UICONTROL Enhanced Visual Experience Composer] will not load on secure pages on my site that use TLS 1.2).

## EEC laddas inte på säkra sidor på min webbplats som använder TLS 1.0. (endast EEG) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Felmeddelandet som beskrivs ovan kan visas i &quot;The [!UICONTROL Enhanced Visual Experience Composer] won&#39;t load on secure pages in my site.&quot; om IP-adresserna ovan är tillåtslista men webbplatsen inte stöder TLS version 1.2. [!DNL Target] använder för närvarande standardkonfigurationen 1.2. Före [!DNL Target] 18.4.1 (25 april 2018) hade standardkonfigurationen stöd för TLS 1.0. Mer information finns i [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Så här kontrollerar du TLS-versionen på din webbplats med Firefox (andra webbläsare har liknande steg):

1. Öppna den berörda webbplatsen i Firefox.
1. Klicka på ikonen **[!UICONTROL Show Site Information]** i webbläsarens adressfält.

   ![](assets/firefox_more_info.png)

1. Klicka på **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![](assets/firefox_more_info_2.png)

1. Se TLS-versionsinformationen under Technical Details (Teknisk information):

   ![](assets/firefox_more_info_3.png)

1. Om du ser att TLS 1.0 visas på din webbplats kan du läsa [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) om du vill ha information om TLS-stödprincipen. För att åtgärda detta (gäller till den 12 september 2018) ber vi dig [kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du vill konfigurera med TLS-versionen och domänen.

## Jag ser timeout-fel eller&quot;åtkomst nekad&quot;-fel när webbplatser med proxy aktiverat läses in. (endast EEG) {#section_60CBB9022DC449F593606C0E6252302D}

Kontrollera att proxy-IP:n inte är blockerade i din miljö.
