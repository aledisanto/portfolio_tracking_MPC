# Investment Portfolio Tracking using Model Predictive Control (MPC)

Questo repository contiene il materiale di ricerca, il report finale e le slide di presentazione sviluppati per il corso di **Control of Cyber-Physical Systems** presso l'**Università degli Studi di Trieste**. 

Il progetto applica le metodologie avanzate della teoria dei controlli automatici (in particolare il controllo predittivo) all'ambito dell'ingegneria finanziaria, basandosi sullo studio e la replicazione del paper scientifico *“Investment portfolio tracking using model predictive control”* (de Melo et al., 2023).

## Obiettivo del Progetto
Il lavoro si propone di risolvere il problema della **gestione passiva ed efficiente di un portafoglio di investimenti**. L'obiettivo ingegneristico è progettare un controllore **MPC a tempo discreto** capace di massimizzare la ricchezza complessiva del portafoglio minimizzando al contempo il *tracking error* rispetto a un indice di riferimento (benchmark), integrando i costi di transazione e vincoli stringenti di esposizione al rischio.

## Modello Matematico e Metodologia
Il sistema dinamico e la strategia di controllo sono stati strutturati analizzando i seguenti aspetti chiave:
* **Equazione della Ricchezza (Portfolio Wealth):** Modellazione degli stati per un portafoglio composto da $n$ asset rischiosi, un asset privo di rischio (*risk-free*) ed eventuale capitale a prestito.
* **Campionamento Giornaliero:** Trattamento dei prezzi di chiusura dei titoli azionari calcolandone il rendimento logaritmico ($\eta_i$), impostando un tempo di campionamento $T_s$ pari a un giorno lavorativo.
* **Controllo Predittivo (MPC):** Formulazione del problema di ottimizzazione su un orizzonte temporale mobile ($N$), bilanciando il trade-off tra performance computazionali e accuratezza del tracciamento.
* **Vincoli e Gestione del Rischio:** Integrazione di metriche di rischio finanziario come il **CVaR (Conditional Value at Risk)** all'interno della funzione di costo e gestione dei limiti fisici di non-negatività sul capitale investito.

## Analisi e Conclusioni Critiche
Le simulazioni numeriche (eseguite su campioni storici del mercato azionario brasiliano) hanno evidenziato:
* L'efficacia dell'MPC nel mantenere un tracking error ridotto, dimostrando un vantaggio competitivo rispetto ai benchmark classici.
* La necessità di un compromesso progettuale sulla scelta dell'orizzonte di predizione $N$: all'aumentare di $N$ si riscontra una crescita esponenziale dei tempi di calcolo a fronte di un potenziale scostamento dal riferimento.
* **Analisi Macroeconomica:** Il report include una riflessione critica sull'applicabilità del modello (tarato su un target annuo del 15% legato al tasso *SELIC* brasiliano) e su come le dinamiche cambierebbero radicalmente se calate nel contesto di mercato europeo ed italiano a causa dei differenti tassi strutturali *risk-free*.

## Contenuto della Repository
* **[Relazione_Progetto_CPS.pdf](./progetto_CPS_Alessandro_Di_Santo.pdf)**: Il report tecnico scritto completo, contenente le equazioni di stato del sistema, le specifiche di costo dell'algoritmo e gli screenshot delle simulazioni e del codice implementato in **MATLAB**.
* **[Presentazione_Progetto_CPS.pptx](./PROGETTO_CPS.pptx)**: Le slide PowerPoint complete utilizzate in sede di discussione finale per riassumere i grafici dei flussi di ricchezza e l'analisi dei parametri di efficienza.
* **progetto_CPS_TESTING.mlx**: codice MATLAB riportato anche sul report tecnico.
* **dati_storici.zip**: dati utilizzati per lo studio presi dal sito Investing.com (tradotti in documento Excel attraverso codice MATLAB: **dati_B3.csv**) 

---
*Studente: Alessandro Di Santo*  
*Professore: Davide Martino Raimondo*  
*Corso di Laurea Magistrale in Computer Engineering (Robotics & AI) — Università degli Studi di Trieste*
