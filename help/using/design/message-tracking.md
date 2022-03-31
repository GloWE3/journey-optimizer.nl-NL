---
title: Je berichten bijhouden
description: Leer hoe u koppelingen toevoegt en verzonden berichten bijhoudt
feature: Monitoring
topic: Content Management
role: User
level: Intermediate
exl-id: 689e630a-00ca-4893-8bf5-6d1ec60c52e7
source-git-commit: 40c42303b8013c1d9f4dd214ab1acbec2942e094
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Koppelingen toevoegen en berichten bijhouden {#tracking}

Gebruiken [!DNL Journey Optimizer] om koppelingen naar uw inhoud toe te voegen en de verzonden berichten te volgen om het gedrag van de ontvangers te controleren.

## Tekstspatiëring inschakelen {#enable-tracking}

U kunt het bijhouden van wijzigingen op berichtniveau inschakelen door de optie **[!UICONTROL Open Tracking for email]** en/of **[!UICONTROL Click Tracking for email]** opties wanneer [uw bericht maken](../messages/get-started-content.md).

![](assets/message-tracking.png)

>[!NOTE]
>
>Beide opties zijn standaard ingeschakeld.

Zo kunt u het gedrag van de ontvangers bijhouden via:

* **[!UICONTROL Open Tracking for email]**: Berichten die zijn geopend.
* **[!UICONTROL Click Tracking for email]**: Klik op koppelingen in een e-mail.

## Koppelingen invoegen {#insert-links}

Bij het ontwerpen van een bericht kunt u koppelingen naar uw inhoud toevoegen.

>[!NOTE]
>
>Wanneer [tracking is ingeschakeld](#enable-tracking), worden alle koppelingen in de inhoud van het bericht bijgehouden.

Volg onderstaande stappen om koppelingen in te voegen in uw e-mailinhoud:

1. Selecteer een element en klik op **[!UICONTROL Insert link]** in de contextuele werkbalk.

   ![](assets/message-tracking-insert-link.png)

1. Kies het type koppeling dat u wilt maken:

   * **[!UICONTROL External link]**: Voeg een koppeling naar een externe URL in.

   * **[!UICONTROL Landing page]**: Koppelingen naar bestemmingspagina&#39;s invoegen. Meer informatie in [deze sectie](../landing-pages/get-started-lp.md)

   * **[!UICONTROL One click Opt-out]**: Voeg een koppeling in om gebruikers in staat te stellen zich snel af te melden voor uw communicatie zonder dat ze hoeven te bevestigen dat ze het abonnement willen opzeggen. Meer informatie in [deze sectie](../messages/consent.md#one-click-opt-out).

   * **[!UICONTROL External Opt-in/Subscription]**: Voeg een koppeling in om het ontvangen van communicatie van uw merk te accepteren.

   * **[!UICONTROL External Opt-out/Unsubscription]**: Voeg een koppeling in om uw abonnement op te zeggen dat u geen communicatie van uw merk wilt ontvangen. Meer informatie over beheer van opt-out in [deze sectie](../messages/consent.md#opt-out-management).

   * **[!UICONTROL Mirror page]**: Voeg een koppeling in om de e-mailinhoud in een webbrowser weer te geven. Meer informatie in [deze sectie](#mirror-page).

   ![](assets/message-tracking-links.png)

1. U kunt uw koppelingen aanpassen. Meer informatie over gepersonaliseerde URL&#39;s vindt u in [deze sectie](../personalization/personalization-syntax.md#perso-urls).

1. Sla uw wijzigingen op.

1. Als de koppeling eenmaal is gemaakt, kunt u deze nog steeds wijzigen in het menu **[!UICONTROL Component settings]** aan de rechterkant.

   * U kunt de koppeling bewerken en het type van de koppeling wijzigen.
   * U kunt de koppeling onderstrepen of niet door de bijbehorende optie in te schakelen.

   ![](assets/message-tracking-link-settings.png)

## Koppelen naar een spiegelpagina {#mirror-page}

De spiegelpagina is een HTML-pagina die online toegankelijk is via een webbrowser. De inhoud is identiek aan de inhoud van uw e-mail.

Als u een koppeling wilt toevoegen aan een spiegel in uw e-mailbericht, [een koppeling invoegen](#insert-links) en selecteert u **[!UICONTROL Mirror page]** als het type koppeling.

![](assets/message-tracking-mirror-page.png)

De spiegelpagina wordt automatisch gemaakt.

>[!NOTE]
>
>U kunt de automatisch gegenereerde koppeling niet bewerken.

Wanneer de e-mail is verzonden en de ontvangers op de koppeling voor de spiegelpagina klikken, wordt de inhoud van de e-mail in hun standaardwebbrowser weergegeven.

>[!NOTE]
>
>In de [bewijs](preview.md#send-proofs) die naar de testprofielen worden verzonden, is de koppeling naar de spiegelpagina niet actief. Deze wordt alleen geactiveerd in de laatste berichten.

De retentieperiode voor een spiegelpagina is 60 dagen. Na die vertraging is de spiegelpagina niet meer beschikbaar.

## Beheer van bijhouden {#manage-tracking}

De [E-mailontwerper](create-email-content.md) Hiermee kunt u de bijgehouden URL&#39;s beheren, zoals het bewerken van het trackingtype voor elke koppeling.

1. Klik op de knop **[!UICONTROL Links]** in het linkerdeelvenster om de lijst weer te geven met alle URL&#39;s van de inhoud die wordt bijgehouden.

   In deze lijst kunt u een gecentraliseerde weergave gebruiken en elke URL in de e-mailinhoud opzoeken.

1. Als u een koppeling wilt bewerken, klikt u op het bijbehorende potloodpictogram.

   ![](assets/message-tracking-edit-links.png)

1. U kunt de **[!UICONTROL Tracking Type]** indien nodig:

   ![](assets/message-tracking-edit-a-link.png)

   Voor elke bijgehouden URL kunt u de modus Tekstspatiëring instellen op een van de volgende waarden:

   * **[!UICONTROL Tracked]**: Hiermee activeert u het bijhouden van wijzigingen op deze URL.
   * **[!UICONTROL Opt out]**: beschouwt deze URL als een opt-out- of niet-abonnements-URL.
   * **[!UICONTROL Mirror page]**: beschouwt deze URL als een URL van een spiegelpagina.
   * **[!UICONTROL Never]**: Hiermee activeert u het bijhouden van deze URL nooit. <!--This information is saved: if the URL appears again in a future message, its tracking is automatically deactivated.-->

Het aantal berichten dat is geopend en het aantal koppelingen waarop is geklikt, worden vermeld in het dialoogvenster [Tabblad Uitvoeringen](../reports/message-monitoring.md).

Rapportage over openingen en klikken is beschikbaar in de [E-mailLive-rapport](../reports/email-live-report.md) en in de [E-mailglobaal rapport](../reports/email-global-report.md).