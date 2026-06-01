# Feedback Docente – Sensori Meteo Backend

Gruppo: Sescu – Giatti – Malachin – Cosmi

---

## 1. Analisi dei Requisiti

* Non è specificato quali regole il backend deve applicare per strutturare, validare e arricchire i dati provenienti dai sensori (schema minimo, timestamp di ricezione, normalizzazione).
* Non è definita la politica di gestione di dati anomali, duplicati o in ritardo (scarto, marcatura, versioning), rendendo non verificabile la coerenza dello storico.
* Non sono esplicitati i requisiti di storicizzazione e disponibilità del dato (periodo di conservazione, granularità minima, tempi di accesso), rendendo il requisito di storicizzazione non misurabile.

## 2. Analisi Funzionale

* Mancano casi d’uso funzionali lato backend (ingestione, validazione, salvataggio, disponibilità dei dati verso sistemi esterni) descritti come flussi con input, output ed errori, rendendo il comportamento del sistema implicito e non verificabile.
* Non è descritto il comportamento funzionale del backend in caso di errori di ingresso (dati incompleti, fuori range, perdita di connessione), quindi non è chiaro come il sistema reagisce agli scenari anomali.
* Non è chiarito funzionalmente come il backend gestisce la temporalità del dato (campionamento, invio, ricezione) e l’allineamento dei timestamp, quindi non è definito cosa viene considerato dato in tempo reale e cosa storico.

---

## 3. Analisi Tecnica

*(valutazione indicativa)*

* Non è esplicitata l’architettura tecnica del backend né lo schema dati (schema logico + modello ER), quindi non sono valutabili componenti/responsabilità e coerenza della persistenza rispetto ai requisiti.
* Non sono definite le interfacce di integrazione e il formato dei messaggi (es. MQTT/HTTP, payload, mapping campi → metriche), quindi non è verificabile il percorso end-to-end dal gateway/ThingsBoard alla persistenza.
* Non sono specificate le scelte tecniche per garantire affidabilità e continuità del backend (gestione perdita dati, persistenza sicura, recupero dopo fault), quindi non è valutabile la robustezza del sistema nel tempo.

---

## Nota metodologica finale

Il documento mostra una buona comprensione del dominio applicativo e degli obiettivi generali del sistema, ma soffre di una separazione non sempre netta tra requisiti, funzionalità e scelte tecniche. In un contesto progettuale o lavorativo, è fondamentale isolare chiaramente cosa il sistema deve garantire (requisiti), come si comporta dal punto di vista logico-funzionale (funzionale) e come viene realizzato concretamente (tecnica).

L’assenza iniziale di questa distinzione rende più difficile valutare completezza, verificabilità e coerenza dell’architettura backend. La riorganizzazione incrementale delle osservazioni va nella direzione corretta e costituisce una base solida per una successiva revisione progettuale più strutturata.


# Valutazione finale del progetto

Il gruppo ha mostrato una buona capacità di revisione della documentazione e ha implementato in modo significativo i feedback forniti durante le diverse milestone, in particolare per quanto riguarda analisi dei requisiti, analisi funzionale e analisi tecnica. La documentazione finale risulta più strutturata, maggiormente coerente con il contesto backend del progetto e complessivamente sufficiente dal punto di vista progettuale.

Sono stati introdotti elementi tecnici e funzionali precedentemente mancanti, come la gestione della validazione dei dati, la distinzione tra dati realtime e storico, la gestione di anomalie e duplicati, le modalità di persistenza e una descrizione più chiara del flusso di acquisizione e trattamento dei dati.

Restano tuttavia criticità importanti nella parte di pianificazione e gestione del progetto. Project Plan e Diagramma di Gantt risultano ancora troppo descrittivi e poco utilizzabili come strumenti reali di gestione operativa, con attività non sempre sufficientemente dettagliate, responsabilità poco isolate e pianificazione temporale non completamente coerente con lo stato reale del progetto.

Dal punto di vista implementativo, il progetto non ha raggiunto gli obiettivi previsti. Non risulta completata una reale integrazione stabile e funzionante dell’intero sistema, e gran parte del lavoro è rimasta a livello documentale o configurativo. La componente pratica del progetto risulta quindi significativamente incompleta rispetto agli obiettivi inizialmente definiti.

Sono inoltre emerse criticità organizzative interne al gruppo, con una distribuzione del lavoro non equilibrata e una partecipazione non omogenea allo sviluppo del progetto, elemento che ha inciso negativamente sull’avanzamento complessivo.

Si richiede pertanto la produzione di una relazione finale tecnica di handover destinata al futuro team di progetto, contenente:
- stato reale del sistema;
- componenti funzionanti e componenti incomplete;
- problematiche tecniche incontrate;
- configurazioni già realizzate;
- criticità organizzative emerse;
- indicazioni operative utili per l’eventuale prosecuzione del progetto.
