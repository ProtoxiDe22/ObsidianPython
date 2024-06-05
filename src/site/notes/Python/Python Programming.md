---
{"dg-publish":true,"permalink":"/python/python-programming/"}
---

## Introduzione a Python

---

### Panoramica di Python

#### Storia di Python
Python è un linguaggio di programmazione creato da Guido van Rossum nel 1991. È stato sviluppato come successore di ABC, un linguaggio che mirava a essere facile da usare. Python è conosciuto per la sua sintassi leggibile e il suo supporto per più paradigmi di programmazione, inclusi quelli imperativi, procedurali, orientati agli oggetti e funzionali.

---

#### Differenze tra Python 2 e Python 3

Python 2 e Python 3 sono due versioni principali del linguaggio Python, e presentano alcune differenze chiave che rendono importante la scelta della versione giusta per il proprio progetto.

- **Print:** In Python 2, `print` è una dichiarazione, mentre in Python 3 è una funzione.
  ```python
  # Python 2
  print "Hello, World!"
  
  # Python 3
  print("Hello, World!")
  ```

- **Divisione intera:** In Python 2, la divisione tra interi restituisce un intero, mentre in Python 3 restituisce un float. Per ottenere il comportamento di divisione intera in Python 3, si usa l'operatore `//`.
  ```python
  # Python 2
  print 5 / 2  # Output: 2
  
  # Python 3
  print(5 / 2)  # Output: 2.5
  print(5 // 2)  # Output: 2
  ```

- **Unicode:** In Python 2, le stringhe sono ASCII per default, mentre in Python 3 le stringhe sono Unicode per default, facilitando la gestione di testo internazionale.

- **Errori di sintassi:** Alcune sintassi sono cambiate o sono state rimosse in Python 3 per migliorare la leggibilità e la coerenza del linguaggio.
  ```python
  # Python 2
  raise IOError, "file error"
  
  # Python 3
  raise IOError("file error")
  ```

---

#### Funzionalità Introdotte nelle versioni recenti di Python 3

Python 3 ha visto molte aggiunte significative negli ultimi anni, rendendo il linguaggio più potente e versatile.

- **F-string (Python 3.6):** Introduzione delle f-string per la formattazione delle stringhe in modo più leggibile ed efficiente.
  ```python
  nome = "Alice"
  eta = 30
  print(f"{nome} ha {eta} anni.")
  ```

- **Type hints (Python 3.5):** Introduzione delle annotazioni di tipo per migliorare la leggibilità del codice e permettere strumenti di controllo statico dei tipi.
  ```python
  def saluta(nome: str) -> str:
      return f"Ciao, {nome}"
  ```

- **Asyncio (Python 3.4):** Introduzione del modulo `asyncio` per la programmazione asincrona, rendendo più facile scrivere codice non bloccante.
  ```python
  import asyncio

  async def saluta():
      await asyncio.sleep(1)
      print("Ciao!")

  asyncio.run(saluta())
  ```

- **Data Classes (Python 3.7):** Introduzione delle data classes per creare classi per la gestione dei dati con meno boilerplate code.
  ```python
  from dataclasses import dataclass

  @dataclass
  class Persona:
      nome: str
      eta: int

  persona = Persona("Alice", 30)
  print(persona)
  ```

- **Walrus operator (Python 3.8):** Introduzione dell'operatore di assegnazione espressionale (`:=`) per semplificare alcune espressioni.
  ```python
  if (n := len("Hello")) > 5:
      print(f"La lunghezza è {n}")
  ```

- **Pattern Matching (Python 3.10):** Introduzione del pattern matching, una potente struttura di controllo che permette di scrivere codice più leggibile e conciso per gestire dati complessi.
  ```python
  def processa(item):
      match item:
          case 1:
              print("Uno")
          case 2:
              print("Due")
          case _:
              print("Altro")
  ```
---

#### Applicazioni di Python

Python è utilizzato in vari campi grazie alla sua versatilità:

- **Sviluppo web:** Framework come Django e Flask permettono di sviluppare applicazioni web robuste e scalabili.
- **Data science e machine learning:** Librerie come Pandas, NumPy, e Scikit-learn rendono Python ideale per l'analisi dei dati e il machine learning.
- **Automazione e scripting:** Python è eccellente per automatizzare compiti ripetitivi e per scrivere script di sistema.
- **Applicazioni desktop:** Toolkit come Tkinter permettono lo sviluppo di interfacce grafiche per applicazioni desktop.

---

### Installazione e Configurazione dell'Ambiente di Sviluppo

#### Installare Python

Per iniziare a programmare in Python, è necessario installarlo sul proprio sistema operativo.

- **Su Windows:** Scarica l'installer da [python.org](https://www.python.org/) e segui le istruzioni. Durante l'installazione, seleziona l'opzione "Add Python to PATH".
- **Su macOS:** Usa Homebrew (se installato) con il comando `brew install python3`.
- **Su Linux:** Installa Python usando il gestore di pacchetti della tua distribuzione. Ad esempio, su Ubuntu, puoi usare `sudo apt-get install python3`.

---

#### Configurare un ambiente di sviluppo

Un buon ambiente di sviluppo migliora l'esperienza di programmazione. Visual Studio Code è un editor di codice gratuito e potente con un'ottima estensione per Python.

- **Visual Studio Code:** Installa Visual Studio Code e aggiungi l'estensione Python per supporto avanzato del linguaggio, come il completamento del codice, debugging, e linting.

---

### Primi Passi con Python

#### Scrivere e eseguire il primo programma Python

Il primo programma che la maggior parte delle persone scrive in un nuovo linguaggio di programmazione è il classico "Hello, World!".

```python
# Questo è il nostro primo programma in Python
print("Hello, World!")
```

Questo semplice programma stampa "Hello, World!" sulla console. La funzione `print()` è usata per produrre output.

---

#### Utilizzo dell'interprete Python

Python può essere eseguito in diversi modi:

- **Interprete interattivo:** Avvia l'interprete Python digitando `python` o `python3` nel terminale. Puoi quindi digitare ed eseguire comandi Python direttamente. Questo è utile per testare rapidamente piccoli pezzi di codice.
- **Esecuzione di script da riga di comando:** Salva il tuo programma in un file con estensione `.py` (ad esempio, `hello.py`) e eseguilo con il comando `python hello.py`.

---

## Termini e Definizioni Fondamentali

### Concetti di Base

#### Identificatori e parole chiave

Gli identificatori sono i nomi utilizzati per variabili, funzioni, classi, ecc. Devono seguire queste regole:

- Devono iniziare con una lettera (a-z, A-Z) o un underscore (_).
- Possono contenere lettere, numeri e underscore.
- Sono case-sensitive (`var` e `Var` sono due identificatori diversi).

Esempi di nomi validi:
```python
my_variable = 10
Variable1 = 20
_hidden = 30
```

Le parole chiave sono riservate dal linguaggio e non possono essere usate come identificatori. Alcune delle parole chiave di Python includono: `if`, `else`, `while`, `for`, `def`, `class`, ecc.

---

#### Commenti e documentazione del codice

Commentare il codice è essenziale per la leggibilità e la manutenzione.

- **Commenti singola linea:** Iniziano con il simbolo `#` e il testo dopo viene ignorato dall'interprete.
  ```python
  # Questo è un commento singola linea
  ```
- **Commenti multilinea:** Possono essere scritti usando triple virgolette.
  ```python
  """
  Questo è un commento
  su più linee
  """
  ```

I commenti aiutano a spiegare cosa fa il codice e sono particolarmente utili quando il codice diventa complesso.

---
---

### Termini e Definizioni Fondamentali

#### Concetti di Base

##### Identificatori e parole chiave

- **Identificatori:**
  Gli identificatori sono nomi utilizzati per identificare variabili, funzioni, classi, moduli o altri oggetti. In Python, ci sono alcune regole e convenzioni da seguire per creare identificatori validi:
  - Un identificatore può essere composto da lettere (a-z, A-Z), numeri (0-9) e underscore (\_).
  - Un identificatore non può iniziare con un numero.
  - Gli identificatori sono case-sensitive (es. `myVariable` e `myvariable` sono diversi).
  
  **Convenzioni di denominazione:**
  - **Variabili:** utilizzare lettere minuscole e underscore per separare le parole. Esempio: `my_variable`
  - **Funzioni:** utilizzare lettere minuscole e underscore per separare le parole. Esempio: `my_function()`
  - **Classi:** utilizzare CamelCase. Esempio: `MyClass`
  - **Costanti:** utilizzare lettere maiuscole e underscore per separare le parole. Esempio: `MY_CONSTANT`
  
  **Esempio di utilizzo degli identificatori:**
  ```python
  my_variable = 10
  def my_function():
      return my_variable
  class MyClass:
      def __init__(self):
          self.value = my_variable
  ```

- **Parole chiave riservate:**
  Python ha delle parole chiave riservate che non possono essere utilizzate come identificatori. Alcune di queste parole sono:  `if`, `else`, `while`, `for`, `def`, `class`, ecc.

---

##### Commenti e documentazione del codice

- **Commenti singola linea:**
  I commenti singola linea iniziano con il simbolo `#` e continuano fino alla fine della riga. Vengono utilizzati per aggiungere spiegazioni o note all'interno del codice.

  **Esempio:**
  ```python
  # Questo è un commento singola linea
  x = 10  # Assegnazione del valore 10 alla variabile x
  ```

- **Commenti multilinea:**
  I commenti multilinea possono essere creati utilizzando tre virgolette singole (`'''`) o tre virgolette doppie (`"""`). Anche se non sono veri e propri commenti, possono essere utilizzati come tali. Tuttavia, è importante notare che vengono trattati come stringhe e quindi occupano spazio in memoria.

  **Esempio:**
  ```python
  '''
  Questo è un commento
  su più righe.
  '''
  def my_function():
      """
      Questa è una docstring per la funzione my_function.
      Le docstring sono utilizzate per documentare funzioni e classi.
      """
      pass
  ```

- **Docstring per documentare funzioni e classi:**
  Le docstring sono stringhe di documentazione che descrivono lo scopo e il comportamento di una funzione, classe o modulo. Sono definite all'interno della funzione o classe usando tre virgolette doppie.

  **Esempio:**
  ```python
  def add(a, b):
      """
      Questa funzione ritorna la somma di due numeri.
      Parametri:
      a (int, float): Il primo numero.
      b (int, float): Il secondo numero.
      Ritorna:
      int, float: La somma di a e b.
      """
      return a + b
  ```

  Le docstring possono essere recuperate utilizzando l'attributo `__doc__` dell'oggetto.

  **Esempio:**
  ```python
  print(add.__doc__)
  ```

---

##### Logica e Struttura di Python

- **Blocco di codice e indentazione:**
  In Python, l'indentazione è fondamentale per definire i blocchi di codice. Un blocco di codice è un insieme di istruzioni che vengono eseguite insieme. L'indentazione in Python deve essere coerente e di solito si utilizzano quattro spazi per livello di indentazione.

  **Esempio:**
  ```python
  if x > 0:
      print("x è positivo")
      if x > 10:
          print("x è anche maggiore di 10")
  ```

  **Regole di indentazione in Python:**
  - Utilizzare quattro spazi per livello di indentazione.
  - Non mescolare spazi e tabulazioni per l'indentazione.
  - Ogni blocco di codice all'interno di un'istruzione condizionale, loop, funzione o classe deve essere indentato.

  **Errori comuni di indentazione:**
  - Utilizzare un numero diverso di spazi per lo stesso livello di indentazione.
  - Dimenticare di indentare il codice all'interno di un blocco.

- **Python come linguaggio interpretato:**
  Python è un linguaggio interpretato, il che significa che il codice viene eseguito direttamente dall'interprete Python, riga per riga, anziché essere compilato in codice macchina eseguibile. Questa caratteristica rende Python particolarmente adatto per lo sviluppo rapido e l'esecuzione di script.

  **Differenza tra linguaggi interpretati e compilati:**
  - **Interpretati:** Il codice viene eseguito direttamente dall'interprete. Esempi: Python, JavaScript, Ruby.
  - **Compilati:** Il codice sorgente viene prima compilato in codice macchina eseguibile. Esempi: C, C++, Java.

---
### Logica e Struttura di Python

#### Blocco di codice e indentazione

Python usa l'indentazione per definire i blocchi di codice. Ogni blocco di codice deve essere indentato allo stesso livello. Questo rende il codice più leggibile e organizzato.

- **Regole di indentazione in Python:** L'indentazione standard è di 4 spazi. È importante essere coerenti con l'uso degli spazi, evitare di mescolare tabulazioni e spazi.
  ```python
  if True:
      print("Questo è un blocco di codice")
  ```

Un errore comune è non mantenere la coerenza nell'indentazione, che può causare errori di sintassi.

---

#### Python come linguaggio interpretato

Python è un linguaggio interpretato, il che significa che il codice viene eseguito direttamente dall'interprete Python, riga per riga, senza una fase di compilazione preliminare. Questo permette un ciclo di sviluppo rapido, poiché il codice può essere testato e modificato facilmente.

In contrasto, i linguaggi compilati come C o C++ traducono il codice sorgente in un file eseguibile prima dell'esecuzione. Questo può portare a tempi di sviluppo più lunghi, ma eseguire il codice più velocemente.

---

## Literals, Variabili e Sistemi Numerici

### Literals e Variabili

#### Literals

I literals sono valori costanti che appaiono direttamente nel codice.

- **Numerici (interi, float, complessi):**
  ```python
  x = 10  # Intero
  y = 3.14  # Float
  z = 1 + 2j  # Numero complesso
  ```
- **Stringhe:**
  ```python
  greeting = "Hello, World!"
  ```
- **Booleani:**
  ```python
  is_python_fun = True
  ```
- **Literals speciali (None):**
  ```python
  nothing = None
  ```

---

#### Dichiarazione e assegnazione di variabili

Le variabili sono usate per memorizzare dati che possono essere utilizzati e modificati nel programma.

- **Convenzioni di denominazione:** Usa nomi significativi e segui la convenzione di snake_case per le variabili.
  ```python
  my_variable = 10
  ```
- **Assegnazione multipla:** È possibile assegnare valori a più variabili in una singola riga.
  ```python
  a, b, c = 1, 2, 3
  ```

L'uso di nomi descrittivi per le variabili rende il codice più leggibile e facile da capire.

---

### Tipi di Dati Numerici

#### Interi, float e complessi

I numeri in Python possono essere di vari tipi:

- **Interi (int):** Numeri senza parte decimale.
- **Float:** Numeri con parte decimale.
- **Complessi:** Numeri con una parte reale e una immaginaria.

Esempi di operazioni sui tipi numerici:
```python
x = 5
y = 2.5
z = 1 + 1j

somma = x + y  # 7.5
prodotto = x * y  # 12.5
```

---

#### Conversione di tipi numerici

Python permette di convertire tra diversi tipi numerici usando funzioni built-in.

- **Conversioni:**
  ```python
  intero = int(3.14)  # 3
  decimale = float(5)  # 5.0
  complesso = complex(2, 3)  # (2+3j)
  ```

La conversione dei tipi è utile quando si lavora con input che devono essere trattati come numeri.

---

### Operatori

#### Operatori aritmetici

Gli operatori aritmetici sono usati per eseguire operazioni matematiche di base.

- **Somma (+):** Aggiunge due numeri.
  ```python
  a = 10
  b = 3
  somma = a + b  # 13
  ```

- **Sottrazione (-):** Sottrae il secondo numero dal primo.
  ```python
  sottrazione = a - b  # 7
  ```

- **Moltiplicazione (*):** Moltiplica due numeri.
  ```python
  moltiplicazione = a * b  # 30
  ```

- **Divisione (/):** Divide il primo numero per il secondo, restituendo un float.
  ```python
  divisione = a / b  # 3.3333...
  ```

- **Divisione intera (//):** Divide il primo numero per il secondo, restituendo un intero.
  ```python
  divisione_intera = a // b  # 3
  ```

- **Potenza (**):** Eleva il primo numero alla potenza del secondo.
  ```python
  potenza = a ** b  # 1000
  ```

- **Operatore Modulo (%):** Restituisce il resto della divisione del primo numero per il secondo.
  ```python
  modulo = a % b  # 1
  ```

  **Esempio di utilizzo dell'operatore Modulo:**
  L'operatore modulo è spesso utilizzato per determinare se un numero è pari o dispari, poiché un numero è pari se il resto della sua divisione per 2 è 0.

  ```python
  numero = 8
  resto = numero % 2  # 0, quindi il numero è pari
  ```

  In questo esempio, `numero % 2` restituisce il resto della divisione di `numero` per 2. Se il resto è 0, il numero è pari.

  Un altro uso comune dell'operatore modulo è per trovare il giorno della settimana dato un numero di giorni. Supponiamo che oggi sia lunedì (giorno 0), possiamo calcolare il giorno della settimana dopo un certo numero di giorni.

  ```python
  giorni_totali = 10
  giorno_settimana = giorni_totali % 7  # 3, quindi sarà giovedì (se lunedì è 0)
  ```

  In questo esempio, `giorni_totali % 7` restituisce il giorno della settimana corrispondente al numero totale di giorni. Se `giorni_totali` è 10, il risultato è 3, il che significa che dopo 10 giorni sarà giovedì (se si parte da lunedì come giorno 0).

---

Questa sezione spiega gli operatori aritmetici di base in Python, inclusi la somma, sottrazione, moltiplicazione, divisione, divisione intera, potenza e modulo, con esempi pratici di come possono essere utilizzati senza introdurre strutture di controllo come if e cicli.

---

#### Operatori di confronto

Gli operatori di confronto confrontano due valori e restituiscono un valore booleano (`True` o `False`).

- **Esempi di operatori di confronto:**
  ```python
  x = 5
  y = 10

  print(x == y)  # False
  print(x != y)  # True
  print(x > y)  # False
  print(x < y)  # True
  print(x >= y)  # False
  print(x <= y)  # True
  ```

Questi operatori sono utilizzati comunemente nei blocchi condizionali.

---

#### Operatori logici

Gli operatori logici permettono di combinare più condizioni.

- **and, or, not:**
  ```python
  a = True
  b = False

  print(a and b)  # False
  print(a or b)  # True
  print(not a)  # False
  ```

Gli operatori logici sono usati per costruire espressioni condizionali complesse.

---

#### Operatori di assegnazione

Gli operatori di assegnazione sono usati per assegnare valori alle variabili.

- **Esempi di operatori di assegnazione:**
  ```python
  x = 5
  x += 3  # x è ora 8
  x -= 2  # x è ora 6
  x *= 2  # x è ora 12
  x /= 3  # x è ora 4.0
  x %= 2  # x è ora 0.0
  ```

Questi operatori semplificano le operazioni di aggiornamento delle variabili.

---

#### Operatori bitwise

Gli operatori bitwise eseguono operazioni sui bit dei numeri interi.

- **Esempi di operatori bitwise:**
  ```python
  a = 0b1100
  b = 0b1010

  print(bin(a & b))  # 0b1000
  print(bin(a | b))  # 0b1110
  print(bin(a ^ b))  # 0b0110
  print(bin(~a))  # -0b1101 (not bitwise)
  print(bin(a << 2))  # 0b110000
  print(bin(a >> 2))  # 0b0011
  ```

Questi operatori sono utili per manipolazioni di basso livello.

---

## Input/Output da Console

### Operazioni di Input

#### Funzione `input()`

La funzione `input()` permette di leggere dati dall'utente. Restituisce sempre una stringa, quindi spesso è necessario convertirla al tipo di dati appropriato.

- **Lettura di stringhe da input:**
  ```python
  nome = input("Come ti chiami? ")
  print("Ciao, " + nome)
  ```

- **Conversione dei tipi di input:**
  ```python
  eta = int(input("Quanti anni hai? "))
  print("Hai " + str(eta) + " anni.")
  ```

L'input dell'utente è fondamentale per interagire con i programmi.

---

---

---

### Input/Output da Console

### Operazioni di Input

#### Funzione `input()`

La funzione `input()` permette di leggere dati dall'utente. Quando viene chiamata, `input()` mette in pausa l'esecuzione del programma e attende che l'utente inserisca un dato, terminato dalla pressione del tasto Invio. Il valore inserito dall'utente viene restituito come una stringa.

- **Lettura di stringhe da input:**
  ```python
  nome = input("Come ti chiami? ")
  # Supponiamo che l'utente inserisca "Alice"
  print("Ciao, " + nome)
  # Output: Ciao, Alice
  ```

  In questo esempio, la funzione `input()` visualizza il prompt "Come ti chiami? ". Quando l'utente inserisce il proprio nome e preme Invio, il valore viene assegnato alla variabile `nome`, che viene poi utilizzata nella funzione `print()` per visualizzare un messaggio di saluto.

- **Conversione dei tipi di input:**
  Poiché `input()` restituisce sempre una stringa, spesso è necessario convertire il valore in un altro tipo di dato, come un intero o un numero in virgola mobile. Questo può essere fatto utilizzando le funzioni di conversione del tipo di dato, come `int()` o `float()`.

  ```python
  eta = input("Quanti anni hai? ")
  # Supponiamo che l'utente inserisca "30"
  eta = int(eta)  # Converte la stringa "30" in un intero 30
  print("Hai " + str(eta) + " anni.")
  # Output: Hai 30 anni.
  ```

  In questo esempio, la funzione `input()` legge l'età dell'utente come una stringa. La funzione `int()` converte la stringa in un intero, e poi la funzione `str()` converte nuovamente l'intero in una stringa per poter essere concatenata nel messaggio di output.

---

### Operazioni di Output

#### Funzione `print()`

La funzione `print()` è utilizzata per produrre output sulla console. Può accettare uno o più argomenti, separati da virgole, e visualizzarli in sequenza sulla console. La funzione `print()` aggiunge automaticamente un carattere di nuova riga alla fine dell'output, ma questo comportamento può essere modificato utilizzando il parametro `end`.

- **Output di base:**
  ```python
  print("Ciao, mondo!")
  # Output: Ciao, mondo!
  ```

  In questo esempio, la funzione `print()` visualizza la stringa "Ciao, mondo!" sulla console.

- **Argomenti multipli e separatori:**
  La funzione `print()` può accettare più argomenti e combinarli con uno spazio (per impostazione predefinita) o con un separatore specificato utilizzando il parametro `sep`.

  ```python
  print("Ciao", "mondo", sep=", ")
  # Output: Ciao, mondo
  ```

  In questo esempio, gli argomenti "Ciao" e "mondo" sono combinati con una virgola e uno spazio tra di loro.

- **Fine riga e fine di stampa:**
  Il parametro `end` specifica quale stringa aggiungere alla fine dell'output. Il valore predefinito è un carattere di nuova riga (`\n`).

  ```python
  print("Ciao", end="!")
  print("mondo")
  # Output: Ciao!mondo
  ```

  In questo esempio, il parametro `end="!"` modifica il comportamento di fine riga della funzione `print()`, così che il carattere "!" venga aggiunto alla fine dell'output invece di una nuova riga.

---

#### Formattazione delle stringhe

Esistono diversi modi per formattare le stringhe in Python, rendendo l'output più leggibile e strutturato.

- **f-strings (formatted string literals):**
  Le f-string (introdotte in Python 3.6) permettono di inserire espressioni all'interno delle stringhe precedute dal carattere `f`.

  ```python
  nome = "Alice"
  eta = 30
  print(f"{nome} ha {eta} anni.")
  # Output: Alice ha 30 anni.
  ```

  In questo esempio, le variabili `nome` ed `eta` sono inserite all'interno della stringa utilizzando le parentesi graffe `{}`.

---

#### Formattazione avanzata con f-strings

Le f-strings offrono molte opzioni avanzate per la formattazione delle stringhe, rendendo semplice il controllo preciso dell'output.

- **Padding (riempimento):**
  Aggiungere spazi per allineare il testo.

  ```python
  nome = "Alice"
  print(f"{nome:>10}")
  # Output:      Alice
  ```

  In questo esempio, `:>10` allinea il testo a destra, riempiendo con spazi per raggiungere una larghezza totale di 10 caratteri.

- **0 Padding:**
  Riempire con zeri anziché spazi.

  ```python
  numero = 42
  print(f"{numero:05}")
  # Output: 00042
  ```

  In questo esempio, `:05` formatta il numero con una larghezza totale di 5 caratteri, riempiendo con zeri a sinistra.

- **Specificare un numero di cifre decimali:**
  Controllare il numero di cifre decimali per numeri in virgola mobile.

  ```python
  pi_greco = 3.141592653589793
  print(f"{pi_greco:.2f}")
  # Output: 3.14
  ```

  In questo esempio, `:.2f` formatta il numero con 2 cifre decimali.

- **Conversione in binario, esadecimale e ottale:**
  Convertire numeri interi in altre basi numeriche.

  ```python
  numero = 255
  print(f"{numero:b}")
  # Output: 11111111

  print(f"{numero:x}")
  # Output: ff

  print(f"{numero:o}")
  # Output: 377
  ```

  In questi esempi, `:b` converte il numero in binario, `:x` in esadecimale e `:o` in ottale.

- **Formattazione con segni e spazi:**
  Aggiungere segni ai numeri positivi e negativi.

  ```python
  positivo = 42
  negativo = -42
  print(f"{positivo:+}")
  # Output: +42

  print(f"{negativo:+}")
  # Output: -42
  ```

  In questo esempio, `:+` aggiunge un segno positivo ai numeri positivi.

- **Formattazione di grandi numeri:**
  Aggiungere separatori di migliaia.

  ```python
  grande_numero = 1000000
  print(f"{grande_numero:,}")
  # Output: 1,000,000
  ```

  In questo esempio, `:,` inserisce una virgola come separatore di migliaia.

---

## Flusso di Controllo - Blocchi Condizionali e Loop

### Istruzione If

#### Sintassi dell'istruzione if

Le istruzioni condizionali permettono di eseguire diverse sezioni di codice basate su condizioni.

- **if semplice:**
  ```python
  x = 10
  if x > 5:
      print("x è maggiore di 5")
  ```

- **if-elif-else:**
  ```python
  x = 10
  if x < 5:
      print("x è minore di 5")
  elif x == 5:
      print("x è uguale a 5")
  else:
      print("x è maggiore di 5")
  ```

---

#### Esempi pratici

- **Condizioni multiple e annidate:**
  ```python
  x = 10
  y = 20
  if x > 5:
      if y > 15:
          print("x è maggiore di 5 e y è maggiore di 15")
      else:
          print("x è maggiore di 5 ma y non è maggiore di 15")
  ```

Questi blocchi condizionali sono fondamentali per il controllo del flusso di un programma.

---

### Loop

#### Loop for

I loop `for` sono usati per iterare su sequenze (liste, stringhe, range).

- **Iterare su sequenze:**
  ```python
  parole = ["Python", "è", "divertente"]
  for parola in parole:
      print(parola)
  ```

- **Funzione `range()`:**
  ```python
  for i in range(5):
      print(i)
  ```

---

#### Loop while

I loop `while` eseguono una sezione di codice finché una condizione è vera.

- **Condizioni di continuazione e terminazione:**
  ```python
  i = 0
  while i < 5:
      print(i)
      i += 1
  ```

---

#### Istruzioni di controllo del loop

- **break:** Esce dal loop.
  ```python
  for i in range(10):
      if i == 5:
          break
      print(i)
  ```

- **continue:** Salta alla prossima iterazione del loop.
  ```python
  for i in range(10):
      if i % 2 == 0:
          continue
      print(i)
  ```

- **pass:** Non fa nulla; è usato come segnaposto.
  ```python
  for i in range(10):
      if i < 5:
          pass
      else:
          print(i)
  ```

Queste istruzioni permettono di controllare il flusso all'interno dei loop.

---

## Data Collection - Tuple, Dizionari, Elenchi e Stringhe

### Liste

#### Creazione e manipolazione delle liste

Le liste sono collezioni ordinate di elementi che possono essere di qualsiasi tipo.

- **Liste vuote e popolazione di liste:**
  ```python
  lista_vuota = []
  lista_vuota.append(1)
  lista_vuota.append(2)
  lista_vuota.append(3)
  ```

- **Indicizzazione e slicing:**
  ```python
  lista = [1, 2, 3, 4, 5]
  primo_elemento = lista[0]
  ultimi_due = lista[-2:]
  ```

---

#### Metodi delle liste

Le liste in Python hanno molti metodi utili per la manipolazione dei dati.

- **append(), insert(), remove(), pop(), sort(), reverse():**
  ```python
  lista = [3, 1, 4, 1, 5]
  lista.append(9)  # Aggiunge un elemento alla fine
  lista.insert(2, 2)  # Inserisce un elemento alla posizione specificata
  lista.remove(1)  # Rimuove la prima occorrenza di 1
  lista.pop()  # Rimuove l'ultimo elemento


  lista.sort()  # Ordina la lista
  lista.reverse()  # Inverte l'ordine degli elementi
  ```

---

#### Liste nidificate e comprensione delle liste

- **Liste di liste:**
  ```python
  matrice = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
  elemento = matrice[1][2]  # 6
  ```

- **List comprehension:**
  ```python
  quadrati = [x**2 for x in range(10)]
  ```

La comprensione delle liste permette di creare nuove liste in modo conciso e leggibile.

---

### Tuple

#### Creazione e uso delle tuple

Le tuple sono simili alle liste, ma sono immutabili (non possono essere modificate dopo la loro creazione).

- **Tuple vuote e con un singolo elemento:**
  ```python
  tupla_vuota = ()
  tupla_un_elemento = (1,)
  ```

---

#### Differenze tra liste e tuple

- **Immutabilità delle tuple:** Le tuple non possono essere modificate dopo la loro creazione, il che le rende utili per dati che non dovrebbero cambiare.
- **Operazioni comuni su tuple:**
  ```python
  tupla = (1, 2, 3)
  primo_elemento = tupla[0]
  ```

Le tuple sono spesso usate per dati che sono logicamente correlati e non devono essere modificati.

---

### Dizionari

#### Creazione e uso dei dizionari

I dizionari sono collezioni non ordinate di coppie chiave-valore.

- **Dizionari vuoti e popolazione di dizionari:**
  ```python
  dizionario_vuoto = {}
  dizionario_vuoto["chiave"] = "valore"
  ```

- **Accesso e modifica di elementi:**
  ```python
  dizionario = {"nome": "Alice", "eta": 30}
  nome = dizionario["nome"]
  dizionario["eta"] = 31
  ```

---

#### Metodi dei dizionari

- **get(), keys(), values(), items(), update(), pop():**
  ```python
  valore = dizionario.get("nome")
  chiavi = dizionario.keys()
  valori = dizionario.values()
  coppie = dizionario.items()
  dizionario.update({"citta": "Roma"})
  dizionario.pop("eta")
  ```

---

#### Iterazione sui dizionari

- **Loop su chiavi, valori e coppie chiave-valore:**
  ```python
  for chiave, valore in dizionario.items():
      print(f"{chiave}: {valore}")
  ```

I dizionari sono molto utili per memorizzare e gestire dati strutturati.

---

### Stringhe

#### Operazioni base sulle stringhe

Le stringhe in Python sono immutabili, ma possono essere manipolate usando vari metodi.

- **Concatenazione, ripetizione, slicing:**
  ```python
  stringa1 = "Hello"
  stringa2 = "World"
  concatenata = stringa1 + " " + stringa2
  ripetuta = stringa1 * 3
  parte = stringa1[1:4]
  ```

---

#### Metodi delle stringhe

Le stringhe hanno molti metodi per manipolare il testo.

- **split(), join(), replace(), upper(), lower(), strip(), find():**
  ```python
  testo = "   Python è fantastico!   "
  lista_parole = testo.split()
  testo_unito = " ".join(lista_parole)
  testo_modificato = testo.replace("fantastico", "potente")
  maiuscolo = testo.upper()
  minuscolo = testo.lower()
  senza_spazi = testo.strip()
  posizione = testo.find("Python")
  ```

---

#### Formattazione avanzata

- **Template strings e moduli `string`:**
  ```python
  from string import Template
  t = Template("Ciao, $nome!")
  messaggio = t.substitute(nome="Alice")
  ```

La manipolazione delle stringhe è fondamentale per molte applicazioni, come l'elaborazione del testo e la costruzione di output leggibili.

---

## Funzioni ed Eccezioni

### Funzioni

#### Definizione e chiamata di funzioni

Le funzioni sono blocchi di codice riutilizzabili che eseguono un'operazione specifica.

- **Sintassi di definizione:**
  ```python
  def saluta():
      print("Ciao!")
  saluta()
  ```

Definire funzioni permette di strutturare il codice in modo più modulare e organizzato.

---

#### Parametri e argomenti

- **Parametri di default:**
  ```python
  def saluta(nome="mondo"):
      print(f"Ciao, {nome}!")
  saluta()
  saluta("Alice")
  ```

I parametri di default permettono di chiamare la funzione senza dover specificare tutti gli argomenti.

---

- **Argomenti arbitrari (*args e **kwargs):**
  ```python
  def somma(*numeri):
      return sum(numeri)
  print(somma(1, 2, 3))

  def mostra_info(**info):
      for chiave, valore in info.items():
          print(f"{chiave}: {valore}")
  mostra_info(nome="Alice", eta=30)
  ```

Gli argomenti arbitrari sono utili quando il numero di argomenti non è noto a priori.

---

#### Funzioni lambda

Le funzioni lambda sono funzioni anonime e brevi.

- **Definizione e uso delle espressioni lambda:**
  ```python
  quadrato = lambda x: x ** 2
  print(quadrato(5))
  ```

Le lambda sono utili per funzioni brevi e anonime che non necessitano di un nome.

---

### Gestione delle Eccezioni

#### Introduzione alle eccezioni

Le eccezioni sono eventi che interrompono il normale flusso di un programma. Python gestisce le eccezioni usando blocchi `try-except`.

---

- **Tipi di eccezioni comuni:** Alcuni tipi di eccezioni comuni sono `ValueError`, `TypeError`, `KeyError`, `IndexError`.

---

#### Sintassi del blocco try-except

- **Blocco try-except:**
  ```python
  try:
      x = int(input("Inserisci un numero: "))
  except ValueError:
      print("Errore: non è stato inserito un numero valido.")
  ```

Il blocco `try-except` permette di gestire errori in modo elegante senza interrompere il programma.

---

- **Clausole finally e else:**
  ```python
  try:
      x = int(input("Inserisci un numero: "))
  except ValueError:
      print("Errore: non è stato inserito un numero valido.")
  else:
      print("Numero inserito correttamente.")
  finally:
      print("Operazione completata.")
  ```

Il blocco `finally` viene eseguito indipendentemente dal fatto che un'eccezione sia stata sollevata o meno. Il blocco `else` viene eseguito solo se non viene sollevata alcuna eccezione.

---

## Moduli e Pacchetti

### Importazione di Moduli

#### Importare moduli built-in

Python ha molti moduli built-in che possono essere importati per aggiungere funzionalità extra.

- **Sintassi di importazione:**
  ```python
  import math
  print(math.sqrt(16))
  ```

Importare moduli permette di riutilizzare codice e aggiungere funzionalità senza doverle scrivere da zero.

---

- **Alias dei moduli:**
  ```python
  import numpy as np
  print(np.array([1, 2, 3]))
  ```

Usare alias rende il codice più conciso e leggibile.

---

### Moduli Specifici

#### Modulo math

Il modulo `math` fornisce funzioni matematiche comuni.

- **Funzioni matematiche comuni:**
  ```python
  import math
  print(math.pi)
  print(math.sin(math.radians(90)))
  ```

---

#### Modulo random

Il modulo `random` è usato per generare numeri casuali.

- **Generazione di numeri casuali e funzioni correlate:**
  ```python
  import random
  print(random.randint(1, 10))
  print(random.choice(['a', 'b', 'c']))
  ```

---

#### Modulo platform

Il modulo `platform` fornisce informazioni sul sistema operativo.

- **Informazioni sul sistema operativo:**
  ```python
  import platform
  print(platform.system())
  print(platform.release())
  ```

---

### Creazione di Moduli e Pacchetti

#### Scrivere e importare moduli personalizzati

Puoi creare i tuoi moduli per organizzare meglio il codice.

- **Definizione di un modulo:**
  Crea un file `mio_modulo.py`:
  ```python
  def saluta():
      print("Ciao dal modulo!")
  ```
  Importa e usa il modulo:
  ```python
  import mio_modulo
  mio_modulo.saluta()
  ```

---

- **Uso del modulo `__name__`:**
  ```python


  if __name__ == "__main__":
      print("Il modulo è stato eseguito direttamente")
  ```

---

#### Creare pacchetti Python

- **Struttura di un pacchetto:** Crea una cartella `mio_pacchetto` con un file `__init__.py` vuoto e altri moduli.
  ```plaintext
  mio_pacchetto/
      __init__.py
      modulo1.py
      modulo2.py
  ```

- **File `__init__.py`:** Importa i moduli nel pacchetto.
  ```python
  from .modulo1 import funzione1
  from .modulo2 import funzione2
  ```

La creazione di pacchetti permette di organizzare il codice in moduli riutilizzabili.

---

#### Utilizzo dei gestori di pacchetti

##### pip

`pip` è il gestore di pacchetti predefinito per Python, utilizzato per installare e gestire i pacchetti Python. È uno strumento potente che semplifica l'installazione di librerie e moduli necessari per i tuoi progetti.

- **Installare un pacchetto:**
  ```sh
  pip install nome_pacchetto
  ```
  Esempio:
  ```sh
  pip install requests
  ```

- **Aggiornare un pacchetto:**
  ```sh
  pip install --upgrade nome_pacchetto
  ```
  Esempio:
  ```sh
  pip install --upgrade requests
  ```

- **Disinstallare un pacchetto:**
  ```sh
  pip uninstall nome_pacchetto
  ```
  Esempio:
  ```sh
  pip uninstall requests
  ```

- **Visualizzare i pacchetti installati:**
  ```sh
  pip list
  ```
  Questo comando mostra una lista di tutti i pacchetti installati nel tuo ambiente.

- **Cercare un pacchetto:**
  ```sh
  pip search nome_pacchetto
  ```
  Esempio:
  ```sh
  pip search requests
  ```

- **Visualizzare le informazioni su un pacchetto:**
  ```sh
  pip show nome_pacchetto
  ```
  Esempio:
  ```sh
  pip show requests
  ```

- **Installare pacchetti da un file requirements.txt:**
  ```sh
  pip install -r requirements.txt
  ```
  Un file `requirements.txt` elenca tutti i pacchetti e le loro versioni necessarie per un progetto. Esempio di un file `requirements.txt`:
  ```
  requests==2.25.1
  numpy==1.19.5
  ```

---
 
##### venv

`venv` è un modulo incluso in Python 3 che permette di creare ambienti virtuali. Un ambiente virtuale è una directory che contiene un'installazione di Python isolata dal sistema globale, permettendo di gestire le dipendenze del progetto senza interferire con altri progetti.

- **Creare un ambiente virtuale:**
  ```sh
  python -m venv nome_ambiente
  ```
  Esempio:
  ```sh
  python -m venv mio_ambiente
  ```

- **Attivare l'ambiente virtuale:**
  - Su Windows:
    ```sh
    .\nome_ambiente\Scripts\activate
    ```
  - Su macOS e Linux:
    ```sh
    source nome_ambiente/bin/activate
    ```
  Esempio:
  ```sh
  source mio_ambiente/bin/activate
  ```

- **Disattivare l'ambiente virtuale:**
  ```sh
  deactivate
  ```
  Questo comando ti riporterà all'ambiente Python globale.

- **Utilizzo degli ambienti virtuali:**
  Quando un ambiente virtuale è attivato, `pip` installerà i pacchetti all'interno dell'ambiente, senza influenzare il sistema globale. Ad esempio:
  ```sh
  pip install requests
  ```
  Questo installerà `requests` solo nell'ambiente virtuale attivo.

- **Vantaggi degli ambienti virtuali:**
  - **Isolamento delle dipendenze:** Ogni progetto può avere le proprie dipendenze senza conflitti.
  - **Riproducibilità:** È possibile replicare esattamente l'ambiente di sviluppo in un altro sistema.
  - **Pulizia:** Mantiene il sistema globale pulito da pacchetti specifici del progetto.

---



## Gestione Avanzata delle Eccezioni

### Eccezioni Predefinite

#### Gerarchia delle eccezioni in Python

Le eccezioni in Python derivano dalla classe base `BaseException`. Capire la gerarchia delle eccezioni aiuta a gestirle in modo più efficace.

---

#### Eccezioni comuni

- **ValueError, TypeError, KeyError, IndexError:**
  ```python
  try:
      x = int("abc")
  except ValueError as e:
      print(f"Errore: {e}")
  ```

---

### Definire Eccezioni Personalizzate

#### Creazione di nuove classi di eccezioni

Puoi definire le tue eccezioni per gestire errori specifici.

- **Ereditarietà da Exception:**
  ```python
  class MiaEccezione(Exception):
      pass
  ```

---

#### Utilizzo delle eccezioni personalizzate

- **Rilancio di eccezioni e messaggi personalizzati:**
  ```python
  def controlla_valore(x):
      if x < 0:
          raise MiaEccezione("Il valore non può essere negativo")
  try:
      controlla_valore(-1)
  except MiaEccezione as e:
      print(f"Errore: {e}")
  ```

Le eccezioni personalizzate migliorano la leggibilità e la gestione degli errori nel codice.

---

## Stringhe - Operazioni Avanzate

### Meccanica delle Stringhe

#### Codifica dei caratteri

Le stringhe in Python supportano vari encodings.

- **ASCII vs Unicode:** ASCII è una codifica a 7 bit per caratteri. Unicode supporta molti più caratteri, inclusi quelli internazionali.
- **Encodings comuni (UTF-8, UTF-16):** UTF-8 è una codifica variabile per Unicode che usa 1-4 byte. UTF-16 usa 2 o 4 byte.

---

#### Byte e stringhe

Le stringhe possono essere convertite in byte e viceversa.

- **Conversione tra stringhe e byte:**
  ```python
stringa = "€"
byte_data = stringa.encode("utf-8")
print(byte_data) # stampa b'\xe2\x82\xac'
stringa_decodificata = byte_data.decode("utf-8")
print(stringa_decodificata) # stampa €
  ```

---

### Manipolazioni Avanzate

#### Regex e stringhe

Le espressioni regolari permettono di cercare e manipolare stringhe in modo avanzato.

- **Introduzione alle espressioni regolari:** Le espressioni regolari permettono di cercare e manipolare stringhe in modo avanzato.
- **Uso del modulo `re` per la ricerca e la sostituzione:**
  ```python
  import re
  testo = "Il numero è 123-456-7890"
  pattern = r'\d{3}-\d{3}-\d{4}'
  risultato = re.search(pattern, testo)
  print(risultato.group())
  ```

---

#### Operazioni di slicing e concatenazione

- **Tecniche avanzate di slicing:**
  ```python
  stringa = "Python è fantastico"
  print(stringa[7:])  # "è fantastico"
  print(stringa[:6])  # "Python"
  ```

- **Concatenazione efficiente delle stringhe:** Usa `join()` per concatenare liste di stringhe.
  ```python
  lista_stringhe = ["Python", "è", "fantastico"]
  risultato = " ".join(lista_stringhe)
  print(risultato)
  ```

---

## Programmazione Orientata agli Oggetti

### Concetti di Base

#### Introduzione alla programmazione orientata agli oggetti

La programmazione orientata agli oggetti (OOP) è un paradigma di programmazione che utilizza "oggetti" per rappresentare dati e metodi.

- **Principi fondamentali (incapsulamento, ereditarietà, polimorfismo):** L'incapsulamento nasconde i dettagli interni degli oggetti. L'ereditarietà permette di creare nuove classi basate su classi esistenti. Il polimorfismo consente di usare un'interfaccia comune per tipi diversi di dati.

---

#### Classi e oggetti

- **Definizione e istanziazione delle classi:**
  ```python
  class Persona:
      def __init__(self, nome, eta):
          self.nome = nome
          self.eta = eta

  persona1 = Persona("Alice", 30)
  print(persona1.nome)
  ```

Definire classi permette di creare oggetti che contengono dati e metodi correlati.

---

### Proprietà e Metodi

#### Definizione di proprietà

Le proprietà sono variabili associate agli oggetti.

- **Attributi di istanza e di classe:**
  ```python
  class Contatore:
      conteggio = 0

      def __init__(self):
          Contatore.conteggio += 1

  c1 = Contatore()
  c2 = Contatore()
  print(Contatore.conteggio)  # 2
  ```

---

#### Definizione di metodi

I metodi sono funzioni associate alle classi.

- **Metodi di istanza:**
  ```python
  class Persona:
      def __init__(self, nome, eta):
          self.nome = nome
          self.eta = eta

      def saluta(self):
          print(f"Ciao, mi chiamo {self.nome} e ho {self.eta} anni.")

  persona1 = Persona("Alice", 30)
  persona1.saluta()
  ```

---

- **Metodi di classe e metodi statici:**
  ```python
  class Matematica:
      @classmethod
      def pi_greco(cls):
          return 3.14159

      @staticmethod
      def quadrato(x):
          return x * x

  print(Matematica.pi_greco())
  print(Matematica.quadrato(5))
  ```

---

### Ereditarietà

#### Creazione di classi derivate

L'ereditarietà permette di creare nuove classi basate su classi esistenti.

- **Ereditarietà singola e multipla:**
  ```python
  class Animale:
      def __init__(self, nome):
          self.nome = nome

      def saluta(self):
          print(f"Ciao, sono un {self.nome}")

  class Cane(Animale):
      def abbaia(self):
          print("Bau!")

  cane = Cane("cane")
  cane.saluta()
  cane.abbaia()
  ```

---

#### Metodi override e super()

- **Sovrascrittura dei metodi:**
  ```python
  class Animale:
      def fa_rumore(self):
          print("Rumore generico")

  class Cane(Animale):
      def fa_rumore(self):
          print("Bau!")

  cane = Cane()
  cane.fa_rumore()  # Bau!
  ```

- **Utilizzo del metodo super():**
  ```python
  class Animale:
      def __init__(self, nome):
          self.nome = nome

  class Cane(Animale):
      def __init__(self, nome, razza):
          super().__init__(nome)
          self.razza = razza

  cane = Cane("Fido", "Labrador")
  print(cane.nome)
  print(cane.razza)
  ```

---

### Oggetti e Costruttori

#### Costruttori (`__init__`)

I costruttori sono metodi speciali usati per inizializzare gli oggetti.

- **Inizializzazione degli attributi:**
  ```python
  class Persona:
      def __init__(self, nome, eta):
          self.nome = nome
          self.eta = eta

  persona = Persona("Alice", 30)
  print(persona.nome)
  ```

---

#### Distruttori (`__del__`)

I distruttori sono metodi speciali usati per pulire le risorse quando un oggetto viene distrutto.

- **Pulizia delle risorse:**
  ```python
  class Risorsa:
      def __init__(self, nome):
          self.nome = nome
          print(f"{self.nome} creata")

      def __del__(self):
          print(f"{self.nome} distrutta")

  risorsa = Risorsa("Risorsa1")
  del risorsa
  ```

---

## Argomenti Avanzati

### List Comprehension

#### Sintassi e utilizzo delle list comprehension

Le list comprehension

 offrono un modo conciso per creare liste.

- **Esempi semplici e complessi:**
  ```python
  quadrati = [x**2 for x in range(10)]
  pari = [x for x in range(20) if x % 2 == 0]
  ```

---

#### Comprensione delle set e dei dizionari

- **Set comprehension:**
  ```python
  quadrati_set = {x**2 for x in range(10)}
  ```

- **Dictionary comprehension:**
  ```python
  quadrati_dict = {x: x**2 for x in range(10)}
  ```

---

### Funzioni Lambda

#### Definizione e uso delle lambda

Le funzioni lambda sono funzioni anonime e brevi.

- **Esempi pratici:**
  ```python
  somma = lambda a, b: a + b
  print(somma(5, 3))
  ```

---

#### Differenze tra lambda e funzioni tradizionali

- **Vantaggi e limitazioni delle lambda:** Le lambda sono utili per funzioni brevi e anonime. Tuttavia, per funzioni più complesse, è meglio usare definizioni regolari.

---

### Closures

#### Definizione e uso delle closures

Le closures sono funzioni che possono catturare e mantenere lo stato dalle loro scope di definizione.

- **Esempi pratici di utilizzo:**
  ```python
  def genera_moltiplicatore(n):
      def moltiplica(x):
          return x * n
      return moltiplica

  raddoppia = genera_moltiplicatore(2)
  print(raddoppia(5))  # 10
  ```

---

#### Decoratori

I decoratori sono una forma di closure che permettono di estendere il comportamento delle funzioni.

- **Introduzione ai decoratori:**
  ```python
  def decoratore(funzione):
      def wrapper():
          print("Prima della funzione")
          funzione()
          print("Dopo la funzione")
      return wrapper

  @decoratore
  def di_ciao():
      print("Ciao!")

  di_ciao()
  ```

---

### Input/Output

#### Operazioni di base su file

Python supporta la lettura e la scrittura di file.

- **Lettura e scrittura di file di testo:**
  ```python
  with open('file.txt', 'w') as file:
      file.write("Ciao, mondo!")

  with open('file.txt', 'r') as file:
      contenuto = file.read()
      print(contenuto)
  ```

---

#### Gestione dei file con `with`

L'uso di `with` garantisce che il file venga chiuso correttamente dopo l'uso.

- **Lettura e scrittura sicura:**
  ```python
  with open('file.txt', 'a') as file:
      file.write("\nAggiungi questa riga.")
  ```

La gestione dei file è essenziale per molte applicazioni, dalla memorizzazione dei dati alla lettura di configurazioni.