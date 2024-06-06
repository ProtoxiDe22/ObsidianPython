---
{"dg-publish":true,"permalink":"/01-python-programming/"}
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

## Data Collection - Liste, Tuple, Dizionari, Set e Stringhe

### Liste

Le liste sono collezioni ordinate di elementi che possono essere di qualsiasi tipo. Sono mutabili, il che significa che gli elementi possono essere modificati dopo la creazione della lista.

#### Creazione e manipolazione delle liste

- **Creazione di una lista:**
  Le liste possono essere create utilizzando le parentesi quadre `[]`, con gli elementi separati da virgole.

  ```python
  frutti = ["mela", "banana", "ciliegia"]
  # Lista con tre elementi: mela, banana, ciliegia
  ```

- **Liste vuote e popolazione di liste:**
  Una lista vuota può essere creata e popolata successivamente utilizzando il metodo `append()`.

  ```python
  numeri = []
  numeri.append(1)
  numeri.append(2)
  numeri.append(3)
  # Lista numeri: [1, 2, 3]
  ```

- **Indicizzazione:**
  Gli elementi di una lista possono essere accessibili utilizzando l'indice, partendo da 0.

  ```python
  primo_frutto = frutti[0]  # "mela"
  ultimo_frutto = frutti[-1]  # "ciliegia"
  # L'indice -1 accede all'ultimo elemento
  ```

- **Slicing:**
  Le liste possono essere "sliced" per ottenere sottoliste.

  ```python
  sottolista = frutti[1:3]
  # Sottolista contiene: ["banana", "ciliegia"]
  ```

---

#### Metodi delle liste

Le liste in Python hanno molti metodi integrati per manipolare i dati:

- **append():** Aggiunge un elemento alla fine della lista.

  ```python
  frutti.append("arancia")
  # Lista frutti: ["mela", "banana", "ciliegia", "arancia"]
  ```

- **insert():** Inserisce un elemento alla posizione specificata.

  ```python
  frutti.insert(1, "pera")
  # Lista frutti: ["mela", "pera", "banana", "ciliegia", "arancia"]
  ```

- **remove():** Rimuove la prima occorrenza di un elemento.

  ```python
  frutti.remove("banana")
  # Lista frutti: ["mela", "pera", "ciliegia", "arancia"]
  ```

- **pop():** Rimuove e restituisce l'elemento all'indice specificato (default: ultimo elemento).

  ```python
  ultimo = frutti.pop()
  # Rimosso "arancia", ultimo = "arancia", Lista frutti: ["mela", "pera", "ciliegia"]
  ```

- **sort():** Ordina la lista in ordine crescente.

  ```python
  numeri = [3, 1, 4, 1, 5]
  numeri.sort()
  # Lista numeri ordinata: [1, 1, 3, 4, 5]
  ```

- **reverse():** Inverte l'ordine degli elementi nella lista.

  ```python
  numeri.reverse()
  # Lista numeri invertita: [5, 4, 3, 1, 1]
  ```

---

#### Liste nidificate e comprensione delle liste

- **Liste nidificate:**
  Le liste possono contenere altre liste come elementi, creando strutture nidificate.

  ```python
  matrice = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
  elemento = matrice[1][2]  # 6
  # Accede all'elemento alla riga 1, colonna 2 della matrice
  ```

- **List comprehension:**
  Le list comprehension offrono un modo conciso per creare liste basate su espressioni e loop.

  ```python
  quadrati = [x**2 for x in range(10)]
  # Lista quadrati: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
  ```

  In questo esempio, la lista `quadrati` è generata elevando al quadrato ogni numero da 0 a 9.

---

### Tuple

Le tuple sono collezioni ordinate e immutabili di elementi. Una volta create, gli elementi di una tupla non possono essere modificati.

#### Creazione e uso delle tuple

- **Creazione di una tupla:**
  Le tuple possono essere create utilizzando le parentesi tonde `()`.

  ```python
  colori = ("rosso", "verde", "blu")
  # Tupla colori: ("rosso", "verde", "blu")
  ```

- **Tuple vuote e con un singolo elemento:**
  Una tupla vuota si crea con `()` e una tupla con un singolo elemento richiede una virgola finale.

  ```python
  vuota = ()
  singolo = ("solo",)
  # Tupla vuota: ()
  # Tupla singolo elemento: ("solo",)
  ```

- **Accesso agli elementi:**
  Gli elementi delle tuple sono accessibili tramite indice, come le liste.

  ```python
  primo_colore = colori[0]  # "rosso"
  ```

---

#### Differenze tra liste e tuple

- **Immutabilità delle tuple:**
  Le tuple non possono essere modificate dopo la creazione, il che le rende utili per memorizzare dati costanti.

  ```python
  # Tentare di modificare una tupla genererà un errore:
  # colori[0] = "giallo"  # TypeError: 'tuple' object does not support item assignment
  ```

- **Operazioni comuni su tuple:**
  Le tuple supportano operazioni come la concatenazione e la ripetizione.

  ```python
  altri_colori = ("giallo", "viola")
  tutti_i_colori = colori + altri_colori
  # Tupla tutti_i_colori: ("rosso", "verde", "blu", "giallo", "viola")
  ```

---


### Set

I set sono collezioni non ordinate e non indicizzate di elementi unici. Sono mutabili, il che significa che gli elementi possono essere aggiunti o rimossi, ma ogni elemento può apparire una sola volta.

#### Creazione e uso dei set

- **Creazione di un set:**
  I set possono essere creati utilizzando le parentesi graffe `{}` o la funzione `set()`.

  ```python
  numeri = {1, 2, 3, 4}
  # Set numeri: {1, 2, 3, 4}
  ```

  ```python
  animali = set(["gatto", "cane", "uccello"])
  # Set animali: {"gatto", "cane", "uccello"}
  ```

- **Set vuoti e popolazione di set:**
  Un set vuoto può essere creato e popolato successivamente.

  ```python
  colori = set()
  colori.add("rosso")
  colori.add("verde")
  # Set colori: {"rosso", "verde"}
  ```

---

#### Metodi dei set

- **add():** Aggiunge un elemento al set.

  ```python
  colori.add("blu")
  # Set colori: {"rosso", "verde", "blu"}
  ```

- **remove():** Rimuove un elemento dal set. Genera un errore se l'elemento non è presente.

  ```python
  colori.remove("verde")
  # Set colori: {"rosso", "blu"}
  ```

- **discard():** Rimuove un elemento dal set, se esiste. Non genera errore se l'elemento non è presente.

  ```python
  colori.discard("giallo")
  # Set colori rimane: {"rosso", "blu"}
  ```

- **union():** Restituisce un nuovo set contenente tutti gli elementi di due set.

  ```python
  altri_colori = {"giallo", "verde"}
  tutti_i_colori = colori.union(altri_colori)
  # Set tutti_i_colori: {"rosso", "blu", "giallo", "verde"}
  ```

- **intersection():** Restituisce un nuovo set contenente solo gli elementi comuni a entrambi i set.

  ```python
  set1 = {1, 2, 3}
  set2 = {2, 3, 4}
  comuni = set1.intersection(set2)
  # Set comuni: {2, 3}
  ```

- **difference():** Restituisce un nuovo set contenente gli elementi presenti nel primo set ma non nel secondo.

  ```python
  differenza = set1.difference(set2)
  # Set differenza: {1}
  ```

---

### Differenze tra Tuple e Set

Le tuple e i set sono due tipi di collezioni in Python che hanno caratteristiche e usi distinti:

#### **Tuple**

- **Ordinazione:** Le tuple sono collezioni ordinate. Gli elementi in una tupla mantengono un ordine fisso, e l'accesso agli elementi avviene tramite indice.
  ```python
  colori = ("rosso", "verde", "blu")
  primo_colore = colori[0]  # "rosso"
  ```

- **Immutabilità:** Le tuple sono immutabili, il che significa che non possono essere modificate dopo la loro creazione. Non è possibile aggiungere, rimuovere o alterare gli elementi di una tupla.
  ```python
  colori = ("rosso", "verde", "blu")
  # Tentativo di modifica: colori[0] = "giallo" genera un errore
  ```

- **Uso tipico:** Le tuple sono utilizzate quando si ha bisogno di una sequenza di elementi che non deve essere modificata. Sono spesso usate per memorizzare dati eterogenei e come chiavi in un dizionario, poiché le tuple possono essere hashate.
  ```python
  posizione = (42.3601, -71.0589)  # Coordinate geografiche immutabili
  ```

#### **Set**

- **Ordinazione:** I set sono collezioni non ordinate. Non mantengono l'ordine degli elementi e non supportano l'accesso tramite indice. Gli elementi possono apparire in un ordine qualsiasi.
  ```python
  frutti = {"mela", "banana", "ciliegia"}
  # Non è possibile accedere agli elementi tramite indice, ad esempio: frutti[0] genera un errore
  ```

- **Mutabilità:** I set sono mutabili, il che significa che possono essere modificati dopo la loro creazione. È possibile aggiungere, rimuovere o alterare gli elementi di un set.
  ```python
  frutti.add("arancia")
  frutti.remove("banana")
  # Set frutti aggiornato: {"mela", "ciliegia", "arancia"}
  ```

- **Unicità degli elementi:** I set non permettono duplicati. Ogni elemento in un set è unico. Se si tenta di aggiungere un duplicato, esso non verrà inserito.
  ```python
  numeri = {1, 2, 3, 3, 4}
  # Set numeri: {1, 2, 3, 4} (duplice "3" viene ignorato)
  ```

- **Uso tipico:** I set sono utilizzati quando è necessario memorizzare una collezione di elementi unici e non ordinati. Sono ideali per operazioni come l'unione, l'intersezione e la differenza di collezioni.
  ```python
  animali_domestici = {"cane", "gatto", "pesce"}
  animali_esotici = {"tigre", "elefante", "pesce"}
  solo_domestici = animali_domestici - animali_esotici
  # Set solo_domestici: {"cane", "gatto"}
  ```

#### **Sintesi**

- **Ordinazione:** Le tuple mantengono l'ordine degli elementi, mentre i set no.
- **Mutabilità:** Le tuple sono immutabili, i set sono mutabili.
- **Accesso agli elementi:** Le tuple supportano l'accesso tramite indice, i set no.
- **Unicità:** I set contengono solo elementi unici, le tuple possono avere duplicati.
- **Uso:** Le tuple sono usate per dati immutabili e ordinati; i set sono usati per collezioni di elementi unici e non ordinati.

---

### Dizionari

I dizionari sono collezioni non ordinate di coppie chiave-valore, dove ogni chiave è unica. Sono mutabili e permettono accesso rapido ai valori basato sulla chiave.

#### Creazione e uso dei dizionari

- **Creazione di un dizionario:**
  I dizionari possono essere creati usando le parentesi graffe `{}` con coppie chiave-valore separate da due punti `:`.

  ```python
  studente = {"nome": "Alice", "eta": 24, "corso": "Informatica"}
  # Dizionario studente: {"nome": "Alice", "eta": 24, "corso": "Informatica"}
  ```

- **Dizionari vuoti e popolazione di dizionari:**
  Un dizionario vuoto può essere creato e popolato successivamente aggiungendo coppie chiave-valore.

  ```python
  dati = {}
  dati["città"] = "Roma"
  dati["popolazione"] = 2873000
  # Dizionario dati: {"città": "Roma", "popolazione": 2873000}
  ```

- **Accesso e modifica di elementi:**
  I valori possono essere accessibili e modificati usando le chiavi.

  ```python
  eta_studente = studente["eta"]  # 24
  studente["eta"] = 25
  # Modificata età: {"nome": "Alice", "eta": 25, "corso": "Informatica"}
  ```

---
#### Metodi dei dizionari

- **get():** Recupera il valore associato a una chiave, restituendo `None` se la chiave non esiste.

  ```python
  nome = studente.get("nome")
  # Output: "Alice"
  ```

- **keys():** Restituisce una vista delle chiavi del dizionario.

  ```python
  chiavi = list(studente.keys())
  # Lista di chiavi: ["nome", "eta", "corso"]
  ```

- **values():** Restituisce una vista dei valori del dizionario.

  ```python
  valori = list(studente.values())
  # Lista di valori: ["Alice", 25, "Informatica"]
  ```

- **items():** Restituisce una vista delle coppie chiave-valore del dizionario.

  ```python
  elementi = list(studente.items())
  # Lista di coppie chiave-valore: [("nome", "Alice"), ("eta", 25), ("corso", "Informatica")]
  ```

- **update():** Aggiorna il dizionario con le coppie chiave-valore di un altro dizionario.

  ```python
  studente.update({"eta": 26, "università": "La Sapienza"})
  # Dizionario aggiornato: {"nome": "Alice", "eta": 26, "corso": "Informatica", "università": "La Sapienza"}
  ```

- **pop():** Rimuove e restituisce il valore associato a una chiave.

  ```python
  corso = studente.pop("corso")
  # Rimosso corso, valore: "Informatica", Dizionario studente: {"nome": "Alice", "eta": 26, "università": "La Sapienza"}
  ```

---

### Stringhe

Le stringhe in Python sono sequenze immutabili di caratteri. Supportano molte operazioni e metodi utili per la manipolazione del testo.

#### Operazioni base sulle stringhe

- **Concatenazione:**
  Le stringhe possono essere concatenate usando l'operatore `+`.

  ```python
  saluto = "Ciao, "
  nome = "Alice"
  messaggio = saluto + nome
  # Output: "Ciao, Alice"
  ```

- **Ripetizione:**
  Le stringhe possono essere ripetute usando l'operatore `*`.

  ```python
  risata = "ha" * 3
  # Output: "hahaha"
  ```

- **Slicing:**
  Le stringhe possono essere "sliced" per ottenere sottostringhe.

  ```python
  testo = "Python è fantastico"
  parte = testo[7:10]
  # Output: "è f"
  ```

---

#### Metodi delle stringhe

Le stringhe in Python hanno molti metodi utili per la manipolazione del testo:

- **split():** Divide la stringa in una lista di sottostringhe usando un delimitatore.

  ```python
  testo = "Python è fantastico"
  parole = testo.split()
  # Lista di parole: ["Python", "è", "fantastico"]
  ```

- **join():** Unisce una lista di stringhe in una singola stringa, usando un delimitatore.

  ```python
  parole = ["Python", "è", "fantastico"]
  frase = " ".join(parole)
  # Output: "Python è fantastico"
  ```

- **replace():** Sostituisce tutte le occorrenze di una sottostringa con un'altra.

  ```python
  testo = "Python è fantastico"
  nuovo_testo = testo.replace("fantastico", "potente")
  # Output: "Python è potente"
  ```

- **upper() e lower():** Converte la stringa in maiuscolo o minuscolo.

  ```python
  testo = "Python"
  maiuscolo = testo.upper()
  minuscolo = testo.lower()
  # Output maiuscolo: "PYTHON"
  # Output minuscolo: "python"
  ```

- **strip():** Rimuove gli spazi bianchi iniziali e finali della stringa.

  ```python
  testo = "   Python è fantastico!   "
  testo_pulito = testo.strip()
  # Output: "Python è fantastico!"
  ```

- **find():** Trova la posizione della prima occorrenza di una sottostringa.

  ```python
  testo = "Python è fantastico"
  posizione = testo.find("fantastico")
  # Output: 10
  ```

---

### Utilizzo della funzione `len()`

La funzione `len()` restituisce la lunghezza di una collezione (numero di elementi) o di una stringa (numero di caratteri). Può essere utilizzata con liste, tuple, dizionari, set e stringhe.

- **Liste:**
  ```python
  frutti = ["mela", "banana", "ciliegia"]
  lunghezza = len(frutti)
  # Output: 3
  ```

- **Tuple:**
  ```python
  colori = ("rosso", "verde", "blu")
  lunghezza = len(colori)
  # Output: 3
  ```

- **Dizionari:**
  ```python
  studente = {"nome": "Alice", "eta": 24, "corso": "Informatica"}
  lunghezza = len(studente)
  # Output: 3
  ```

- **Set:**
  ```python
  numeri = {1, 2, 3, 4}
  lunghezza = len(numeri)
  # Output: 4
  ```

- **Stringhe:**
  ```python
  testo = "Python"
  lunghezza = len(testo)
  # Output: 6
  ```

In tutti questi esempi, la funzione `len()` viene utilizzata per determinare il numero di elementi nelle diverse collezioni o il numero di caratteri in una stringa.

---

---

## Funzioni ed Eccezioni

### Funzioni

Le funzioni sono blocchi di codice riutilizzabili che eseguono un'operazione specifica. Permettono di organizzare il codice in modo modulare, facilitando la leggibilità e la manutenzione.

#### Definizione e chiamata di funzioni

- **Definizione di una funzione:**
  Una funzione in Python viene definita utilizzando la parola chiave `def`, seguita dal nome della funzione e dalle parentesi `()` che possono contenere parametri. Il corpo della funzione è indentato e può includere un'istruzione `return` per restituire un valore.

  ```python
  def saluta():
      print("Ciao!")
  # Definisce una funzione chiamata saluta che stampa "Ciao!"
  ```

- **Chiamata di una funzione:**
  Una funzione viene chiamata utilizzando il suo nome seguito dalle parentesi `()` che possono contenere argomenti.

  ```python
  saluta()
  # Output: Ciao!
  ```

---

#### Parametri e argomenti

Le funzioni possono accettare input sotto forma di parametri, che sono variabili elencate tra le parentesi nella definizione della funzione. Gli argomenti sono i valori effettivi che vengono passati quando la funzione viene chiamata.

- **Parametri posizionali:**
  I parametri posizionali sono passati in base alla posizione. L'ordine degli argomenti deve corrispondere all'ordine dei parametri nella definizione della funzione.

  ```python
  def somma(a, b):
      return a + b

  risultato = somma(5, 3)
  # Output: 8
  ```

  In questo esempio, gli argomenti `5` e `3` sono passati ai parametri `a` e `b` rispettivamente in base alla loro posizione.

- **Parametri di default:**
  I parametri di default sono definiti con un valore predefinito e possono essere omessi nella chiamata della funzione.

  ```python
  def saluta(nome="mondo"):
      print(f"Ciao, {nome}!")

  saluta()
  # Output: Ciao, mondo!

  saluta("Alice")
  # Output: Ciao, Alice!
  ```

  In questo esempio, se non viene passato alcun argomento, il parametro `nome` assume il valore predefinito `"mondo"`.

- **Argomenti con nome (keyword arguments):**
  Gli argomenti possono essere passati specificando il nome del parametro, indipendentemente dalla loro posizione.

  ```python
  def sottrai(a, b):
      return a - b

  risultato = sottrai(b=5, a=10)
  # Output: 5
  ```

  In questo esempio, gli argomenti sono passati utilizzando i nomi dei parametri `a` e `b`, quindi l'ordine non è importante.

---

#### Parametri variabili

Python consente di passare un numero variabile di argomenti a una funzione utilizzando `*args` e `**kwargs`.

- **Argomenti arbitrari (*args):**
  Il parametro `*args` consente di passare un numero variabile di argomenti posizionali. All'interno della funzione, `args` è una tupla che contiene tutti gli argomenti posizionali passati.

  ```python
  def somma_tutti(*args):
      return sum(args)

  risultato = somma_tutti(1, 2, 3, 4)
  # Output: 10
  ```

  In questo esempio, `*args` raccoglie tutti gli argomenti posizionali passati alla funzione `somma_tutti` in una tupla, e la funzione `sum()` calcola la somma degli elementi.

- **Argomenti con nome arbitrari (**kwargs):**
  Il parametro `**kwargs` consente di passare un numero variabile di argomenti con nome. All'interno della funzione, `kwargs` è un dizionario che contiene tutte le coppie chiave-valore passate.

  ```python
  def stampa_informazioni(**kwargs):
      for chiave, valore in kwargs.items():
          print(f"{chiave}: {valore}")

  stampa_informazioni(nome="Alice", eta=30, città="Roma")
  # Output:
  # nome: Alice
  # eta: 30
  # città: Roma
  ```

  In questo esempio, `**kwargs` raccoglie tutti gli argomenti con nome passati alla funzione `stampa_informazioni` in un dizionario, e un ciclo `for` viene utilizzato per stampare ciascuna coppia chiave-valore.

- **Combinazione di parametri:**
  È possibile combinare parametri normali, `*args` e `**kwargs` in una funzione. L'ordine dei parametri deve essere: parametri normali, `*args`, `**kwargs`.

  ```python
  def mostra_dettagli(parametro_fisso, *args, **kwargs):
      print(f"Parametro fisso: {parametro_fisso}")
      print("args:", args)
      print("kwargs:", kwargs)

  mostra_dettagli("obbligatorio", 1, 2, 3, chiave1="valore1", chiave2="valore2")
  # Output:
  # Parametro fisso: obbligatorio
  # args: (1, 2, 3)
  # kwargs: {'chiave1': 'valore1', 'chiave2': 'valore2'}
  ```

  In questo esempio, la funzione `mostra_dettagli` accetta un parametro fisso, argomenti posizionali variabili e argomenti con nome variabili, dimostrando la flessibilità nella definizione delle funzioni in Python.


---
### Gestione delle Eccezioni

#### Introduzione alle eccezioni

Le eccezioni sono eventi che interrompono il normale flusso di un programma. Python gestisce le eccezioni usando blocchi `try-except`.


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

I moduli e i pacchetti sono strumenti essenziali in Python che permettono di organizzare il codice in maniera modulare, facilitando il riuso e la gestione delle dipendenze.

### Importazione di Moduli

I moduli in Python sono file che contengono definizioni di funzioni, variabili e classi che possono essere riutilizzate in altri file.

#### Importare moduli built-in

Python viene fornito con molti moduli built-in che offrono funzionalità estese. Puoi importare questi moduli usando la parola chiave `import`.

- **Sintassi di importazione:**
  ```python
  import math
  print(math.sqrt(16))
  # Output: 4.0
  ```

  In questo esempio, importiamo il modulo `math` e usiamo la funzione `sqrt()` per calcolare la radice quadrata di 16.

- **Importazione di funzioni specifiche da un modulo:**
  Puoi importare funzioni specifiche direttamente usando `from ... import ...`.

  ```python
  from math import pi, sin
  print(pi)
  # Output: 3.141592653589793
  print(sin(pi/2))
  # Output: 1.0
  ```

  In questo esempio, importiamo solo `pi` e `sin` dal modulo `math`.

- **Alias dei moduli:**
  Puoi rinominare un modulo usando `as` per rendere il codice più conciso.

  ```python
  import numpy as np
  array = np.array([1, 2, 3])
  print(array)
  # Output: [1 2 3]
  ```

  In questo esempio, importiamo il modulo `numpy` come `np` e creiamo un array.

---
---

### Moduli Specifici

Python offre una vasta gamma di moduli built-in che forniscono funzionalità estese. Qui approfondiamo i moduli `math`, `random`, `platform`, e `os`, elencando le loro funzioni più utilizzate.

#### Modulo `math`

Il modulo `math` fornisce funzioni matematiche standard, tra cui:

- **`math.sqrt(x)`**: Restituisce la radice quadrata di `x`.
  ```python
  import math
  print(math.sqrt(16))
  # Output: 4.0
  ```

- **`math.sin(x)`**: Restituisce il seno di `x` (dove `x` è in radianti).
  ```python
  print(math.sin(math.pi / 2))
  # Output: 1.0
  ```

- **`math.cos(x)`**: Restituisce il coseno di `x`.
  ```python
  print(math.cos(0))
  # Output: 1.0
  ```

- **`math.log(x[, base])`**: Restituisce il logaritmo di `x` alla base specificata (default: base `e`).
  ```python
  print(math.log(100, 10))
  # Output: 2.0
  ```

- **`math.factorial(x)`**: Restituisce il fattoriale di `x`.
  ```python
  print(math.factorial(5))
  # Output: 120
  ```

- **`math.pi`**: Costante che rappresenta il valore di π.
  ```python
  print(math.pi)
  # Output: 3.141592653589793
  ```

- **`math.e`**: Costante che rappresenta il valore di `e`.
  ```python
  print(math.e)
  # Output: 2.718281828459045
  ```

---

#### Modulo `random`

Il modulo `random` è usato per generare numeri casuali e funzioni correlate:

- **`random.randint(a, b)`**: Restituisce un numero intero casuale `N` tale che `a <= N <= b`.
  ```python
  import random
  print(random.randint(1, 10))
  # Output: un numero intero casuale tra 1 e 10
  ```

- **`random.random()`**: Restituisce un numero casuale in virgola mobile tra 0.0 e 1.0.
  ```python
  print(random.random())
  # Output: un numero casuale in virgola mobile tra 0.0 e 1.0
  ```

- **`random.choice(seq)`**: Restituisce un elemento casuale dalla sequenza `seq`.
  ```python
  elementi = ['rosso', 'verde', 'blu']
  print(random.choice(elementi))
  # Output: un elemento casuale tra 'rosso', 'verde', 'blu'
  ```

- **`random.shuffle(seq)`**: Mescola gli elementi della sequenza `seq` in loco.
  ```python
  carte = ['asso', 're', 'regina', 'fante']
  random.shuffle(carte)
  print(carte)
  # Output: una lista mescolata degli elementi
  ```

- **`random.sample(seq, k)`**: Restituisce una nuova lista di `k` elementi casuali presi dalla sequenza `seq`.
  ```python
  numeri = list(range(10))
  print(random.sample(numeri, 3))
  # Output: una lista di 3 elementi casuali da numeri
  ```

---

#### Modulo `platform`

Il modulo `platform` fornisce informazioni sul sistema operativo:

- **`platform.system()`**: Restituisce il nome del sistema operativo.
  ```python
  import platform
  print(platform.system())
  # Output: nome del sistema operativo (es. "Windows", "Linux")
  ```

- **`platform.release()`**: Restituisce la versione del sistema operativo.
  ```python
  print(platform.release())
  # Output: versione del sistema operativo
  ```

- **`platform.version()`**: Restituisce la versione dettagliata del sistema operativo.
  ```python
  print(platform.version())
  # Output: dettagli della versione del sistema operativo
  ```

- **`platform.processor()`**: Restituisce informazioni sul processore.
  ```python
  print(platform.processor())
  # Output: dettagli del processore (es. "Intel64 Family 6 Model 142 Stepping 10, GenuineIntel")
  ```

- **`platform.python_version()`**: Restituisce la versione di Python in uso.
  ```python
  print(platform.python_version())
  # Output: versione di Python (es. "3.10.1")
  ```

---

#### Modulo `os`

Il modulo `os` fornisce una portabilità del sistema operativo e funzioni per interagire con il filesystem:

- **`os.name`**: Restituisce il nome del sistema operativo dipendente dal modulo in uso (`posix`, `nt`, `os2`, `ce`, `java`, `riscos`).
  ```python
  import os
  print(os.name)
  # Output: nome del sistema operativo dipendente dal modulo (es. "posix" per Linux, "nt" per Windows)
  ```

- **`os.getcwd()`**: Restituisce la directory corrente di lavoro.
  ```python
  print(os.getcwd())
  # Output: percorso della directory corrente
  ```

- **`os.listdir(path)`**: Restituisce una lista dei file nella directory specificata.
  ```python
  print(os.listdir('.'))
  # Output: lista dei file nella directory corrente
  ```

- **`os.mkdir(path)`**: Crea una nuova directory al percorso specificato.
  ```python
  os.mkdir('nuova_cartella')
  # Crea una directory chiamata 'nuova_cartella'
  ```

- **`os.remove(path)`**: Rimuove il file specificato.
  ```python
  os.remove('vecchio_file.txt')
  # Rimuove il file 'vecchio_file.txt'
  ```

- **`os.rmdir(path)`**: Rimuove la directory specificata. La directory deve essere vuota.
  ```python
  os.rmdir('vecchia_cartella')
  # Rimuove la directory 'vecchia_cartella'
  ```

- **`os.path.exists(path)`**: Restituisce `True` se il percorso specificato esiste.
  ```python
  print(os.path.exists('nuova_cartella'))
  # Output: True o False a seconda se 'nuova_cartella' esiste
  ```

- **`os.path.join(path, *paths)`**: Unisce uno o più componenti del percorso in modo sensato per il sistema operativo.
  ```python
  percorso_completo = os.path.join('dir', 'sottodir', 'file.txt')
  print(percorso_completo)
  # Output: 'dir/sottodir/file.txt' su Unix o 'dir\\sottodir\\file.txt' su Windows
  ```


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
