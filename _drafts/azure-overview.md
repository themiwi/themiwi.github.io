---
layout: post
title:  "Eine Übersicht zu den Microsoft Azure Diensten"
date:   2021-05-12 11:31:00 +0200
categories: [programming, cloud, azure]
---

## Einleitung

Ich habe selbst schon öfters mit der Azure Cloud gearbeitet. Dabei habe ich
hauptsächlich die "Infrastructure as a Service" (kurz _IaaS_) Dienste, wie
Virtuelle Maschinen und Netzwerke genutzt. Von den "Software as a Service"
(_SaaS_) Diensten beschränkte sich mein Erfahrungshorizont auf den MS SQL
Server. Ich wusste, dass da mehr ist, und hatte auch im Groben einen Überblick
darüber, was sonst noch alles angeboten wird. Aber die Details waren verwirrend,
schon nur weil viele der Namen erstens nicht sehr aussagekräftig sind und
zweitens erhebliche Überlappungen und Verwechslungspotential bieten.

In Diskussionen mit Arbeitskolleg*innen, insbesondere aus dem nicht-technischen,
eher kommerziellen Umfeld, stellte ich fest, dass ich nicht der einzige bin, dem
es so geht. In einer dieser Diskussionen kam dann die Idee auf, eine Übersicht
mit Kurzzusammenfassungen zu allen angebotenen Azure Diensten zu erstellen.
Diese sollte für IT-affine Nicht-Spezialisten, und vor allem
Nicht-Programmierer, zugänglich sein, und sich auf das _WAS_ statt das _WIE_
fokussieren.

Also setzte ich mich hin und wühlte mich durch Unmengen and Marketing-Material
voll von Worthülsen und notierte mir zu jedem der Dienste ein paar Sätze. Ich
orientierte mich dabei an den Gruppierungen der Dienste, wie sie auch von
Microsoft verwendet wird. Allerdings tauchen viele Dienste in den Dokumenten von
Microsoft unter mehren Gruppen auf. Einerseits macht das Sinn, weil die Dienste
in verschiedenen Kontexten genutzt werden können. Aber gleichzeitig leidet
darunter die Übersichtlichkeit. Daher wählte ich die Gruppe, mit der ein Dienst
am stärksten verbunden ist, und beschrieb diesen nur dort. Für die meisten Leser
sollte es eigentlich nach der Lektüre offensichtlich sein, in welchen anderen
Zusammenhängen ein Dienst auch noch sinnvoll eingesetzt werden kann. Wo
nötig, versuchte ich diese zu ähnlichen Diensten abzugrenzen. Aus dieser Arbeit
entstand dann https://wildmichael.github.io/azure-overview.

In diesem Artikel möchte ich diese Übersicht nochmals konzentrierter vorstellen.
Ich werde aber den Schnitt etwas anders anlegen, indem ich beschreibe, _was_ die
Azure Cloud kann. Dazu erwähne ich dann jeweils, welche Dienste dafür genutzt
werden können. Auch werde ich sehr exotische Dienste oder solche, die bald
eingestellt werden, weglassen.

## Rechnerinfrastruktur

Wie in fast jeder anderen Cloud können auch in Azure Rechner bzw. Server als
Dienst gemietet werden. Dies kann notwendig oder von Vorteil sein, wenn sonst
kein Angebot die funktionalen Anforderungen, oder aber auch die
Leistungsanforderungen, erfüllt. Oder z.B. aber auch, wenn Legacy-Anwendungen in
die Cloud migriert werden sollen. Mit all diesen Diensten übernimmt der Kunde
die Verantwortung für Updates und Wartung des Betriebssystems. 

* [CycleCloud]
* [Dedicated Host]
* [Microsoft Azure Virtual Machine Scale Sets]
* [Virtuelle Citrix-Apps und -Desktops für Azure]
* [Virtuelle Computer]
* [VMware Horizon Cloud in Microsoft Azure]
* [VMWare-Lösungen in Azure]
* [Windows Virtual Desktop]

## Netzwerk

Auch dieser Bereich ist aufgrund seiner Diversität und Komplexität sehr gross
und bietet sehr viele Dienste. Da gibt es Dienste zur Erstellung und Verwaltung
von virtuellen Netzwerken zwischen Cloud-Ressourcen wie virtuellen Maschinen,
Applikationen, Containern, etc. Für Webapplikationen gibt es Reverse Proxies,
Firewalls und Load-Balancer. Ein Dienst kombiniert das Content Distribution
Network (CDN) von Azure mit Sicherheitsdiensten wie Web-Application Firewall,
SSL-Offloading und Schutz vor DDoS Angriffen. Es können private Tunnel
eingerichtet werden, um on-premise Netzwerke und Ressourcen mit denen in der
Cloud zu verbinden. Um z.B. Filialen miteinander zu verbinden, können virtuelle
WANs angelegt werden. Der Netzwerkverkehr kann überwacht und gesteuert, die
verwendeten Ressourcen bedarfsgesteuert skaliert werden. Routinginformation kann
automatisch zwischen on-premise und Cloud-Netzwerken ausgetauscht werden.
Entlegene Orte ohne Netzwerkinfrastruktur können mittels Satellitenverbindung in
ein Netzwerk eingebunden werden. Betreiber von eigenen Kommunikationssatelliten
können deren Einsatz, die Erdstationen etc. planen und als eigene Dienste auf
Azure anbieten.

* [Application Gateway]
* [Bastion]
* [DNS]
* [Firewall Manager]
* [Firewall]
* [Front Door]
* [Internet Analyzer]
* [Lastenausgleich]
* [Load Balancer]
* [Network Watcher]
* [Orbital]
* [Private Link]
* [Route Server]
* [Traffic Manager]
* [Virtual Network]
* [Virtual WAN]
* [VPN Gateway]
* [Web Application Firewall]

## Betrieb von Anwendungen

### Hosting von Applikationen

Diese Dienste erlauben dem Kunden den Betrieb von Anwendungen auf von
Microsoft verwalteter Infrastruktur. D.h. der Kunde ist im Gegensatz zu den
zuvor erwähnten Diensten, nicht für die Updates und Wartung des Betriebssystems
verantwortlich.

* [Cloud Services]
* [Mobile Apps]
* [Spring Cloud]
* [SQL Server auf VM]

### Microservices und Container

Für sogenannte _cloud native_ Anwendungen, Microservice und Service-orientierte
Architekturen bieten sich mehrere Dienste, mit teils deutlich überlappender
Funktionalität an. Einerseits leidet da die Übersichtlichkeit, andererseits
kann man sich so die am besten passende Lösung auswählen. Einige der Dienste
erlauben es auch, eher traditionelle Anwendungen in eine Microservice- oder
Cloud-Native-Landschaft zu überführen.

* [Container Instances]
* [Container Registry]
* [Kubernetes Service]
* [Red Hat OpenShift]
* [Service Fabric]
* [Web-App für Container]

### Serverlose Anwendungen

Serverlose Anwendungen sind wohl einen der wichtigsten Innovationen der letzten
Jahre im Cloud Bereich. Obwohl ich hier nur einen einzigen Dienst aufgeführt
habe kann ich gar nicht genügend hervorheben, wie stark serverlose Architekturen
ganze Bereiche der IT transformieren. Mit Azure Functions können
ereignisgesteuerte Funktionen erstellt werden. Diese werden nicht fixen
Ressourcen zugewiesen, sondern die Azure Cloud führt sie auf dynamisch zur
Verfügung gestellten Ressourcen aus und kann diese so auch nach Bedarf
skalieren. Wird die Funktion nicht ausgeführt fallen auch keine Kosten an. Als
weiteren Vorteil lassen sich die Funktionen über sogenannte Bindings rein
deklarativ an Daten-Quellen und Daten-Senken anbinden, ohne dass der
Programmierer die Daten explizit lesen oder schreiben muss. Dadurch fällt sehr
viel Code einfach weg. Es stehen sehr viele Ereignisse zur Verfügung, welche die
Ausführung einer Funktion veranlassen. Dies können z.B. HTTP-Aufrufe,
Datenbankmodifikationen, Änderungen im Blob Storage oder Nachrichten im Event
Grid, IoT Hub, Queue Storage, etc. pp. sein. Ich bin fest davon überzeugt, dass
die Azure Functions die Zukunft der Anwendungsentwicklung und
Unternehmensarchitektur stark beeinflussen und verändern werden. 

* [Functions]

### API's

Moderne Applikations-Architekturen und Designs beherzigen oft den API-first
Ansatz. Dies erlaubt es auch viel einfacher, Dienste miteinander zu verknüpfen
und Automatisierungen zu bauen. So können auch Frontends von dem Backend
getrennt werden, und das Frontend z.B. nur noch als statische Webseite
veröffentlicht werden, welche dann per REST auf eine separate API als Backend
zurückgreift. Sogenannte Microservice- und Service-Mesh-Architekturen, obwohl
nicht gleich, benötigen ein oder mehrere Gateways. Bidirektionale Kommunikation
wird auch immer mehr, z.B. für Chats und Benachrichtigungen, zur Anzeige von
Live-Daten, etc. benötigt. Für all diese Bedürfnisse bietet Microsoft in der
Azure Cloud Dienste.

* [API Management]
* [API-Apps]
* [App Service]
* [SignalR Service]
* [Statische Web-Apps]

## Speicher

### Datenbanken

Eine der wohl wichtigsten Komponenten für eine Vielzahl von Applikationen ist
die Datenbank. Entsprechend gross ist das Angebot, welches verschiedene Formen
des Microsoft-eigenen SQL Server, aber auch verschiedene open-source SQL
Datenbanken und sogenannte No-SQL Datenbanken, wie Key-Value-Stores, Dokumenten-
und Graphendatenbanken, umfasst.

* [API für FHIR] (Gesundheitsdaten)
* [Cache for Redis]
* [Cosmos DB]
* [Database for MariaDB]
* [Database for MySQL]
* [Database for PostgreSQL]
* [Managed Storage für Apache Cassandra]
* [SQL Datenbank]
* [SQL Edge]
* [SQL Managed Instance]
* [Table Storage]

### Andere Speicher

Um Daten in unstrukturierten, z.B. in Dateisystem-ähnlichen Strukturen, zu
speichern gibt es für unterschiedliche Anwendungsszenarien spezialisierte
Dienste. Es können z.B. traditionelle Netzwerklaufwerke in die Cloud migriert
werden. In sogenannten Blob-Speichern können Anwendungen Daten ablegen, für
welche sich eine Datenbank schlecht eignet (z.B. Benutzerbilder oder
Dokumentenuploads). Es können aber auch Archive und Backups gespeichert werden.
Für wissenschaftliche Simulationen stehen speziell schnelle Speicherdienste
bereit.

Sollen Daten sicher mit Drittparteien geteilt werden, stellt auch Microsoft hier
einen Dienst bereit.

* [Archive Storage]
* [Avere vFXT für Azure]
* [Backup]
* [Blob Storage]
* [Data Lake Storage]
* [Data Share]
* [Disk Storage]
* [Files]
* [FXT Edge Filer]
* [HPC Cache]
* [NetApp Files]
* [Queue Storage]
* [Speicher Explorer]
* [StorSimple]

## Mobile

Die meisten in der Azure Cloud angebotenen Dienste lassen sich
selbstverständlich auch im Kontext von Mobile-Apps nutzen, z.B. um deren Backend
zu erstellen. Dennoch bietet Microsoft einige speziell auf die Erstellung von
Mobile-Applikationen ausgerichtete Dienste an. Diese reichen von Karten- und
Navigationsdiensten über Programmier-Bibliotheken und Werkzeugen hin zu
Kommunikationsplattformen, welche es dem Entwickler ermöglichen Video, Chat,
SMS und Telefonie in der App zu nutzen.

* [Communications Services]
* [Maps]
* [Visual Studio App Center]
* [Xamarin]

## Identität

Mit Azure Active Directory bietet Microsoft einen sehr umfangreichen Dienst zur
Authentifizierung und Autorisierung mit modernsten Protokollen wie OpenID
Connect, OAuth 2.0 und Multifaktor-Authentifizierung (MFA). Weiter bietet
Microsoft Domänenkontroller zur Verwaltung von virtuellen Maschinen in der Azure
Cloud bereit. Auch können Zugriffe über Organisationsgrenzen hinweg an externe
Personen, z.B. Kunden oder Partnern gewährt und verwaltet werden.

* [Azure Active Directory Domain Services]
* [Azure Active Directory]
* [Externe Azure Active Directory Identitäten]

## Integration, Messaging, Events

Microsoft bietet mehrere Dienste an, mit denen Applikationen untereinander
mittels Ereignissen und Nachrichten kommunizieren können. Je nach Charakteristik
eignen sich diese eher für seltene grosse und komplexe Datenpakete, oder aber
für kleine Ereignisse in sehr hoher Frequenz. Diese können genutzt werden, um
Applikationen in kleine, lose gekoppelte Teile zu zerlegen oder bestehende
Applikationen miteinander zu integrieren. Die Ereignisse oder Nachrichten können
aber z.B. auch von IoT Geräten erzeugt werden.

* [Event Grid]
* [Event Hubs]
* [Logic Apps]
* [Queue Storage]
* [Service Bus]

## Internet of Things (IoT)

Unter der Flagge _IoT_ bietet Microsoft sehr unterschiedliche Dienste an. Diese
reichen von der Erstellung, Auslieferung und Wartung der Software auf IoT
Geräten über die Verwaltung ebendieser Geräte bis hin zur Datenverarbeitung der
durch die Geräte erzeugten Daten. Microsoft bietet sogar ein eigenes real-time
Betriebssystem für Mikrokontroller an. Natürlich können die Geräte auch
überwacht werden. Um die Geräte und die Kommunikation abzusichern bietet
Microsoft auch mehrere Dienstleistungen an. Weiter können sogenannte Digital
Twins erstellt werden, mit denen ganze Systeme in Echtzeit simuliert werden
können, um z.B. sonst nicht messbare Grössen zu erfassen, die Effizienz von
Anlagen zu maximieren oder deren Wartung zu optimieren. Letztlich können auch
AI/Machine-Learning-Anwendungen auf IoT Geräten eingesetzt und mit den
entsprechenden Diensten in der Cloud integriert werden.

* [Defender for IoT]
* [Digital Twins]
* [IoT Central]
* [IoT Edge]
* [IoT Hub]
* [IoT Solution Accelerators]
* [Percept]
* [RTOS]
* [Sphere]
* [Time Series Insight]
* [Windows 10 IoT Services]

## Analysen

### Big Data Analysen

Microsoft Azure bietet mehrere Dienste zur Verarbeitung von grossen Datenmengen,
welche z.B. aus SQL Datenbanken, aber auch unstrukturierten Dateien bestehen
können. Microsoft setzt hier auf bekannte Open-Source Technologien wie Apache
Spark, Apache Hadoop, Apache HBase, R und Python.

* [Data Factory]
* [Data Lake Analytics]
* [Databricks]
* [Daten-Explorer]
* [HDInsight]
* [Microsoft Graph Data Connect]
* [R-Server for HDInsight]
* [Synapse Analytics]

### Daten-Governance und Verwaltung

Heute werden immer mehr Daten gesammelt. Gerade grosse Organisationen müssen
ihre Daten einerseits gut auffindbar, und damit nutzbar machen. Andererseits
sollen diese aber auch vor unerlaubten Zugriffen geschützt werden.

* [Data Catalog]
* [Pureview]

### Datenstrom-Verarbeitung

Mit diesen Diensten können Daten _on-the-fly_ transformiert und analysiert
werden. Beispiele dafür könnten prädiktive Wartungstools sein, welche
Maschinendaten laufend analysieren um z.B. Anomalien zu entdecken. Diese
Analysen können auch direkt auf Geräten ausserhalb der Cloud, z.B. auf
Maschinensteuerungen, ausgeführt werden.

* [Stream Analytics]

### Log-Daten Analyse

Grosse Applikationen generieren grosse Mengen an Log-Daten. Diese Logs können
unmöglich mehr einzeln gelesen werden, daher müssen sie mit spezialisierten
Tools statistisch analysiert werden.

* [Log Analytics]

### Business Intelligence

In der Azure Cloud gibt es Dienste und Werkzeuge um die eigenen Geschäftsdaten
zu analysieren. Das self-service Analysetool kann aber auch unter eigenem Namen
(d.h. als _white-label_ Produkt) in eigene Produkte eingebaut werden.

* [Analysis Services]
* [Power BI Embedded]

## AI und Machine-Learning

In den letzten Jahren ist das Feld von AI und maschinellem Lernen förmlich
explodiert. Und so ist hat auch Microsoft auf der Azure Cloud ein sehr grosses
Angebot an Diensten, die sich im weitesten Sinne mit künstlicher Intelligenz und
maschinellem Lernen beschäftigen. Microsoft bietet sowohl fix fertige Dienste
"aus der Konserve" an, als auch Unterstützung für den gesamten Lebenszyklus
eigener Modelle und Anwendungen in diesem Bereich. Die Dienste können auch sehr
einfach mit anderen Azure Produkten integriert werden.

### Entwicklung von Modellen und Anwendungen

Microsoft bietet für die Entwicklung von neuen Machine Learning Modellen und
Anwendungen sowohl vorbereitete Infrastruktur, als auch Dienste, welche es
erlauben, mit nur wenig (oder gar keinen) Programmierkenntnissen neue Modelle
oder sogar ganze Anwendungen zu entwickeln.

* [Machine Learning]
* [Project Bonsai]
* [Virtuelle Data-Science Computer]

### Daten

Für die Analyse von Datenreihen bietet Microsoft einen Dienst um Anomalien zu
erkennen, und einen Ratgeber, welcher aufgrund der Daten geeignete Metriken und
KPI vorschlägt, welche dann zur Analyse und Optimierung genutzt werden können.

* [Anomalieerkennung]
* [Metrics Advisor]

### Sprache und Dokumente

Die automatische Analyse und Verarbeitung von natürlicher Sprache und
unstrukturierten Dokumenten nimmt einen grossen Platz ein in der Welt der Azure
ML und KI Dienste. Das fängt bei Text-to-Speech und Speech-to-Text an, geht über
Inhaltsmoderation und Übersetzung hin zu semantischen und Meinungs- bzw.
Stimmungs-Analysen, Erkennung von Formularen und das automatischen Generieren
von Frage-Antwort-Diensten aufgrund von Handbüchern und Dokumentationen.

* [Content Moderator]
* [Formularerkennung]
* [Language Understanding]
* [Plastischer Reader]
* [QnA Maker]
* [Spracherkennung]
* [Sprachübersetzung]
* [Sprechererkennung]
* [Text-to-Speech]
* [Textanalysen]
* [Übersetzer]

### Suche

Einerseits bietet Microsoft die pfannenfertige Bing Suche als Produkt für die
eigenen Daten an, andererseits gibt es auch einen Dienst mit dem man auch eigene
KI-gestützte Suchanwendungen erstellen kann.

* [Bing Websuche]
* [Cognitive Search]

### Bots

Heute binden viele Anwendungen sogenannte Bots ein, welche es dem Benutzer
erlauben mittels natürlicher Sprache mit der Anwendung zu interagieren.
Microsoft selbst setzt diese Technologie z.B. sehr stark in der Teams
Kollaborationsplattform ein. Mit den Bot Services lassen sich ohne viel Aufwand
solche Bots für die eigene Anwendung erstellen. Für den Gesundheitsbereich gibt
es einen spezialisierten Dienst, der z.B. bei der Diagnose und Patiententriage Unterstützung bieten kann.

* [Bot Services]
* [Health Bot]

### Bild und Video

Mit den Azure Diensten zur Bild-Erkennung und Video-Analyse können z.B.
Diagnose-Anwendungen für Industrieprozesse erstellt werden, oder eigene Dienste
welche Gesichtserkennung einsetzen. Bilder und Videos können klassifiziert
werden.

* [Custom Vision]
* [Gesichtserkennung]
* [Maschinelles Sehen]
* [Videoindizierung]

### Weiteres

Weiter gibt es AI und ML Dienste spezialisiert auf Gentechnik und Forschung. Mit
kurierten und aufbereiteten Datensätzen ermöglicht es Microsoft schnell eigene
Modelle zu trainieren. Letztlich gibt es noch einen Dienst, der ein ML Modell
nutzt, um eigenen Anwendungen für die Benutzer, gemäss ihren Bedürfnissen und
Präferenzen, zu personalisieren.

* [Microsoft Genomics]
* [Open Datasets]
* [Personalisierung]

## Mixed Reality

Virtual Reality und Augmented Reality, unter dem neuen Begriff _Mixed Reality_
zusammengefasst, sind mittlerweile in Freizeit und Beruf angekommen. Spiele wie
_Pokémon Go_, Navigationssysteme aber auch ganze Produktionsanlagen, nutzen
mittlerweile die Möglichkeiten, welche VR- und AR-Brillen, Mobiltelefone und
Tablets bieten. Mit den von Microsoft angebotenen Diensten lassen sich virtuelle
Inhalte z.B. an physische Orte oder Objekte binden. Mittels Analyse von Sprache
und maschinellem Sehen lassen sich auch Eingaben erfassen. Das Rendering für
z.B. komplexe 3D-Modelle kann remote in der Cloud erfolgen und die so
entstandenen Bilder auf die Datenbrillen übertragen werden.

* [Kinect DK]
* [Object Anchors]
* [Remote Rendering]
* [Spatial Anchors]

## Multimedia

In der Azure Cloud werden Dienste zur Verarbeitung, Analyse, Verbreitung und
Wiedergabe von Multimedia-Inhalten angeboten, welche z.B. auch schon für die
Übertragung von den Olympischen Spielen genutzt wurden. Weiter können diese
Inhalte mit DRM vor Diebstahl geschützt werden.

* [Codierung]
* [Content Delivery Network]
* [Content Protection]
* [Live Video Analytics]
* [Live- und On-Demand Streaming]
* [Media Player]

## Entwicklerwerkzeuge und DevOps

Für Entwickler bietet Microsoft in Azure einige Dienste an. Einerseits, für das
agile Projektmanagement, Versionskontrolle und Build Server für Continuous
Integration und Deployment, aber auch Dienste, um Softwarepakete für .NET, NPM,
und Python zu veröffentlichen oder im Team zu teilen.  Weiter gibt es Dienste
zur Bereitstellung von standardisierten Entwicklungs- und Testumgebungen.
Manuelle und explorative Tests lassen sich auch planen und protokollieren. All
diese Dienste werden in dem Azure DevOps Portal zusammengefasst.

Für Schulungen, Kurse, Hackathons, etc. lassen sich bedarfsgesteuert
vorkonfigurierte virtuelle Maschinen bereitstellen.

Um Applikationen in Azure Dienste einzubinden und um die Azure Ressourcen
programmgesteuert zu verwalten bietet Microsoft SDK's für eine grosse Anzahl
Programmiersprachen an und stellt Kommandozeilentools für Scripting bereit.
Damit lässt sich das _Infrastructure-as-Code_ Paradigma umsetzen.

Um die Anwendungskonfiguration zu vereinfachen bietet Azure einen Dienst, um
die Parameter zentral zu verwalten.

* [App Configuration]
* [Artifacts]
* [Boards]
* [DevTest Labs]
* [Lab Services]
* [Pipelines]
* [Repos]
* [SDK's]
* [Test Plans]

## Stapelverarbeitung

Viele Applikationen laufen als Stapelverarbeitung. Wie z.B. Lohnabrechnungen,
wissenschaftliche Simulationen oder Berechnen von Portfoliorisiken. Oftmals
benötigen diese Anwendungen viel Rechnerleistung, welche dann zwischen den
Durchläufen brach liegt und Kosten verursacht. Mit diesem Dienst zur
Stapelverarbeitung können die Ressourcen zusätzlich automatisch skaliert werden.

* [Batch]

## Migration

Um grossen Organisationen die komplexe und mit erheblichen Risiken verbundene
Migration in die Cloud zu erleichtern, bietet Microsoft sehr viele Dienste an,
welche z.B. den Betrieb von Legacy-Anwendungen z.B. mittels Lift-and-Shift
ermöglichen. Den Kunden soll der Einstieg ja möglichst leicht gemacht werden.

Um den Gesamtüberblick über die Migration in die Cloud zu behalten, bietet
Microsoft aber auch spezialisierte Dienste an, mit deren Hilfe sich das
Unterfangen Planen lässt. Workloads können ermittelt, bewertet, geplant und
verfolgt werden. Sämtliche Aktionen werden rückverfolgbar aufgezeichnet und
können so für Audits verwendet werden.

Falls sehr grosse Datenmengen in die Cloud migriert werden sollen und dies über
das Netzwerk zu lange dauern würde, stellt Microsoft auch physische Speicher
verschiedener Grösse zur Verfügung, mit welchen die Daten in das
Cloud-Datencenter transportiert werden können.

* [Data Box]
* [Migrate]

## Sicherheit

Hier bietet Microsoft eine Reihe von Diensten an welche von sehr spezialisiert
bis hin zur eierlegenden Wollmilchsau gehen. Es gibt Abwehrmechanismen gegen
DDoS Attacken, hardwarebasierte Sicherheitsmodule, Dienste zum Schutz von
Informationen, Speicher für Anwendungspasswörter, Zertifikate und ähnliches,
aber auch KI-gestützte Analysewerkzeuge. Schliesslich gibt es eine zentrale
Übersicht über die Sicherheit von Azure Diensten und hybriden Ressourcen, welche
auch Berichte für Compliance-Nachweise erstellt. Microsoft bietet auch einen
Dienst zur Sicherstellung der Integrität und Vertrauenswürdigkeit von Ressourcen
ausserhalb der Cloud an, zum Beispiel von Edge Geräten.

* [DDoS Protection]
* [Dedicated HSM]
* [Defender]
* [Information Protection]
* [Key Vault]
* [Microsoft Azure Attestation]
* [Security Center]
* [Sentinel]

## Verwaltung, Automatisierung und Governance

### Automatisierung

In der Azure Cloud lassen sich viele Aufgaben und Dienste automatisieren und
mittels Vorlagen und Schablonen konsistent und vereinfacht erstellen.

* [Automanage]
* [Automation]
* [Blueprint]
* [Cloud Shell]
* [Resource Mover]
* [Vorlagen für Azure Resource Manager]

### Governance

Microsoft unterstützt seine Kunden bei der Erstellung, Erzwingung und
Überwachung von Richtlinien in der Cloud und für on-premise Ressourcen. Ein
Ratgeber erteilt automatisch Vorschläge zur Verbesserung der Zuverlässigkeit,
Sicherheit, Leistung und Senkung von Kosten. Die Zugriffsrechte auf Daten kann für
Personen und Systeme innerhalb und ausserhalb der eigenen Organisation gesteuert
und überwacht werden.

* [Advisor]
* [Lighthouse]
* [Policy]

### Verwaltung und Überwachung

Für den Betrieb von Anwendungen und Ressourcen in der Cloud bietet Microsoft
Dienste zur Überwachung, Kostenverrechnung und Wiederherstellung. Mit der
Mobile-App können viele dieser Aufgaben auch unterwegs erledigt werden.

* [Mobile App]
* [Monitor]
* [Service Health]
* [Site Recovery]
* [Cost Management und Abrechnung]

## Hybrid und Multicloud

Viele Anwendungsszenarien verlangen, dass Azure Ressourcen mit Computern,
Programmen oder Geräten ausserhalb der Cloud zusammenarbeiten. Z.B. können das
IoT Geräte (wie Anlagensteuerungen, Messanlagen, etc.), Kassensysteme, noch
nicht in die Cloud migrierte on-premise Dienste, etc. pp. sein. Oder aber eine
Organisation will sich nicht auf einen Cloud-Anbieter festlegen, möglicherweise
werden aus Verfügbarkeitsgründen sogar die gleichen Applikationen in mehreren
Clouds redundant betrieben. All diese Szenarien stellen besondere
Herausforderungen an das Verwalten der Dienste, die Überprüfung von Policies und
Compliance Richtlinien und die Sicherheit. Mit den von Microsoft angebotenen
Diensten kann man diese Aufgaben unter einer vereinheitlichten, zentralen Stelle
aus erfüllen. Andere Dienste von Microsoft in diesem Themenfeld ermöglichen es,
Azure Dienste auch ausserhalb der Cloud zu nutzen, z.B. auf Edge-Geräten, im
eigenen Datacenter oder an Orten ohne Netzwerkanbindung.

* [Arc]
* [ExpressRoute]
* [Modular Datacenter]
* [Stack Edge]
* [Stack HCI]
* [Stack Hub]
* [Stack]

## Anbieten eigener Dienste

Microsoft hat das Azure-Ökosystem auch für Drittanbieter geöffnet, die selbst
eigene Dienste und Ressourcen anbieten können.

* [Managed Applications]

## Abschliessende Gedanken

Wie ersichtlich, ist die Anzahl der Dienste und die von ihnen abgedeckten
Themenfelder sehr gross. Für mich die einfacheren sind diejenigen, welche sich
auf die "Lift-and-Shift" Szenarien beziehen. D.h. bestehende Anwendungen und
Ressourcen werden mit möglichst wenig Modifikation und Aufwand in die Cloud
migriert. Allerdings kann dies nur der erste Schritt sein. Man spart sich
dadurch bestenfalls die Investitionskosten in eigene Hardware und deren Wartung,
aber weder verbessert sich die Unternehmens- noch die Applikationsarchitektur
und eine Integration in andere Dienste ist immer noch schwierig. Eine echte
Cloud-Strategie sollte diese Dienste nur für eine Übergangsphase als tragend
betrachten.

Die Herausforderung liegt dann darin, die Anwendungen "neu zu denken" und die
bekannten Trampelpfade zu verlassen. Die vielen Legobausteine wollen geschickt
kombiniert werden, um viel rascher und mit sehr wenig Code zu ausgereiften
und robusten Lösungen zu kommen. Die Gefahr liegt darin, dass man dazu tendiert,
vertraute Lösungsansätze zu bevorzugen und so den Lösungsraum unnötig und
ungünstig einschränkt. Andererseits eignet sich der gerade zuletzt erlernte
Dienst nicht für alle Anwendungen &ndash; das Problem des sprichwörtlichen
Jungen mit einem Hammer, für den jeder Gegenstand wie ein Nagel ausschaut. Hier
lohnt es sich den Spieltrieb auszuleben, die neuen Möglichkeiten in kleinen
Prototypen und "Wegwerfprojekten" auszuprobieren und deren Vor- und Nachteile zu
erforschen. Aus dem einfachen Grund, dass man das, was man nicht kennt, auch
nicht sinnvoll einsetzen kann.

[Azure Active Directory Domain Services]: https://azure.microsoft.com/de-de/services/active-directory-ds/
[Azure Active Directory]: https://azure.microsoft.com/de-de/services/active-directory/
[Advisor]: https://azure.microsoft.com/de-de/services/advisor/
[Analysis Services]: https://azure.microsoft.com/de-de/services/analysis-services/
[Anomalieerkennung]: https://azure.microsoft.com/de-de/services/cognitive-services/anomaly-detector/
[Apache Cassandra]: https://cassandra.apache.org/
[API für FHIR]: https://azure.microsoft.com/de-de/services/azure-api-for-fhir/
[API Management]: https://azure.microsoft.com/de-de/services/api-management/
[API-Apps]: https://azure.microsoft.com/de-de/services/app-service/api/
[App Configuration]: https://azure.microsoft.com/de-de/services/app-configuration/
[App Service]: https://azure.microsoft.com/de-de/services/app-service
[Application Gateway]: https://azure.microsoft.com/de-de/services/application-gateway/
[Arc]: https://azure.microsoft.com/de-de/services/azure-arc/
[Archive Storage]: https://azure.microsoft.com/de-de/services/storage/archive/
[Artifacts]: https://azure.microsoft.com/de-de/services/devops/artifacts/
[Automanage]: https://azure.microsoft.com/de-de/services/azure-automanage/
[Automation]: https://azure.microsoft.com/de-de/services/automation/
[Avere vFXT für Azure]: https://azure.microsoft.com/de-de/services/storage/avere-vfxt/
[Backup]: https://azure.microsoft.com/de-de/services/backup/
[Bastion]: https://azure.microsoft.com/de-de/services/azure-bastion/
[Batch]: https://azure.microsoft.com/de-de/services/batch/
[Bing Websuche]: https://www.microsoft.com/en-us/bing/apis
[Blob Storage]: https://azure.microsoft.com/de-de/services/storage/blobs/
[blockchain retirement]: https://docs.microsoft.com/azure/blockchain/service/migration-guide
[Blockchain Tokens]: https://azure.microsoft.com/en-us/services/blockchain-tokens/
[Blockchain Workbench]: https://azure.microsoft.com/features/blockchain-workbench/
[Blockchain-Dienst]: https://azure.microsoft.com/de-de/services/blockchain-service/
[Blueprint]: https://azure.microsoft.com/de-de/services/blueprints/
[Boards]: https://azure.microsoft.com/de-de/services/devops/boards/
[Bot Services]: https://azure.microsoft.com/de-de/services/bot-services/
[Cache for Redis]: https://azure.microsoft.com/de-de/services/cache/
[Cloud Services]: https://azure.microsoft.com/de-de/services/cloud-services/
[Cloud Shell]: https://azure.microsoft.com/de-de/features/cloud-shell/
[Codierung]: https://azure.microsoft.com/de-de/services/media-services/encoding/
[Cognitive Search]: https://azure.microsoft.com/de-de/services/search/
[Cognitive Services]: https://azure.microsoft.com/de-de/services/cognitive-services/
[Communications Services]: https://azure.microsoft.com/de-de/services/communication-services/
[Container Instances]: https://azure.microsoft.com/de-de/services/container-instances/
[Container Registry]: https://azure.microsoft.com/de-de/services/container-registry/
[Content Delivery Network]: https://azure.microsoft.com/de-de/services/cdn/
[Content Moderator]: https://azure.microsoft.com/de-de/services/cognitive-services/content-moderator/
[Content Protection]: https://azure.microsoft.com/de-de/services/media-services/content-protection/
[Cosmos DB]: https://azure.microsoft.com/de-de/services/cosmos-db/
[Cost Management und Abrechnung]: https://azure.microsoft.com/de-de/services/cost-management/
[Custom Vision]: https://azure.microsoft.com/de-de/services/cognitive-services/custom-vision-service/
[CycleCloud]: https://azure.microsoft.com/features/azure-cyclecloud/
[Data Box]: https://azure.microsoft.com/de-de/services/databox/
[Data Catalog]: https://azure.microsoft.com/de-de/services/data-catalog/
[Data Factory]: https://azure.microsoft.com/de-de/services/data-factory/
[Data Lake Analytics]: https://azure.microsoft.com/de-de/services/data-lake-analytics/
[Data Lake Storage]: https://azure.microsoft.com/de-de/services/storage/data-lake-storage/
[Data Share]: https://azure.microsoft.com/de-de/services/data-share/
[Database for MariaDB]: https://azure.microsoft.com/de-de/services/mariadb/
[Database for MySQL]: https://azure.microsoft.com/de-de/services/mysql/
[Database for PostgreSQL]: https://azure.microsoft.com/de-de/services/postgresql/
[Database Migration Service]: https://azure.microsoft.com/de-de/services/database-migration/
[Databricks]: https://azure.microsoft.com/de-de/services/databricks/
[Daten-Explorer]: https://azure.microsoft.com/de-de/services/data-explorer/
[DDoS Protection]: https://azure.microsoft.com/de-de/services/ddos-protection/
[Dedicated Host]: https://azure.microsoft.com/de-de/services/virtual-machines/dedicated-host/
[Dedicated HSM]: https://azure.microsoft.com/de-de/services/azure-dedicated-hsm/
[Defender for IoT]: https://azure.microsoft.com/de-de/services/azure-defender-for-iot/
[Defender]: https://azure.microsoft.com/de-de/services/azure-defender/
[DevTest Labs]: https://azure.microsoft.com/de-de/services/devtest-lab/
[Digital Twins]: https://azure.microsoft.com/de-de/services/digital-twins/
[Disk Storage]: https://azure.microsoft.com/de-de/services/storage/disks
[DNS]: https://azure.microsoft.com/de-de/services/dns/
[etcd]: https://etcd.io/
[Event Grid]: https://azure.microsoft.com/de-de/services/event-grid/
[Event Hubs]: https://azure.microsoft.com/de-de/services/event-hubs/
[ExpressRoute]: https://azure.microsoft.com/de-de/services/expressroute/
[Externe Azure Active Directory Identitäten]: https://azure.microsoft.com/de-de/services/active-directory/external-identities/
[Files]: https://azure.microsoft.com/de-de/services/storage/files/
[Firewall Manager]: https://azure.microsoft.com/de-de/services/firewall-manager/
[Firewall]: https://azure.microsoft.com/de-de/services/azure-firewall/
[Formularerkennung]: https://azure.microsoft.com/de-de/services/cognitive-services/form-recognizer/
[Front Door]: https://azure.microsoft.com/de-de/services/frontdoor/
[Functions]: https://azure.microsoft.com/de-de/services/functions/
[FXT Edge Filer]: https://azure.microsoft.com/de-de/services/fxt-edge-filer/
[Gesichtserkennung]: https://azure.microsoft.com/de-de/services/cognitive-services/face/
[Gremlin]: https://tinkerpop.apache.org/
[HDInsight]: https://azure.microsoft.com/de-de/services/hdinsight
[Health Bot]: https://azure.microsoft.com/de-de/services/bot-services/health-bot/
[HIPAA BAA]: https://docs.microsoft.com/en-us/compliance/regulatory/offering-hipaa-hitech
[HL7-FHIR]: https://www.hl7.org/fhir/
[HPC Cache]: https://azure.microsoft.com/de-de/services/hpc-cache/
[Information Protection]: https://azure.microsoft.com/de-de/services/information-protection/
[Internet Analyzer]: https://azure.microsoft.com/de-de/services/internet-analyzer/
[IoT Central]: https://azure.microsoft.com/de-de/services/iot-central/
[IoT Edge]: https://azure.microsoft.com/de-de/services/iot-edge/
[IoT Hub]: https://azure.microsoft.com/de-de/services/iot-hub/
[IoT Solution Accelerators]: https://azure.microsoft.com/de-de/features/iot-accelerators/
[Key Vault]: https://azure.microsoft.com/de-de/services/key-vault/
[Kinect DK]: https://azure.microsoft.com/de-de/services/kinect-dk/
[Kubernetes Service]: https://azure.microsoft.com/de-de/services/kubernetes-service/
[Lab Services]: https://azure.microsoft.com/de-de/services/lab-services/
[Language Understanding]: https://azure.microsoft.com/de-de/services/cognitive-services/language-understanding-intelligent-service/
[Lastenausgleich]: https://azure.microsoft.com/de-de/products/azure-load-balancing/
[Lighthouse]: https://azure.microsoft.com/de-de/services/azure-lighthouse/
[Live Video Analytics]: https://azure.microsoft.com/de-de/services/media-services/live-video-analytics/
[Live- und On-Demand Streaming]: https://azure.microsoft.com/de-de/services/media-services/live-on-demand/
[Load Balancer]: https://azure.microsoft.com/de-de/services/load-balancer/
[Log Analytics]: https://docs.microsoft.com/azure/azure-monitor/logs/log-analytics-overview
[Logic Apps]: https://azure.microsoft.com/de-de/services/logic-apps/
[Machine Learning]: https://azure.microsoft.com/de-de/services/machine-learning/
[Managed Applications]: https://azure.microsoft.com/de-de/services/managed-applications/
[Managed Storage für Apache Cassandra]: https://azure.microsoft.com/de-de/services/managed-instance-apache-cassandra/
[Maps]: https://azure.microsoft.com/de-de/services/azure-maps/
[MariaDB]: https://mariadb.org/
[Maschinelles Sehen]: https://azure.microsoft.com/de-de/services/cognitive-services/computer-vision/
[MAUI]: https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui/
[Media Player]: https://azure.microsoft.com/de-de/services/media-services/media-player/
[Metrics Advisor]: https://azure.microsoft.com/en-us/services/cognitive-services/metrics-advisor/
[Microsoft Azure Attestation]: https://azure.microsoft.com/de-de/services/azure-attestation/
[Microsoft Azure Portal]: https://azure.microsoft.com/de-de/features/azure-portal/
[Microsoft Azure Virtual Machine Scale Sets]: https://azure.microsoft.com/de-de/services/virtual-machine-scale-sets/
[Microsoft Genomics]: https://azure.microsoft.com/de-de/services/genomics/
[Microsoft Graph Data Connect]: https://azure.microsoft.com/de-de/services/graph-data-connect/
[Microsoft HoloLens 2]: https://www.microsoft.com/de-de/hololens
[Migrate]: https://azure.microsoft.com/de-de/services/azure-migrate/
[Mobile App]: https://azure.microsoft.com/de-de/features/azure-portal/mobile-app/
[Mobile Apps]: https://azure.microsoft.com/de-de/services/app-service/mobile/
[Modular Datacenter]: https://azure.microsoft.com/de-de/products/azure-modular-datacenter/
[MongoDB]: https://www.mongodb.com/
[Monitor]: https://azure.microsoft.com/de-de/services/monitor/
[MySQL]: https://www.mysql.com/
[NetApp Files]: https://azure.microsoft.com/de-de/services/netapp/
[Network Watcher]: https://azure.microsoft.com/de-de/services/network-watcher/
[Object Anchors]: https://azure.microsoft.com/de-de/services/object-anchors/
[Open Datasets]: https://azure.microsoft.com/de-de/services/open-datasets/
[Orbital]: https://azure.microsoft.com/de-de/services/orbital/
[Percept]: https://azure.microsoft.com/de-de/services/azure-percept/
[Personalisierung]: https://azure.microsoft.com/de-de/services/cognitive-services/personalizer/
[Pipelines]: https://azure.microsoft.com/de-de/services/devops/pipelines/
[Plastischer Reader]: https://azure.microsoft.com/de-de/services/cognitive-services/immersive-reader/
[Policy]: https://azure.microsoft.com/de-de/services/azure-policy/
[PostgreSQL]: https://www.postgresql.org/
[Power BI Embedded]: https://azure.microsoft.com/de-de/services/power-bi-embedded
[Private Link]: https://azure.microsoft.com/de-de/services/private-link/
[Project Bonsai]: https://azure.microsoft.com/de-de/services/project-bonsai/
[Pureview]: https://azure.microsoft.com/de-de/services/purview/
[Purview]: https://azure.microsoft.com/de-de/services/purview/
[QnA Maker]: https://azure.microsoft.com/de-de/services/cognitive-services/qna-maker/
[Quantum]: https://azure.microsoft.com/de-de/services/quantum/
[Queue Storage]: https://azure.microsoft.com/de-de/services/storage/queues/
[R-Server for HDInsight]: https://azure.microsoft.com/de-de/services/hdinsight/r-server/
[Red Hat OpenShift]: https://azure.microsoft.com/de-de/services/openshift/
[Remote Rendering]: https://azure.microsoft.com/de-de/services/remote-rendering/
[Repos]: https://azure.microsoft.com/de-de/services/devops/repos/
[Resource Manager]: https://azure.microsoft.com/de-de/features/resource-manager/
[Resource Mover]: https://azure.microsoft.com/de-de/services/resource-mover/
[Route Server]: https://azure.microsoft.com/de-de/services/route-server/
[RTOS]: https://azure.microsoft.com/de-de/services/rtos/
[SDK's]: https://azure.microsoft.com/de-de/downloads/
[Security Center]: https://azure.microsoft.com/de-de/services/security-center/
[Sentinel]: https://azure.microsoft.com/de-de/services/azure-sentinel/
[Service Bus]: https://azure.microsoft.com/de-de/services/service-bus/
[Service Fabric]: https://azure.microsoft.com/de-de/services/service-fabric/
[Service Health]: https://azure.microsoft.com/de-de/features/service-health/
[SignalR Service]: https://azure.microsoft.com/de-de/services/signalr-service/
[Site Recovery]: https://azure.microsoft.com/de-de/services/site-recovery/
[Spatial Anchors]: https://azure.microsoft.com/de-de/services/spatial-anchors/
[Speicher Explorer]: https://azure.microsoft.com/de-de/features/storage-explorer/
[Sphere]: https://azure.microsoft.com/de-de/services/azure-sphere/
[Spracherkennung]: https://azure.microsoft.com/de-de/services/cognitive-services/speech-to-text/
[Sprachübersetzung]: https://azure.microsoft.com/de-de/services/cognitive-services/speech-translation/
[Sprechererkennung]: https://azure.microsoft.com/de-de/services/cognitive-services/speech-translation/
[Spring Cloud]: https://azure.microsoft.com/de-de/services/spring-cloud/
[SQL Datenbank]: https://azure.microsoft.com/de-de/services/sql-database/
[SQL Edge]: https://azure.microsoft.com/de-de/services/sql-edge/
[SQL Managed Instance]: https://azure.microsoft.com/de-de/services/azure-sql/sql-managed-instance/
[SQL Server auf VM]: https://azure.microsoft.com/de-de/services/virtual-machines/sql-server/
[Stack Edge]: https://azure.microsoft.com/de-de/products/azure-stack/edge/
[Stack HCI]: https://azure.microsoft.com/de-de/products/azure-stack/hci/
[Stack Hub]: https://azure.microsoft.com/de-de/products/azure-stack/hub/
[Stack]: https://azure.microsoft.com/de-de/overview/azure-stack/
[Statische Web-Apps]: https://azure.microsoft.com/de-de/services/app-service/static/
[StorSimple]: https://azure.microsoft.com/de-de/services/storsimple/
[Stream Analytics]: https://azure.microsoft.com/de-de/services/stream-analytics/
[Synapse Analytics]: https://azure.microsoft.com/de-de/services/synapse-analytics/
[Table Storage]: https://azure.microsoft.com/en-us/services/storage/tables/
[Test Plans]: https://azure.microsoft.com/de-de/services/devops/test-plans/
[Text-to-Speech]: https://azure.microsoft.com/de-de/services/cognitive-services/text-to-speech/
[Textanalysen]: https://azure.microsoft.com/de-de/services/cognitive-services/text-analytics/
[Time Series Insight]: https://azure.microsoft.com/de-de/services/time-series-insights/
[Traffic Manager]: https://azure.microsoft.com/de-de/services/traffic-manager/
[Übersetzer]: https://azure.microsoft.com/de-de/services/cognitive-services/translator/
[Vergleich AKS vs. Service Fabric]: https://docs.microsoft.com/en-us/archive/blogs/azuredev/service-fabric-and-kubernetes-comparison-part-1-distributed-systems-architecture
[Videoindizierung]: https://azure.microsoft.com/de-de/services/media-services/video-indexer/
[Virtual Network]: https://azure.microsoft.com/de-de/services/virtual-network/
[Virtual WAN]: https://azure.microsoft.com/de-de/services/virtual-wan/
[Virtuelle Citrix-Apps und -Desktops für Azure]: https://azure.microsoft.com/de-de/services/virtual-desktop/citrix-virtual-apps-desktops-for-azure/
[Virtuelle Computer]: https://azure.microsoft.com/de-de/services/virtual-machines/
[Virtuelle Data-Science Computer]: https://azure.microsoft.com/de-de/services/virtual-machines/data-science-virtual-machines/
[Visual Studio App Center]: https://azure.microsoft.com/de-de/services/app-center/
[VMware Horizon Cloud in Microsoft Azure]: https://azure.microsoft.com/de-de/services/virtual-desktop/vmware-horizon-cloud/
[VMWare-Lösungen in Azure]: https://azure.microsoft.com/de-de/services/azure-vmware/
[Vorlagen für Azure Resource Manager]: https://azure.microsoft.com/de-de/services/arm-templates/
[VPN Gateway]: https://azure.microsoft.com/de-de/services/vpn-gateway/
[Web Application Firewall]: https://azure.microsoft.com/de-de/services/web-application-firewall/
[Web-App für Container]: https://azure.microsoft.com/de-de/services/app-service/containers/
[Windows 10 IoT Services]: https://azure.microsoft.com/de-de/services/windows-10-iot-core/
[Windows Virtual Desktop]: https://azure.microsoft.com/de-de/services/virtual-desktop/
[Xamarin]: https://azure.microsoft.com/de-de/features/xamarin/
