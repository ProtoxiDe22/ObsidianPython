---
{"dg-publish":true,"permalink":"/course-outline/","tags":["gardenEntry"]}
---

### Capitolo 1: Introduzione a Python
#### 1.1 Panoramica di Python
- Storia di Python
  - Creazione e sviluppo del linguaggio
  - Versioni principali (Python 2 vs Python 3)
- Applicazioni di Python
  - Sviluppo web
  - Data science e machine learning
  - Automazione e scripting
  - Applicazioni desktop

#### 1.2 Installazione e Configurazione dell'Ambiente di Sviluppo
- Installare Python
  - Su Windows
  - Su macOS
  - Su Linux
- Configurare un ambiente di sviluppo
  - Visual Studio Code
- Utilizzo dei gestori di pacchetti
  - pip
  - venv e virtualenv

#### 1.3 Primi Passi con Python
- Scrivere e eseguire il primo programma Python
  - "Hello, World!"
- Utilizzo dell'interprete Python
  - Interprete interattivo
  - Esecuzione di script da riga di comando

### Capitolo 2: Termini e Definizioni Fondamentali
#### 2.1 Concetti di Base
- Identificatori e parole chiave
  - Nomi validi per variabili e funzioni
  - Parole chiave riservate di Python
- Commenti e documentazione del codice
  - Commenti singola linea e multilinea
  - Docstring per documentare funzioni e classi

#### 2.2 Logica e Struttura di Python
- Blocco di codice e indentazione
  - Regole di indentazione in Python
  - Errori comuni di indentazione
- Python come linguaggio interpretato
  - Differenza tra linguaggi interpretati e compilati

### Capitolo 3: Literals, Variabili e Sistemi Numerici
#### 3.1 Literals e Variabili
- Literals
  - Numerici (interi, float, complessi)
  - Stringhe
  - Booleani
  - Literals speciali (None)
- Dichiarazione e assegnazione di variabili
  - Convenzioni di denominazione
  - Assegnazione multipla

#### 3.2 Tipi di Dati Numerici
- Interi, float e complessi
  - Proprietà e operazioni sui tipi numerici
- Conversione di tipi numerici
  - Funzioni `int()`, `float()`, `complex()`

#### 3.3 Operatori
- Operatori aritmetici
  - Somma, sottrazione, moltiplicazione, divisione
  - Operatori modulo e potenza
- Operatori di confronto
  - Uguale, diverso, maggiore, minore, maggiore o uguale, minore o uguale
- Operatori logici
  - and, or, not
- Operatori di assegnazione
  - =, +=, -=, *=, /=, %=
- Operatori bitwise
  - &, |, ^, ~, <<, >>

### Capitolo 4: Input/Output da Console
#### 4.1 Operazioni di Input
- Funzione `input()`
  - Lettura di stringhe da input
  - Conversione dei tipi di input

#### 4.2 Operazioni di Output
- Funzione `print()`
  - Argomenti multipli e separatori
  - Fine riga e fine di stampa
- Formattazione delle stringhe
  - f-strings (formatted string literals)
  - Metodo `format()`
  - Operatore `%` (percent formatting)

### Capitolo 5: Flusso di Controllo - Blocchi Condizionali e Loop
#### 5.1 Istruzione If
- Sintassi dell'istruzione if
  - if semplice
  - if-elif-else
- Esempi pratici
  - Condizioni multiple e annidate

#### 5.2 Loop
- Loop for
  - Iterare su sequenze (liste, stringhe, range)
  - Funzione `range()`
- Loop while
  - Condizioni di continuazione e terminazione
- Istruzioni di controllo del loop
  - break
  - continue
  - pass

### Capitolo 6: Data Collection - Tuple, Dizionari, Elenchi e Stringhe
#### 6.1 Liste
- Creazione e manipolazione delle liste
  - Liste vuote e popolazione di liste
  - Indicizzazione e slicing
- Metodi delle liste
  - append(), insert(), remove(), pop(), sort(), reverse()
- Liste nidificate e comprensione delle liste
  - Liste di liste
  - List comprehension

#### 6.2 Tuple
- Creazione e uso delle tuple
  - Tuple vuote e con un singolo elemento
- Differenze tra liste e tuple
  - Immutabilità delle tuple
  - Operazioni comuni su tuple

#### 6.3 Dizionari
- Creazione e uso dei dizionari
  - Dizionari vuoti e popolazione di dizionari
  - Accesso e modifica di elementi
- Metodi dei dizionari
  - get(), keys(), values(), items(), update(), pop()
- Iterazione sui dizionari
  - Loop su chiavi, valori e coppie chiave-valore

#### 6.4 Stringhe
- Operazioni base sulle stringhe
  - Concatenazione, ripetizione, slicing
- Metodi delle stringhe
  - split(), join(), replace(), upper(), lower(), strip(), find()
- Formattazione avanzata
  - Template strings e moduli `string`

### Capitolo 7: Funzioni ed Eccezioni
#### 7.1 Funzioni
- Definizione e chiamata di funzioni
  - Sintassi di definizione
  - Parametri posizionali e keyword
- Parametri e argomenti
  - Parametri di default
  - Argomenti arbitrari (*args e **kwargs)
- Funzioni lambda
  - Definizione e uso delle espressioni lambda
  - Differenze con funzioni tradizionali

#### 7.2 Gestione delle Eccezioni
- Introduzione alle eccezioni
  - Tipi di eccezioni comuni
  - Sintassi del blocco try-except
- Blocco try-except
  - Gestione delle eccezioni specifiche e generiche
- Clausole finally e else
  - Uso delle clausole finalmente ed else

### Capitolo 8: Moduli e Pacchetti
#### 8.1 Importazione di Moduli
- Importare moduli built-in
  - Sintassi di importazione
  - Alias dei moduli

#### 8.2 Moduli Specifici
- Modulo math
  - Funzioni matematiche comuni
- Modulo random
  - Generazione di numeri casuali e funzioni correlate
- Modulo platform
  - Informazioni sul sistema operativo

#### 8.3 Creazione di Moduli e Pacchetti
- Scrivere e importare moduli personalizzati
  - Definizione di un modulo
  - Uso del modulo `__name__`
- Creare pacchetti Python
  - Struttura di un pacchetto
  - File `__init__.py`

### Capitolo 9: Gestione Avanzata delle Eccezioni
#### 9.1 Eccezioni Predefinite
- Gerarchia delle eccezioni in Python
  - Classi base e derivate
- Eccezioni comuni
  - ValueError, TypeError, KeyError, IndexError

#### 9.2 Definire Eccezioni Personalizzate
- Creazione di nuove classi di eccezioni
  - Ereditarietà da Exception
- Utilizzo delle eccezioni personalizzate
  - Rilancio di eccezioni e messaggi personalizzati

### Capitolo 10: Stringhe - Operazioni Avanzate
#### 10.1 Meccanica delle Stringhe
- Codifica dei caratteri
  - ASCII vs Unicode
  - Encodings comuni (UTF-8, UTF-16)
- Byte e stringhe
  - Conversione tra stringhe e byte

#### 10.2 Manipolazioni Avanzate
- Regex e stringhe
  - Introduzione alle espressioni regolari
  - Uso del modulo `re` per la ricerca e la sostituzione
- Operazioni di slicing e concatenazione
  - Tecniche avanzate di slicing
  - Concatenazione efficiente delle stringhe

### Capitolo 11: Programmazione Orientata agli Oggetti
#### 11.1 Concetti di Base
- Introduzione alla programmazione orientata agli oggetti
  - Principi fondamentali (incapsulamento, ereditarietà, polimorfismo)
- Classi e oggetti
  - Definizione e istanziazione delle classi

#### 11.2 Proprietà e Metodi
- Definizione di proprietà
  - Attributi di istanza e di classe
- Definizione di metodi
  - Metodi di istanza
  - Metodi di classe e metodi statici

#### 11.3 Ereditarietà
- Creazione

 di classi derivate
  - Ereditarietà singola e multipla
- Metodi override e super()
  - Sovrascrittura dei metodi
  - Utilizzo del metodo super()

#### 11.4 Oggetti e Costruttori
- Costruttori (`__init__`)
  - Inizializzazione degli attributi
- Distruttori (`__del__`)
  - Pulizia delle risorse

### Capitolo 12: Argomenti Avanzati
#### 12.1 List Comprehension
- Sintassi e utilizzo delle list comprehension
  - Esempi semplici e complessi
- Comprensione delle set e dei dizionari
  - Set comprehension
  - Dictionary comprehension

#### 12.2 Funzioni Lambda
- Definizione e uso delle lambda
  - Esempi pratici
- Differenze tra lambda e funzioni tradizionali
  - Vantaggi e limitazioni delle lambda

#### 12.3 Closures
- Definizione e uso delle closures
  - Esempi pratici di utilizzo
- Decoratori
  - Introduzione ai decoratori
  - Creazione e utilizzo di decoratori personalizzati

#### 12.4 Input/Output
- Operazioni di base su file
  - Lettura e scrittura di file di testo
  - Modalità di apertura dei file (`r`, `w`, `a`, `b`)
- Gestione dei file con `with`
  - Uso del contesto manageriale
  - Lettura e scrittura sicura
