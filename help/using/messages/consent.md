---
title: Weigeren beheren
description: Meer informatie over het beheren van opt-out en privacy
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 1%

---

# Toestemming beheren {#consent}

Gebruiken [!DNL Journey Optimizer] om de toestemming van uw ontvangers voor communicatie te volgen en te begrijpen hoe zij met uw merk willen werken door hun voorkeuren en abonnementen te beheren.

Regels zoals de GDPR bepalen dat u aan specifieke vereisten moet voldoen voordat u informatie van de Onderwerpen van Gegevens kunt gebruiken. Bovendien moeten betrokkenen hun toestemming te allen tijde kunnen wijzigen.

**Waarom is het belangrijk?**

* Als u deze voorschriften niet naleeft, brengt u juridische risico&#39;s met zich mee voor uw merk.
* Het helpt u vermijden verzendend ongevraagde mededelingen naar uw ontvangers, die hen zouden kunnen maken uw berichten als spam merken en uw reputatie schaden.

Meer informatie over het beheren van privacy en de toepasselijke regels in het dialoogvenster [Documentatie Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=&quot;_blank&quot;}.

>[!NOTE]
>
>In [!DNL Journey Optimizer], wordt de toestemming door het Experience Platform afgehandeld [Goedkeuringsschema](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html){target=&quot;_blank&quot;}. Standaard is de waarde voor het veld voor toestemming leeg en wordt deze behandeld als toestemming voor het ontvangen van uw communicatie. U kunt deze standaardwaarde wijzigen terwijl u aan boord gaat tot een van de mogelijke vermelde waarden [hier](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html#choice-values){target=&quot;_blank&quot;}.

## E-mailuitschakelbeheer {#opt-out-management}

Het is een wettelijke vereiste dat ontvangers de mogelijkheid krijgen om zich af te melden voor het ontvangen van communicatie van een merk. Meer informatie over de toepasselijke wetgeving vindt u in het [Documentatie Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html#regulations){target=&quot;_blank&quot;}.

Daarom moet u altijd een **afmelden, koppeling** in elke e-mail die naar ontvangers wordt verzonden:

* Nadat u op deze koppeling hebt geklikt, worden de ontvangers naar een bestemmingspagina gestuurd om te bevestigen dat ze het programma willen afsluiten.
* Na bevestiging van hun keuze worden de gegevens van de profielen bijgewerkt met deze informatie.

### Externe opt-out {#opt-out-external-lp}

Hiervoor kunt u een koppeling naar een externe bestemmingspagina invoegen in een e-mail, zodat gebruikers zich niet meer kunnen abonneren op het ontvangen van communicatie van uw merk.

#### Koppeling voor annuleren toevoegen {#add-unsubscribe-link}

Eerst moet u een afmeldingskoppeling toevoegen aan een bericht. Volg de onderstaande stappen om dit te doen:

1. Bouw uw eigen bestemmingspagina zonder abonnement.

1. De gastheer het op het derdesysteem van uw keus.

1. [Een bericht maken](create-message.md) in [!DNL Journey Optimizer].

1. Selecteer tekst in uw inhoud en [een koppeling invoegen](message-tracking.md#insert-links) gebruiken van de contextafhankelijke werkbalk.

   ![](assets/opt-out-insert-link.png)

1. Selecteren **[!UICONTROL External Opt-out/Unsubscription]** van de **[!UICONTROL Link type]** vervolgkeuzelijst.

   ![](assets/opt-out-link-type.png)

1. In de **[!UICONTROL Link]** , plakt u de koppeling naar de bestemmingspagina van derden.

   ![](assets/opt-out-link-url.png)

1. Klik op **[!UICONTROL Save]**.

1. Sla uw inhoud op en [uw bericht publiceren](publish-manage-message.md).

#### Een API-aanroep voor opt-out implementeren {#opt-out-api}

Als u wilt dat de ontvangers de optie Weigeren kiezen wanneer ze hun keuze op de bestemmingspagina indienen, moet u een **API-oproep voor abonnement** via Adobe I/O om de voorkeuren van de corresponderende profielen bij te werken.

Deze vraag van de POST van Adobe I/O is als volgt:

Eindpunt: platform.adobe.io/journey/imp/consent/preferences

Parameters query:

* **param**: bevat de gecodeerde lading
* **sig**: handtekening
* **pid**: gecodeerde profiel-id

Deze drie parameters worden opgenomen in de URL van de bestemmingspagina van derden die naar de ontvanger wordt verzonden:

![](assets/opt-out-parameters.png)

Eisen voor koptekst:

* x-api-key
* x-gw-ims-org-id
* x-sandbox-name
* autorisatie (gebruikerstoken van uw technische account)

Instantie van aanvraag:

```
{
   "marketing": [
       {
            "type": "email",           
            "choice": "no",          
            "scope": "channel"       
        }
    ],
 
}
```

[!DNL Journey Optimizer] gebruikt u deze parameters om de keuze van het corresponderende profiel bij te werken via de aanroep van Adobe I/O.

#### Bericht verzenden met afmeldingskoppeling {#send-message-unsubscribe-link}

Zodra u de unsubscribe verbinding aan uw landende pagina vormde en de API vraag uitvoerde, is uw bericht klaar om te worden verzonden.

1. Verzend het bericht inclusief de koppeling via een [reis](../building-journeys/journey.md).

1. Zodra het bericht wordt ontvangen, als de ontvanger de unsubscribe verbinding klikt, wordt uw landende pagina getoond.

   ![](assets/opt-out-lp-example.png)

1. Indien de ontvanger het formulier indient (hier door op de **Abonnement opzeggen** (in uw bestemmingspagina), worden de profielgegevens bijgewerkt via [Adobe I/O-oproep](#opt-out-api).

1. De ontvanger van de optie-uit wordt dan opnieuw gericht aan een bevestigingsberichtscherm erop wijzend dat het kiezen uit succesvol was.

   ![](assets/opt-out-confirmation-example.png)

   Dit heeft tot gevolg dat deze gebruiker geen communicatie van uw merk ontvangt, tenzij hij opnieuw een abonnement neemt.

1. Als u wilt controleren of de keuze van het corresponderende profiel is bijgewerkt, gaat u naar het Experience Platform en opent u het profiel door een naamruimte voor identiteiten en een bijbehorende identiteitswaarde te selecteren. Meer informatie in het dialoogvenster [Documentatie Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}.

   ![](assets/opt-out-profile-choice.png)

   In de **[!UICONTROL Attributes]** tab, kunt u de waarde zien voor **[!UICONTROL choice]** is gewijzigd in **[!UICONTROL no]**.

### Eén klik op Weigeren {#one-click-opt-out}

Omdat veel klanten op zoek zijn naar een eenvoudiger proces om hun abonnement op te zeggen, kunt u ook een link met één muisklik toevoegen aan uw e-mailinhoud. Deze verbinding zal uw ontvangers toestaan om van uw mededelingen snel af te zien, zonder aan een landende pagina worden opnieuw gericht waar zij hun keus moeten bevestigen, die het afmeldingsproces versnellen.

Volg onderstaande stappen om een koppeling om te weigeren toe te voegen in uw e-mail.

1. [Een koppeling invoegen](message-tracking.md#insert-links) en selecteert u **[!UICONTROL One click Opt-out]** als het type koppeling.

   ![](assets/message-tracking-opt-out.png)

1. Selecteer hoe u de optie Weigeren wilt toepassen: op het kanaal, de identiteit, of abonnementsniveau.

   ![](assets/message-tracking-opt-out-level.png)

   * **[!UICONTROL Channel]**: De opt-out is van toepassing op toekomstige berichten die naar het doel van het profiel (d.w.z. e-mailadres) voor het huidige kanaal worden verzonden. Als er meerdere doelen aan een profiel zijn gekoppeld, geldt de opt-out voor alle doelen (e-mailadressen) in het profiel voor dat kanaal.
   * **[!UICONTROL Identity]**: De opt-out is van toepassing op toekomstige berichten die worden verzonden naar het specifieke doel (d.w.z. e-mailadres) dat voor het huidige bericht wordt gebruikt.
   * **[!UICONTROL Subscription]**: De opt-out is van toepassing op toekomstige berichten verbonden aan een specifieke abonnementenlijst. Deze optie kan alleen worden geselecteerd als het huidige bericht is gekoppeld aan een abonnementenlijst.

1. Voer de URL in van de bestemmingspagina waarop de gebruiker wordt omgeleid wanneer het abonnement wordt opgezegd. Deze pagina is alleen hier om te bevestigen dat de optie Weigeren is gelukt.

   ![](assets/message-tracking-opt-out-confirmation.png)

   U kunt uw koppelingen aanpassen. Meer informatie over gepersonaliseerde URL&#39;s vindt u in [deze sectie](../personalization/personalization-syntax.md).

1. Sla uw wijzigingen op.

Zodra uw bericht door [reis](../building-journeys/journey.md)Als een ontvanger op de koppeling om te weigeren klikt, wordt zijn profiel onmiddellijk uitgeschakeld.

### Koppeling in berichtkop opzeggen {#unsubscribe-email}

Als de e-mailclient van de ontvangers ondersteuning biedt voor het weergeven van een niet-geabonneerde koppeling in de e-mailheader, worden e-mails verzonden met [!DNL Journey Optimizer] neemt deze koppeling automatisch op.

De koppeling voor afmelden wordt bijvoorbeeld als volgt weergegeven in Gmail:

![](assets/unsubscribe-email.png)

Afhankelijk van de e-mailclient heeft het klikken op de koppeling voor het afmelden van abonnementen in de header een van de volgende gevolgen:

* Het corresponderende profiel wordt direct uitgeschakeld en deze keuze wordt in het Experience Platform bijgewerkt. Meer informatie in het dialoogvenster [Documentatie Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}.

* Dit heeft hetzelfde effect als klikken op de koppeling Abonnement opzeggen in de e-mailinhoud: de ontvanger wordt omgeleid naar een bestemmingspagina met een knop om te bevestigen dat hij of zij het programma afsluit. Meer informatie over beheer van opt-out in [deze sectie](#opt-out-management).

## Push opt-out-beheer {#push-opt-out-management}

Push-ontvangers kunnen hun abonnement opzeggen via hun apparaten zelf.

Ze kunnen er bijvoorbeeld voor kiezen om meldingen te stoppen wanneer ze worden gedownload of wanneer ze uw app gebruiken. Op dezelfde manier kunnen ze de meldingsinstellingen wijzigen via het mobiele besturingssysteem.