---
title: Voorinstellingen voor openingspagina definiëren
description: Leer hoe u uw omgeving configureert voor het maken en gebruiken van bestemmingspagina's met Journey Optimizer
role: Admin
level: Intermediate
exl-id: 7cf1f083-bef0-40b5-8ddd-920a9d108eca
source-git-commit: a036f53b88425d64281d2ac530016d638e2d13c9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 2%

---

# Voorinstellingen voor openingspagina definiëren {#lp-presets}

Wanneer [een openingspagina maken](../landing-pages/create-lp.md#create-a-lp), moet u een voorinstelling voor een bestemmingspagina selecteren om de bestemmingspagina te kunnen samenstellen en er doorheen te kunnen gaan **[!DNL Journey Optimizer]**.

## Voorinstellingen voor openingspagina&#39;s openen {#access-lp-presets}

Volg onderstaande stappen om voorinstellingen voor openingspagina&#39;s te openen.

1. Toegang krijgen tot **[!UICONTROL Administration]** > **[!UICONTROL Channels]** -menu.

1. Selecteer **[!UICONTROL Branding]** > **[!UICONTROL Landing page presets]**.

   ![](assets/lp_presets-access.png)

1. Klik op een vooraf ingesteld label voor toegang tot de details van de voorinstelling voor de openingspagina.

   ![](assets/lp_preset-details.png)

## Een voorinstelling voor een openingspagina maken {#lp-create-preset}

Volg onderstaande stappen om een voorinstelling voor een openingspagina te maken.

>[!NOTE]
>
>Als u een voorinstelling wilt maken, moet u ervoor zorgen dat u eerder ten minste één subdomein van de bestemmingspagina hebt geconfigureerd. [Meer informatie](lp-subdomains.md)

1. Toegang krijgen tot **[!UICONTROL Administration]** > **[!UICONTROL Channels]** menu, selecteert u vervolgens **[!UICONTROL Branding]** > **[!UICONTROL Landing page presets]**.

1. Selecteer **[!UICONTROL Create landing page preset]**.

   ![](assets/lp_create-preset-temp.png)

1. Voer een naam en een beschrijving in voor de voorinstelling.

   >[!NOTE]
   >
   > Namen moeten beginnen met een letter (A-Z). Het mag alleen alfanumerieke tekens bevatten. U kunt ook het onderstrepingsteken gebruiken `_`, punt`.` en afbreekstreepje `-` tekens.

1. Selecteer een subdomein van een bestemmingspagina in de vervolgkeuzelijst.

   ![](assets/lp_preset-subdomain.png)

   >[!NOTE]
   >
   >Om een subdomein te kunnen selecteren, zorg ervoor u eerder minstens één het landen paginasubdomain hebt gevormd. [Meer informatie](#lp-subdomains)

   De instellingen die overeenkomen met de geselecteerde subdomeinweergave.

1. Als u het subdomein van de bestemmingspagina als volgende URL wilt selecteren, controleer **[!UICONTROL Same as landing page subdomain]** optie. [Meer informatie over bijhouden](../design/message-tracking.md)

   ![](assets/lp_preset-subdomain-settings-same.png)

   Als de bestemmingspagina-URL bijvoorbeeld &#39;pages.mail.luma.com&#39; is en de URL voor bijhouden &#39;data.mail.luma.com&#39;, kunt u &#39;pages.mail.luma.com&#39; kiezen die u wilt gebruiken als subdomein voor bijhouden.

1. Klikken **[!UICONTROL Submit]** om het maken van de voorinstelling voor de bestemmingspagina te bevestigen. U kunt de voorinstelling ook opslaan als concept en de configuratie ervan later hervatten.

   ![](assets/lp_preset-subdomain-settings-submit.png)

1. Nadat de voorinstelling voor de openingspagina is gemaakt, wordt deze in de lijst weergegeven met de **[!UICONTROL Active]** status. U kunt deze nu gebruiken voor uw bestemmingspagina&#39;s.

   ![](assets/lp-preset-active-temp.png)

U kunt nu [bestemmingspagina&#39;s maken](../landing-pages/create-lp.md) in [!DNL Journey Optimizer].

>[!NOTE]
>
>Leer hoe u berichtvoorinstellingen voor pushmeldingen en e-mailberichten kunt maken in [deze sectie](message-presets.md).

**Verwante onderwerpen**:

* [Aan de slag met bestemmingspagina&#39;s](../landing-pages/get-started-lp.md)
* [Een landingspagina maken](../landing-pages/create-lp.md#create-a-lp)