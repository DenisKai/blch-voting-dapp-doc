# Rework-Plan für die Dokumentation

Ziel ist eine deutlich gestraffte, wissenschaftlich wirkende Dokumentation in deutscher Sprache mit ungefähr fünf Seiten Umfang. Die in den `.tex`-Dateien markierten Stellen mit `\hl{}` werden als konkrete Umbauhinweise verwendet.

## Leitlinie

Die neue Fassung soll nicht wie eine vollständige Ausarbeitung eines Forschungspapiers wirken, sondern wie ein kurzer, klar strukturierter Projektbericht. Der Schwerpunkt liegt auf dem tatsächlich implementierten System, nicht auf allgemeinen Lehrbucherklärungen.

## Zielstruktur

1. Einleitung
2. Methodik
3. Hauptkapitel
4. Diskussion

Die Struktur dient nur der Ordnung des Inhalts. Es müssen nicht für jeden Unterpunkt eigene `\section{}`-Blöcke entstehen.

## Inhaltliche Neuausrichtung

### 1. Einleitung

- Kurz das Projekt, den Zweck und den Anwendungsfall vorstellen.
- Die DApp als reduzierte, poolbasierte Predictionsmarkt-Demo auf einer EVM-Blockchain beschreiben.
- Den Fokus auf das demonstrierbare Kernsystem legen: Token, Markt, Staking, Auflösung, Auszahlung.
- Allgemeine DApp-Definitionen stark kürzen oder ganz entfernen, wenn sie keinen direkten Bezug zum Projekt haben.

### 2. Methodik

- Den methodischen Rahmen knapp erklären: Was wurde implementiert, wie wurde die Anwendung aufgebaut und wie wird sie betrieben.
- Die Architektur nur so weit erklären, wie sie für das Verständnis des Projekts nötig ist.
- Klare Trennung zwischen On-Chain-Logik, Frontend und Deployment-Pfad.
- Die Beschreibung von Hardhat, Nuxt, MetaMask, Contract-Export und lokalen/Testnet-Setups auf das Wesentliche reduzieren.

### 3. Hauptkapitel

Dieses Kapitel soll den eigentlichen Kern der Arbeit tragen. Inhaltlich bietet sich eine Verdichtung aus den bisherigen Kapiteln zu drei Blöcken an:

#### 3.1 System und Funktionsumfang

- Den konkreten Use Case des Projekts beschreiben.
- Den Ablauf in wenigen Schritten darstellen: Faucet, Markterstellung, Staking, Auflösung, Claim.
- Nur die tatsächlich unterstützten Kernfunktionen beschreiben, keine erzählerischen Umwege.

#### 3.2 Smart Contracts und Frontend

- Die Verträge `VoteToken` und `PredictionMarket` als zentrale Bausteine knapp vorstellen.
- Wichtige Mechanismen erläutern: ERC-20, `approve`/`transferFrom`, Zeitlogik, admin-basierte Auflösung, Pull-Payment-Claim.
- Die Frontend-Rolle auf die Bedienoberfläche und die Anzeige von Zuständen beschränken.
- Die Reduktion des Frontends auf YES/NO als bewusste Vereinfachung nennen.

#### 3.3 Qualität und Sicherheit

- Schutzmechanismen knapp bündeln: Zeitgrenzen, Zustandsprüfungen, einmalige Auflösung, Pull-Pattern, Reentrancy-Vorsorge.
- Bewusste Grenzen des Demo-Designs benennen: Admin-Vertrauen, kein sekundärer Handel, kein dezentrales Reporting, keine produktive Oracle-Struktur.

### 4. Diskussion

- Das Projekt knapp im Verhältnis zu realen Predictions-Märkten einordnen.
- Herausarbeiten, was die DApp gut demonstriert und was bewusst offen bleibt.
- Keine breiten Exkurse zu Polymarket, Augur, Gnosis oder Chainlink, wenn sie nicht direkt zur Projekteinordnung beitragen.
- Die Diskussion als komprimierte Reflexion über Lernwert, Grenzen und mögliche nächste Ausbaustufen formulieren.

## Konkrete Kürzungen und Umformulierungen

- Allgemeine Blockchain-Definitionen kürzen, wenn sie bereits für die Einordnung im Projektkontext bekannt vorausgesetzt werden können.
- Das Lernenden-/Praktikums-Narrativ durch neutralere, sachlichere Formulierungen ersetzen.
- Zu technische oder meta-argumentative Sätze streichen, wenn sie nur einen Kommentar auf den Text darstellen.
- Begriffe wie `Marktkarten`, `Ausführungsrelevanz`, `triviale Disziplin`, `wissenschaftliche Arbeit` oder ähnliche Metaformulierungen in präzisere Fachsprache umwandeln.
- Den Oracle-Teil so umbauen, dass er die reale Rolle der Admin-Adresse im Projekt korrekt beschreibt, statt eine zu breite externe Oracle-Diskussion zu führen.
- Die Detailtiefe bei Wahrscheinlichkeitsanzeige und Rundung reduzieren; nur so viel Mathematik zeigen, wie für das Verständnis nötig ist.

## Kapitelbezogene Arbeitsliste

### `content/intro.tex`

- Einstieg schärfen und auf das Projektziel zuschneiden.
- Kein langer theoretischer Vorlauf.

### `content/theorie-einordnung.tex`

- Allgemeines theoretisches Material deutlich kürzen.
- Nur die Konzepte behalten, die direkt für das Projekt gebraucht werden.
- Vergleichsbeispiele stark reduzieren oder in die Diskussion verschieben.

### `content/kernfunktionalitaet.tex`

- Narrativen Einstieg komprimieren oder entfernen.
- Der Abschnitt zur Kernfunktionalität soll die eigentliche Funktionskette des Systems knapp zeigen.
- Komfortfunktionen nur dann erwähnen, wenn sie für das Verständnis wirklich relevant sind.

### `content/architektur.tex`

- Auf die tatsächliche Systemarchitektur fokussieren.
- Backend-/Server-Diskussion nur soweit nötig behandeln.
- Deployment und Netzwerke sachlich, aber kurz erklären.

### `content/smart-contract.tex`

- Vertragserklärung auf die funktional wesentlichen Mechanismen begrenzen.
- Wahrscheinlichkeits- und Belohnungsformeln nur kurz einführen.
- Zu feine mathematische Detailtiefe reduzieren.

### `content/anwendung-deployment.tex`

- Frontend, Rollen und Deployment in einer kompakten Beschreibung zusammenziehen.
- Stärker auf Bedienablauf und Build-/Deploy-Kette als auf UI-Details fokussieren.

### `content/sicherheit-qualitaet.tex`

- Sicherheitsmechanismen kompakt und technisch sauber formulieren.
- Bewertungseinordnungen und Notenbezug entfernen.
- Nur echte Grenzen und relevante Qualitätsaspekte behalten.

## Empfohlene Reihenfolge für die Überarbeitung

1. Inhaltlich redundante und allgemeine Passagen entfernen.
2. Die Kapitel auf die neue Zielstruktur umsortieren.
3. Sprachlich alle markierten Stellen straffen und vereinheitlichen.
4. Danach den Umfang auf etwa fünf Seiten trimmen.
5. Abschließend einen vollständigen Sprach- und Konsistenzdurchlauf machen.

## Erwartetes Ergebnis

Am Ende soll ein kurzer, konsistenter Bericht entstehen, der:

- den Projektaufbau verständlich erklärt,
- die Kernfunktionalität sauber beschreibt,
- Sicherheit und Grenzen realistisch einordnet,
- und ohne unnötige Ausschweifungen in gut lesbarem Deutsch auskommt.