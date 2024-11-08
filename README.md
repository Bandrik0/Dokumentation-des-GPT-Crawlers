Dokumentation des GPT-Crawlers für die Erstellung einer Informationsdatenbank

Einleitung

In diesem Projekt wurde der GPT-Crawler verwendet, um eine Informationsdatenbank zu erstellen, die für eine Schulwebsite nützlich ist. Der Crawler durchsucht Webseiten und speichert nützliche Informationen in einer JSON-Datei, die anschließend genutzt wird, um einen Chatbot zu füttern. Dieser Chatbot beantwortet Fragen der Nutzer basierend auf den gesammelten Daten.


Voraussetzungen


Um dieses Projekt erfolgreich zu verwenden, stelle sicher, dass du folgende Programme und Tools installiert hast:

•	Node.js: https://nodejs.org/

•	npm (Node Package Manager): Wird zusammen mit Node.js installiert.

•	Git: https://git-scm.com/

Schritte zur Einrichtung

1. Git-Repository klonen

Klonen des Repositories auf deinen lokalen Rechner:

	git clone https://github.com/builderio/gpt-crawler


2. Installation der benötigten Abhängigkeiten

Navigiere in das Projektverzeichnis und installiere alle notwendigen Abhängigkeiten mit npm:

	cd gpt-crawler
	npm install

3. Konfiguration des Crawlers

	•	Öffne die Datei config.ts im Projektordner.
	•	Ändere die Konfiguration nach deinen Wünschen. Ein Beispiel für die Konfiguration:

		import { Config } from "./src/config";
		
		export const defaultConfig: Config = {
		  url: "https://wp.tls-gi.de",  // Die URL der Website, die gecrawlt werden soll
		  match: "https://www.builder.io/c/docs/**",  // Passen Sie dies an, wenn Sie eine andere Seite crawlen möchten
		  maxPagesToCrawl: 50,  // Maximale Seitenanzahl, die gecrawlt werden soll
		  outputFileName: "output.json",  // Name der Datei, in der die Ergebnisse gespeichert werden
		  maxTokens: 2000000,  // Maximale Anzahl von Tokens für die GPT-API
		};


Tipp: Du kannst das match-Feld druch das gleiche URL ersetzen am ende soll /**, wenn du die gesamte Website crawlen möchtest.


4. Crawling starten

Starte den Crawler mit folgendem Befehl:

	npm start


Der Crawler wird nun die angegebene Website durchsuchen und die gesammelten Daten in einer Datei namens output.json speichern.

5. Verwenden der output.json-Datei

Lade die Datei output.json auf die ChatGPT-Website oder eine andere geeignete Plattform hoch, um einen Chatbot mit den gesammelten Daten zu erstellen. Der Chatbot kann nun Fragen basierend auf den Informationen beantworten, die der Crawler von der Website extrahiert hat.

Fehlerbehebung

Falls du auf Probleme stößt, überprüfe die folgenden Punkte:
	•	Stelle sicher, dass alle Abhängigkeiten erfolgreich mit npm install installiert wurden.
	•	Vergewissere dich, dass du den richtigen Ordner im Terminal geöffnet hast, bevor du den Crawler startest.
	•	Achte darauf, dass die output.json-Datei erfolgreich erstellt wurde und die richtigen Daten enthält.

Fazit

Dieses Projekt ermöglicht es dir, automatisiert Informationen von einer Website zu extrahieren und diese in einer Chatbot-Datenbank zu speichern. Der GPT-Crawler ist ein nützliches Werkzeug für die schnelle Erstellung von Informationsdatenbanken, die dann zur Interaktion mit Nutzern genutzt werden können.
