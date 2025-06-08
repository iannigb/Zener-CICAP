# Zener-CICAP

Questo repository contiene una semplice applicazione web composta da due pagine per effettuare un esperimento con le carte Zener. È stato realizzato in italiano e utilizza HTML, CSS e JavaScript senza strumenti di build esterni.

## Contenuti

- `operatore.html` – l'interfaccia per l'operatore, che seleziona le carte segrete e registra i risultati
- `medium.html` – l'interfaccia per il medium che indica la carta che ritiene corretta
- immagini PNG (`circle.png`, `cross.png`, `square.png`, `star.png`, `waves.png`, `retro.png`) con i simboli Zener

Entrambe le pagine comunicano tramite `BroadcastChannel` (nome del canale `zener_test`) e devono essere servite dallo stesso origin.

## Utilizzo

1. Avviare un semplice server HTTP in questa cartella, ad esempio:

   ```bash
   python3 -m http.server
   ```

2. Aprire `operatore.html` in una finestra del browser e `medium.html` in un'altra.
3. Usare la pagina dell'operatore per iniziare un nuovo test e rivelare le carte. Il medium sceglie un simbolo a ogni turno. I risultati e le statistiche sono mostrati nella pagina dell'operatore e possono essere esportati in formato CSV.
4. In alternativa è possibile aprire entrambe le pagine con un doppio clic sui file HTML: anche così il `BroadcastChannel` funziona correttamente se il browser le carica in locale (ad esempio da `127.0.0.1`).

Il test prevede di default 50 turni (`TOT_TURNI`). I calcoli di probabilità mostrano quanto sia probabile ottenere gli stessi risultati per puro caso.
Il test fornisce un risultato positivo se si indovinano almeno 18 carte su 50 (cosa che può avvenire nel circa l'1% dei test per pura casualità).
