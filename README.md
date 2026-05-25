# Progetto Esame - Analisi dei Dati di un Dataset Storico-Artistico

## DOI: https://doi.org/10.5281/zenodo.20379406

## Descrizione:

Il progetto realizzato vuole analizzare il dataset storico-artistico fornito dal Professore Sebastian Barzaghi riguardante opere d'arte comprese tra l'anno Mille fino ai primi anni del Duemila.

## Domande di Ricerca:

* ricostruzione della tendenza artistica di Tiziano all'arte religiosa
* indagine dimensionale: verificare la correlazione tra il genere dell'opera (es. arte religiosa, ritrattistica, ...) e la superificie fisica, identificando quali categorie tematiche richiedessero formati più monumentali
* analizzare il genere di opere e gli artisti prevalenti nella località di Bologna

## Fonte dei dati

| Variabile       | Tipo di dato       | Definizione                                                   | Esempio |
|-----------------|------------------|---------------------------------------------------------------|---------|
| `id`            | Stringa/URL      | Identificativo univoco dell’opera, spesso link a Wikidata o altra fonte esterna | `http://www.wikidata.org/entity/Q428274` |
| `titolo`        | Stringa          | Titolo dell’opera d’arte                                      | *Ritratto di Fedra Inghirami, detto Fedra* |
| `artisti`       | Stringa          | Nome dell’artista autore dell’opera                           | *Raffaello Sanzio (maschio)* |
| `data_creazione`| Intero/Stringa   | Anno di creazione dell’opera                                   | `1510` |
| `generi`        | Stringa          | Genere artistico o descrittivo dell’opera                     | *ritratto* |
| `luoghi`        | Stringa          | Luogo o museo in cui l’opera è conservata                     | *Galleria Palatina* |
| `collezioni`    | Stringa          | Collezione o contesto espositivo                               | *Galleria Palatina* |
| `contenuti`     | Stringa          | Elementi semantici/temi presenti nell’opera                   | *libro; carta; scrittura; strabismo; …* |
| `movimenti`     | Stringa          | Movimento artistico a cui l’opera è associata                 | *Alto Rinascimento* |
| `soggetti`      | Stringa          | Principali figure o soggetti rappresentati                    | *Tommaso Inghirami* |
| `altezza`       | Float            | Altezza dell’opera in centimetri                               | `91.0` |
| `larghezza`     | Float            | Larghezza dell’opera in centimetri                             | `61.0` |

I Dati originali utilizzati sono stati estratti dal CSV a questo link:  https://raw.githubusercontent.com/dhdmch/2025-2026/refs/heads/main/data/vapod/data.csv

I Dati in output sono stati gestiti tramite Google Colab, utilizzando il linguaggio Python e le seguenti librerie specializzate: 
1. pandas come strumento principale per la manipolazione, analisi e visualizzazione dei dati
2. numpy per la gestione della memoria e la velocità dei calcoli numerici di base
3. seaborn per la lettura della tabella di pandas e decisione della struttura avanzata e colorazione dei grafici
4. matplotlib.pyplot per la rifinitura del grafico e la visualizzazione a schermo

Per garantire la coerenza dell'analisi, sono state eseguite le seguenti operazioni di trattamento dati:

* **Caricamento e ispezione dei dati:** *p.read_csv*, *df.head()*
* **Creazione di nuove variabili:** url, artista_target, genere_target
* **Normalizzazione dei dati:** creazione di artisti_clean e generi_clean per evitare errori case sensitive (maiuscolo/minuscolo)
* **Gestione dei campi multivalore:** Trattamento delle colonne  `generi_clean` e `artisti_clean ` tramite queste funzioni *.replace()*, *.split()*, *.explode()* per ottenere i singoli valori.
* **Analisi esplorativa tramite aggregazioni:** *.value_counts()*, *.groupby()*
* **Visualizzazione dei risultati:** tramite grafico a barre *.barplot*

## Analisi dei Risultati

### DOMANDA 1
L'analisi trae conclusioni chiare sulla tendenza all'arte religiosa di Tiziano, in quanto il 48,6% delle opere nel file CSV fa parte di questo genere. 

### DOMANDA 2
L'analisi sull'influenza del genere sulla dimensione dell'opera riporta che: 
- i dipinti di battaglia (1) sono in cima alla classifica, il formato rispecchia il genere principalmente per un'attenzione specifica ad ogni singolo dettaglio e spesso sono opere su commissione. 
- l'autoritratto si posiziona in fondo alla classifica, il formato rispecchia il genere in quanto spesso sono opere ad uso dell'artista e non su commissione 

### DOMANDA 3 
L'ultima analisi tenta di capire quale tipologia di opera è più presente a Bologna:
l'analisi dimosra che il genere più presente è quello dell'arte religiosa, mentre c'è un pareggio sugli artisti, ovvero: Guido Reni, Ludovico e Annibale Carracci.

## Dataset e Strumenti 
* Fonte Dati: Dataset VAPOD (Formato CSV) disponibile al link: https://raw.githubusercontent.com/dhdmch/2025-2026/refs/heads/main/data/vapod/data.csv
* Strumenti: Phyton (Pandas, numpy, matplotlib.pyplot e seaborn)

## Responsabile
Ilaria Ciampone 

## Licenza
I dati sono rilasciati sotto licenza CC0 1.0 Universal

*Relazione prodotta per il corso di Informatica per i Beni Culturali (2025/2026)*
