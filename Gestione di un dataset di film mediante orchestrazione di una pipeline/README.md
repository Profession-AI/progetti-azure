# Gestione di un dataset di film mediante orchestrazione di una pipeline

## Descrizione dell'Azienda
**CineData Solutions** è un'azienda specializzata nell'ottimizzazione e trasformazione di dataset cinematografici per piattaforme di streaming e distribuzione digitale. La missione dell'azienda è di rendere i dati sui film più accessibili e utilizzabili per aziende che operano nel settore dell'intrattenimento, offrendo pipeline di dati su misura che facilitano l'integrazione, la pulizia e l'arricchimento delle informazioni.

## Sfida Aziendale
L'azienda si trova ad affrontare un'enorme quantità di dati disomogenei sui film, con informazioni in varie lingue e formati. Per garantire che queste informazioni possano essere utilizzate in modo efficace, CineData Solutions ha bisogno di creare una pipeline che traduca, pulisca e selezioni i dati in base a criteri specifici, migliorando l'accuratezza delle informazioni presentate alle piattaforme di distribuzione.

## Soluzione Proposta
CineData Solutions ha sviluppato una pipeline di trasformazione dati utilizzando **Azure Data Factory** per processare grandi volumi di dati cinematografici. Il progetto prevede il caricamento di un file CSV (MoviesDB2.csv) contenente informazioni su film, genere e valutazioni, e la trasformazione di tali dati per renderli più rilevanti e utilizzabili. 

### Passi Chiave del Processo
1. **Caricamento e Pulizia dei Dati**: Il file CSV contenente le informazioni cinematografiche viene caricato in un contenitore **Input** su Azure Blob Storage.
2. **Rimappatura dei Campi**: I nomi dei campi del file, originariamente in inglese, vengono rimappati in italiano. I campi principali che rimangono sono "Film", "Genere" e "Valutazione".
3. **Filtraggio dei Dati**: Vengono mantenuti solo i film che hanno una valutazione superiore a 7 su 10, in modo da garantire che solo i film con alte recensioni siano selezionati per l'analisi.
4. **Trasferimento e Parallelizzazione**: Una volta puliti e rimappati, i dati vengono copiati in un contenitore **Output**, con la possibilità di eseguire il processo in modo parallelo per garantire maggiore efficienza e scalabilità.
5. **Gestione dei Metadata**: Durante la copia, i metadata vengono mantenuti per conservare eventuali informazioni aggiuntive che potrebbero risultare utili in futuro, rendendo il dataset più ricco e utile per altre applicazioni.

### Componenti Tecnologiche
- **Azure Data Factory**: Utilizzata per orchestrare l'intera pipeline, con un design che garantisce flessibilità e scalabilità.
- **Azure Blob Storage**: Serve come contenitore per il caricamento e la distribuzione dei file di input e output.
- **Azure Translator (Opzionale)**: Può essere utilizzato per tradurre automaticamente i titoli dei film, offrendo un ulteriore livello di localizzazione.

## Vantaggi per l'Azienda
La soluzione fornisce diversi vantaggi competitivi:
- **Efficienza Operativa**: La pipeline permette un processo automatizzato che riduce il tempo necessario per la pulizia e la traduzione dei dati.
- **Flessibilità**: Gli utenti possono adattare il flusso di lavoro alle loro necessità, come l'uso di traduttori o di regole di filtraggio personalizzate.
- **Scalabilità**: La pipeline è progettata per gestire grandi volumi di dati in modo parallelo, ottimizzando l'uso delle risorse e riducendo i costi.
- **Valore dei Dati**: La conservazione dei metadata rende il dataset più versatile e ricco di informazioni, migliorando l'esperienza per gli utenti finali e facilitando analisi future.

## Valore Aggiunto
CineData Solutions offre una soluzione avanzata per le piattaforme di streaming e distribuzione cinematografica, trasformando i dati grezzi in informazioni pulite e pronte all'uso. Grazie a questa pipeline automatizzata, i partner dell'azienda possono ottenere rapidamente insight sui migliori film da distribuire e promuovere, risparmiando tempo e denaro nella gestione dei dati. Il sistema, inoltre, può essere personalizzato e ampliato per includere altre funzionalità di traduzione o filtraggio, garantendo un'alta flessibilità e adattabilità alle esigenze di mercato.



# Dataset

Il dataset è scaricabile da qui: https://proai-datasets.s3.eu-west-3.amazonaws.com/moviesDB.csv

# Modalità di consegna:  il JSON della pipeline e un documento scritto in cui spieghi in modo discorsivo cosa fai