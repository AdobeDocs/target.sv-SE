---
keywords: Targeting;eec;visual experience composer;troubleshoot enhanced experience composer;troubleshooting
description: Visningsproblem kan ibland uppstå i Adobe Target Enhanced Experience Composer (EEC) under vissa förhållanden.
title: Felsökning av problem relaterade till Förbättrad Experience Composer
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Felsöka problem med Förbättrad Experience Composer

Visningsproblem kan ibland uppstå i [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) under vissa förhållanden.

## EEG läser inte in en intern QA-URL som inte är tillgänglig på offentlig IP. (Endast EEC) {#section_D29E96911D5C401889B5EACE267F13CF}

Detta kan du lösa genom att tillåtslista följande IP-adresser. De här IP-adresserna är för Adobe-servern som används som proxy för Enhanced Experience Composer. De behövs bara för aktivitetsredigering. Besökare på platsen behöver inte dessa IP-adresser tillåtslista

Be IT-teamet att tillåtslista följande IP-adresser:

| Län | IP-adresser | Värdnamn |
|--- |--- |--- |
| Amerikas förenta stater | 52.55.99.45 | `us1-proxy.adobemc.com` |
| Europa, Mellanöstern och Afrika (EMEA) | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| Asien-Stillahavsområdet (APAC) | 52.193.67.35 | `apac1-proxy.adobemc.com` |

Följande felmeddelande kan visas i Target:

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Följande är orsaker till att du kan se det här felmeddelandet och åtgärda problemet:

* **Problem:** Din webbplatsdomän (ISP) blockerar Förbättrad Experience Composer.

   **Åtgärd:** Tillåtslista IP-adresserna som anges ovan.

* **Problem: IP-** adresserna är tillåtslista men webbplatsen stöder inte TLS version 1.2. Målet använder för närvarande standardkonfigurationen 1.2. Före mål 18.4.1 (25 april 2018) hade standardkonfigurationen stöd för TLS 1.0. Mer information finns i  [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

   **Lösning:** Se följande fråga (Förbättrad Visual Experience Composer läses inte in på säkra sidor på min webbplats som använder TLS 1.2).

## EEC laddas inte på säkra sidor på min webbplats som använder TLS 1.0. (Endast EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Du kan se felmeddelandet som beskrivs ovan i&quot;Den förbättrade Visual Experience Composer läses inte in på säkra sidor på min webbplats.&quot; om IP-adresserna ovan är tillåtslista men webbplatsen inte stöder TLS version 1.2. Målet använder för närvarande standardkonfigurationen 1.2. Före mål 18.4.1 (25 april 2018) hade standardkonfigurationen stöd för TLS 1.0. Mer information finns i [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Så här kontrollerar du TLS-versionen på din webbplats med Firefox (andra webbläsare har liknande steg):

1. Öppna den berörda webbplatsen i Firefox.
1. Klicka på ikonen **[!UICONTROL Show Site Information]** i webbläsarens adressfält.

   ![](assets/firefox_more_info.png)

1. Klicka på **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![](assets/firefox_more_info_2.png)

1. Se TLS-versionsinformationen under Technical Details (Teknisk information):

   ![](assets/firefox_more_info_3.png)

1. Om du ser att TLS 1.0 visas på din webbplats kan du läsa [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) om du vill ha information om TLS-stödprincipen. För att åtgärda detta (gäller till den 12 september 2018) ber vi dig [kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du vill konfigurera med TLS-versionen och domänen.

## Jag ser timeout-fel eller&quot;åtkomst nekad&quot;-fel när webbplatser med proxy aktiverat läses in. (Endast EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Kontrollera att proxy-IP:n inte är blockerade i din miljö.
