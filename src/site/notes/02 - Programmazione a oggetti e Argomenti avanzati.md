---
{"dg-publish":true,"permalink":"/02-programmazione-a-oggetti-e-argomenti-avanzati/"}
---


## Programmazione Orientata agli Oggetti

La Programmazione Orientata agli Oggetti (OOP) è un paradigma di programmazione che utilizza "oggetti" e "classi" per strutturare il codice. È un modo di organizzare il software che cerca di modellare il mondo reale in termini di entità con attributi e comportamenti. In Python, questo paradigma è ampiamente utilizzato per rendere il codice più modularizzato, riutilizzabile e manutenibile.

### Concetti di Base

#### Introduzione alla Programmazione Orientata agli Oggetti

La OOP si basa su quattro principi fondamentali:
1. **Incapsulamento**
2. **Ereditarietà**
3. **Polimorfismo**
4. **Astrazione**

**Incapsulamento** implica la limitazione dell'accesso agli attributi e ai metodi di un oggetto, fornendo solo un'interfaccia pubblica per interagire con esso. **Ereditarietà** permette di creare nuove classi basate su classi esistenti. **Polimorfismo** consente di trattare oggetti di diversi tipi in modo uniforme. **Astrazione** consiste nel nascondere i dettagli complessi e mostrare solo le caratteristiche essenziali.

#### Classi e Oggetti

**Classe**: È un modello (o blueprint) che definisce la struttura e il comportamento degli oggetti. Una classe specifica cosa un oggetto "è" e cosa può "fare".

**Oggetto**: È un'istanza di una classe. È una rappresentazione concreta di qualcosa basato sulla classe, con dati e comportamento definiti.

##### Definizione e Istanziazione delle Classi

- **Definire una classe:**
  ```python
  class Animale:
      def __init__(self, nome, specie):
          self.nome = nome  # Attributo
          self.specie = specie  # Attributo

      def saluta(self):
          return f"Ciao, sono {self.nome} e sono un {self.specie}."  # Metodo
  ```

  In questo esempio, `Animale` è una classe che definisce cosa significa essere un "animale" con attributi `nome` e `specie`, e un metodo `saluta()`.

- **Creare un oggetto (istanza) di una classe:**
  ```python
  mio_animale = Animale("Fido", "cane")
  print(mio_animale.saluta())
  # Output: Ciao, sono Fido e sono un cane.
  ```

  Qui, `mio_animale` è un oggetto della classe `Animale`. Viene creato usando la classe `Animale`, e i valori `Fido` e `cane` vengono passati al costruttore `__init__` per inizializzare gli attributi dell'oggetto.

---

### Proprietà e Metodi

Le **proprietà** sono attributi o dati che gli oggetti possiedono, mentre i **metodi** sono funzioni definite all'interno di una classe che descrivono i comportamenti degli oggetti.

#### Definizione di Proprietà

- **Attributi di istanza:** Sono definiti all'interno del metodo `__init__` e specifici per ogni istanza.

  ```python
  class Persona:
      def __init__(self, nome, eta):
          self.nome = nome
          self.eta = eta
  ```

  In questo esempio, `nome` ed `eta` sono attributi di istanza.

- **Attributi di classe:** Sono condivisi tra tutte le istanze della classe.

  ```python
  class Persona:
      specie = "Homo sapiens"  # Attributo di classe

      def __init__(self, nome, eta):
          self.nome = nome  # Attributo di istanza
          self.eta = eta  # Attributo di istanza
  ```

  In questo esempio, `specie` è un attributo di classe che sarà lo stesso per tutte le istanze di `Persona`.

#### Definizione di Metodi

- **Metodi di istanza:** Operano sui dati contenuti in un'istanza della classe. Devono avere `self` come primo parametro.

  ```python
  class Persona:
      def __init__(self, nome, eta):
          self.nome = nome
          self.eta = eta

      def descrizione(self):
          return f"{self.nome} ha {self.eta} anni."
  ```

  In questo esempio, `descrizione` è un metodo di istanza che accede agli attributi `nome` ed `eta`.

- **Metodi di classe e metodi statici:** Non operano su un'istanza ma sulla classe stessa.

  ```python
  class Persona:
      numero_persona = 0  # Attributo di classe

      def __init__(self, nome, eta):
          self.nome = nome
          self.eta = eta
          Persona.numero_persona += 1

      @classmethod
      def conta_persone(cls):
          return f"Ci sono {cls.numero_persona} persone."

      @staticmethod
      def saluto_generale():
          return "Ciao a tutti!"
  ```

  In questo esempio, `conta_persone` è un metodo di classe che opera su `numero_persona`, mentre `saluto_generale` è un metodo statico che non opera né su attributi di classe né di istanza.

---

### Ereditarietà

L'**ereditarietà** permette di creare una nuova classe basata su un'altra classe esistente. La nuova classe (sottoclasse) eredita attributi e metodi dalla classe esistente (superclasse).

#### Creazione di Classi Derivate

- **Esempio di ereditarietà:**
  ```python
  class Animale:
      def __init__(self, nome):
          self.nome = nome

      def parla(self):
          pass  # Questo metodo sarà sovrascritto

  class Cane(Animale):
      def parla(self):
          return f"{self.nome} dice Woof!"

  class Gatto(Animale):
      def parla(self):
          return f"{self.nome} dice Meow!"
  ```

  In questo esempio, `Cane` e `Gatto` sono sottoclassi di `Animale`. Entrambe sovrascrivono il metodo `parla`.

#### Metodi Override e `super()`

- **Override dei metodi:** Una sottoclasse può fornire una propria implementazione di un metodo definito nella superclasse.

  ```python
  class Cane(Animale):
      def parla(self):
          return f"{self.nome} dice Woof!"
  ```

  In questo esempio, `parla` è sovrascritto nella sottoclasse `Cane`.

- **Utilizzo del metodo `super()`:** Permette di accedere ai metodi della superclasse dalla sottoclasse.

  ```python
  class Cane(Animale):
      def __init__(self, nome, razza):
          super().__init__(nome)  # Chiama il costruttore della superclasse
          self.razza = razza

      def parla(self):
          return f"{self.nome} della razza {self.razza} dice Woof!"
  ```

  In questo esempio, `super().__init__(nome)` chiama il costruttore della superclasse `Animale` per inizializzare `nome`.

---

### Oggetti e Costruttori

Il **costruttore** è un metodo speciale (`__init__`) che viene eseguito automaticamente quando un oggetto viene creato, per inizializzare gli attributi dell'oggetto.

#### Costruttori (`__init__`)

- **Esempio di costruttore:**
  ```python
  class Auto:
      def __init__(self, marca, modello):
          self.marca = marca
          self.modello = modello

      def descrizione(self):
          return f"Auto: {self.marca} {self.modello}"
  ```

  In questo esempio, il costruttore `__init__` inizializza gli attributi `marca` e `modello`.

#### Distruttori (`__del__`)

Il **distruttore** è un metodo speciale (`__del__`) che viene eseguito quando un oggetto viene distrutto. È usato per pulire le risorse.

- **Esempio di distruttore:**
  ```python
  class FileHandler:
      def __init__(self, nome_file):
          self.file = open(nome_file, 'r')

      def __del__(self):
          self.file.close()
          print("File chiuso.")

  handler = FileHandler('test.txt')
  # Quando l'oggetto `handler` è distrutto, il file è chiuso automaticamente
  ```

  In questo esempio, il distruttore `__del__` chiude il file quando l'oggetto `handler` è distrutto.

---

### Esempio Completo di Programmazione a Oggetti

**Definizione delle classi:**

```python
class Persona:
    def __init__(self, nome, eta):
        self.nome = nome
        self.eta = eta

    def descrizione(self):
        return f"{self.nome} ha {self.eta} anni."

class Studente(Persona):
    def __init__(self, nome, eta, corso):
        super().__init__(nome, eta)
       

 self.corso = corso

    def descrizione(self):
        return f"{self.nome} ha {self.eta} anni e studia {self.corso}."
```

**Creazione e uso degli oggetti:**

```python
persona = Persona("Alice", 30)
print(persona.descrizione())
# Output: Alice ha 30 anni.

studente = Studente("Bob", 20, "Informatica")
print(studente.descrizione())
# Output: Bob ha 20 anni e studia Informatica.
```

In questo esempio, `Persona` è la superclasse e `Studente` è la sottoclasse che estende `Persona` aggiungendo l'attributo `corso` e sovrascrivendo il metodo `descrizione`.


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

Certamente! Ecco la sezione sulle funzioni lambda aggiornata con esempi reali, accompagnati dalle versioni equivalenti senza l'uso di lambda per un confronto chiaro.

---

### Funzioni lambda

Le funzioni lambda sono funzioni anonime e brevi, definite utilizzando la parola chiave `lambda`. Sono utili per eseguire operazioni semplici che non richiedono una funzione nominata. Le lambda vengono interpretate come funzioni inline che possono essere passate come argomenti ad altre funzioni.

#### Definizione e utilizzo delle espressioni lambda

- **Sintassi di base:**
  Una funzione lambda in Python è definita usando la sintassi:
  ```python
  lambda parametri: espressione
  ```
  Dove:
  - `parametri` è una lista di parametri separati da virgole.
  - `espressione` è un'operazione singola eseguita sulla base dei parametri.

  **Esempio con lambda:**
  ```python
  doppio = lambda x: x * 2
  print(doppio(5))
  # Output: 10
  ```

  **Esempio equivalente senza lambda:**
  ```python
  def raddoppia(x):
      return x * 2

  print(raddoppia(5))
  # Output: 10
  ```

  In questo esempio, `lambda x: x * 2` crea una funzione anonima che moltiplica `x` per 2. La funzione viene assegnata alla variabile `doppio` e invocata con l'argomento `5`. La versione senza lambda utilizza una funzione nominata `raddoppia`.

---

#### Utilizzo reale delle lambda

Le funzioni lambda sono utili in situazioni dove è richiesta una funzione breve e senza nome. Sono comunemente utilizzate con funzioni che accettano altre funzioni come argomenti.

- **Ordinamento con `sorted()`:**
  La funzione `sorted()` può accettare una funzione chiave che determina l'ordine degli elementi. Le lambda possono essere utilizzate per definire questa funzione chiave inline.

  **Esempio con lambda:**
  ```python
  studenti = [
      {"nome": "Alice", "eta": 25},
      {"nome": "Bob", "eta": 20},
      {"nome": "Charlie", "eta": 23}
  ]
  
  ordinati_per_eta = sorted(studenti, key=lambda studente: studente["eta"])
  print(ordinati_per_eta)
  # Output: [{'nome': 'Bob', 'eta': 20}, {'nome': 'Charlie', 'eta': 23}, {'nome': 'Alice', 'eta': 25}]
  ```

  **Esempio equivalente senza lambda:**
  ```python
  def estrai_eta(studente):
      return studente["eta"]

  ordinati_per_eta = sorted(studenti, key=estrai_eta)
  print(ordinati_per_eta)
  # Output: [{'nome': 'Bob', 'eta': 20}, {'nome': 'Charlie', 'eta': 23}, {'nome': 'Alice', 'eta': 25}]
  ```

  In questo esempio, la lambda `lambda studente: studente["eta"]` estrae l'età di ciascun studente per ordinare la lista di dizionari. La versione senza lambda utilizza una funzione nominata `estrai_eta`.

---

- **Filtraggio con `filter()`:**
  La funzione `filter()` utilizza una funzione booleana per determinare quali elementi mantenere in una lista. Le lambda possono semplificare la scrittura di questa funzione booleana.

  **Esempio con lambda:**
  ```python
  numeri = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  
  numeri_pari = list(filter(lambda x: x % 2 == 0, numeri))
  print(numeri_pari)
  # Output: [2, 4, 6, 8, 10]
  ```

  **Esempio equivalente senza lambda:**
  ```python
  def è_pari(x):
      return x % 2 == 0

  numeri_pari = list(filter(è_pari, numeri))
  print(numeri_pari)
  # Output: [2, 4, 6, 8, 10]
  ```

  In questo esempio, la lambda `lambda x: x % 2 == 0` ritorna `True` per i numeri pari, mantenendoli nella lista filtrata. La versione senza lambda utilizza una funzione nominata `è_pari`.

---

- **Trasformazione con `map()`:**
  La funzione `map()` applica una funzione a ogni elemento di una lista. Le lambda possono essere usate per definire questa funzione inline.

  **Esempio con lambda:**
  ```python
  numeri = [1, 2, 3, 4, 5]
  
  doppi = list(map(lambda x: x * 2, numeri))
  print(doppi)
  # Output: [2, 4, 6, 8, 10]
  ```

  **Esempio equivalente senza lambda:**
  ```python
  def raddoppia(x):
      return x * 2

  doppi = list(map(raddoppia, numeri))
  print(doppi)
  # Output: [2, 4, 6, 8, 10]
  ```

  In questo esempio, la lambda `lambda x: x * 2` raddoppia ogni numero nella lista `numeri`. La versione senza lambda utilizza una funzione nominata `raddoppia`.

---

- **Riduzione con `functools.reduce()`:**
  La funzione `reduce()` applica una funzione binaria cumulativa a tutti gli elementi di una lista, riducendo la lista a un singolo valore. Le lambda possono essere utilizzate per definire la funzione binaria.

  **Esempio con lambda:**
  ```python
  from functools import reduce
  
  numeri = [1, 2, 3, 4, 5]
  
  somma_totale = reduce(lambda x, y: x + y, numeri)
  print(somma_totale)
  # Output: 15
  ```

  **Esempio equivalente senza lambda:**
  ```python
  def somma(x, y):
      return x + y

  somma_totale = reduce(somma, numeri)
  print(somma_totale)
  # Output: 15
  ```

  In questo esempio, la lambda `lambda x, y: x + y` somma cumulativamente tutti i numeri nella lista `numeri`, restituendo il totale. La versione senza lambda utilizza una funzione nominata `somma`.

---

- **Lambda come funzione di callback:**
  Le lambda possono essere utilizzate come funzioni di callback in vari contesti, come negli eventi di interfaccia grafica o nei metodi asincroni.

  **Esempio con lambda:**
  ```python
  def esegui(callback):
      risultato = callback(5)
      print(risultato)
  
  esegui(lambda x: x ** 2)
  # Output: 25
  ```

  **Esempio equivalente senza lambda:**
  ```python
  def esegui(callback):
      risultato = callback(5)
      print(risultato)

  def quadrato(x):
      return x ** 2

  esegui(quadrato)
  # Output: 25
  ```

  In questo esempio, una lambda che eleva `x` al quadrato viene passata come funzione di callback a `esegui`. La versione senza lambda utilizza una funzione nominata `quadrato`.

---

### Limiti delle funzioni lambda

- **Solo una singola espressione:** Le lambda non possono contenere più istruzioni o comandi complessi.
  ```python
  # Non consentito:
  # lambda x: if x > 0: return x else: return -x
  ```

- **Difficoltà di lettura:** Le lambda possono essere difficili da leggere e comprendere se usate in modo eccessivo o in contesti complessi.

In sintesi, le funzioni lambda in Python sono strumenti potenti per definire funzioni brevi e anonime utilizzabili in molti contesti funzionali, come l'ordinamento, il filtraggio e la trasformazione dei dati. Tuttavia, per funzioni più complesse, è meglio utilizzare funzioni nominate per una maggiore chiarezza e leggibilità del codice.
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



### Creazione di Moduli e Pacchetti

#### Scrivere e importare moduli personalizzati

Puoi creare i tuoi moduli per organizzare meglio il codice. Un modulo personalizzato è semplicemente un file Python (.py) che contiene definizioni di funzioni, variabili e classi.

- **Definizione di un modulo:**
  Crea un file `mio_modulo.py` con il seguente contenuto:
  ```python
  # Contenuto di mio_modulo.py
  def saluta():
      print("Ciao dal modulo!")
  ```

  **Uso di un modulo personalizzato:**
  Importa e usa il modulo nel tuo script principale:
  ```python
  import mio_modulo
  mio_modulo.saluta()
  # Output: Ciao dal modulo!
  ```

  In questo esempio, definiamo una funzione `saluta()` in `mio_modulo.py` e la importiamo per utilizzarla nel nostro script principale.

---
#### Uso della variabile `__name__`

La variabile `__name__` permette di controllare se il file viene eseguito direttamente o importato come modulo.

- **Esempio di utilizzo di `__name__`:**
  ```python
  # Contenuto di mio_modulo.py
  def saluta():
      print("Ciao dal modulo!")

  if __name__ == "__main__":
      saluta()
  ```

  **Uso di `__name__`:**
  ```python
  import mio_modulo
  # Nessun output perché il blocco if non viene eseguito quando importato
  ```

  Se eseguiamo `mio_modulo.py` direttamente, `__name__` sarà `"__main__"`, e la funzione `saluta()` verrà eseguita. Se importiamo il modulo, il blocco `if` non verrà eseguito.

---

#### Creare pacchetti Python

I pacchetti sono collezioni di moduli organizzati in una struttura di directory. Ogni directory contiene un file `__init__.py` che può essere vuoto o contenere codice di inizializzazione per il pacchetto.

- **Struttura di un pacchetto:**
  ```plaintext
  mio_pacchetto/
      __init__.py
      modulo1.py
      modulo2.py
  ```

  **Esempio di file `__init__.py`:**
  ```python
  # Contenuto di mio_pacchetto/__init__.py
  from .modulo1 import funzione1
  from .modulo2 import funzione2
  ```

  **Uso di un pacchetto:**
  ```python
  from mio_pacchetto import funzione1
  funzione1()
  ```

  In questo esempio, creiamo un pacchetto `mio_pacchetto` con due moduli `modulo1.py` e `modulo2.py`. Nel file `__init__.py`, importiamo le funzioni `funzione1` e `funzione2` dai rispettivi moduli, rendendole disponibili a chi importa il pacchetto.

- **File `__init__.py`:**
  Il file `__init__.py` rende una directory riconoscibile come pacchetto e può contenere codice per l'inizializzazione del pacchetto.

---

### Esempi pratici

**Modulo personalizzato:**

- `calcoli.py`
  ```python
  # Contenuto di calcoli.py
  def somma(a, b):
      return a + b

  def moltiplica(a, b):
      return a * b
  ```

- Uso del modulo:
  ```python
  import calcoli

  risultato_somma = calcoli.somma(2, 3)
  # Output: 5

  risultato_moltiplica = calcoli.moltiplica(2, 3)
  # Output: 6
  ```

**Pacchetto personalizzato:**

- Struttura:
  ```plaintext
  matematica/
      __init__.py
      aritmetica.py
      geometria.py
  ```

- `aritmetica.py`
  ```python
  # Contenuto di aritmetica.py
  def somma(a, b):
      return a + b

  def sottrai(a, b):
      return a - b
  ```

- `geometria.py`
  ```python
  # Contenuto di geometria.py
  def area_rettangolo(lunghezza, larghezza):
      return lunghezza * larghezza

  def perimetro_rettangolo(lunghezza, larghezza):
      return 2 * (lunghezza + larghezza)
  ```

- `__init__.py`
  ```python
  # Contenuto di __init__.py
  from .aritmetica import somma, sottrai
  from .geometria import area_rettangolo, perimetro_rettangolo
  ```

- Uso del pacchetto:
  ```python
  from matematica import somma, area_rettangolo

  risultato_somma = somma(5, 7)
  # Output: 12

  area = area_rettangolo(5, 3)
  # Output: 15
  ```

---

### Esecuzione Diretta di Moduli e File `__main__.py`

In Python, i moduli possono essere eseguiti direttamente come script oppure importati da altri moduli. La gestione di questo comportamento è fondamentale per creare script riutilizzabili ed eseguibili.

#### Esecuzione Diretta di Moduli

Quando un modulo viene eseguito direttamente, la variabile speciale `__name__` è impostata su `"__main__"`. Questo permette di scrivere codice che viene eseguito solo se il modulo è eseguito come script principale, e non quando è importato come modulo.

- **Esempio di controllo `__name__`:**
  ```python
  # Contenuto di esempio.py
  def funzione_principale():
      print("Funzione principale eseguita")

  if __name__ == "__main__":
      funzione_principale()
  ```

  **Esecuzione diretta:**
  ```sh
  python esempio.py
  # Output: Funzione principale eseguita
  ```

  **Importazione del modulo:**
  ```python
  import esempio
  # Nessun output perché il blocco if non viene eseguito
  ```

  In questo esempio, la funzione `funzione_principale()` viene eseguita solo quando `esempio.py` viene eseguito direttamente, non quando viene importato come modulo.

---

### File `__main__.py`

Il file `__main__.py` è un file speciale che viene eseguito quando un pacchetto viene eseguito come script. Questo è utile per creare pacchetti che possono essere eseguiti direttamente da linea di comando.

#### Struttura di un pacchetto con `__main__.py`

Supponiamo di avere una struttura di pacchetto come segue:
```plaintext
mio_pacchetto/
    __init__.py
    modulo1.py
    __main__.py
```

- **Contenuto di `__main__.py`:**
  ```python
  # Contenuto di mio_pacchetto/__main__.py
  from .modulo1 import saluta

  if __name__ == "__main__":
      print("Esecuzione diretta del pacchetto mio_pacchetto")
      saluta()
  ```

  **Contenuto di `modulo1.py`:**
  ```python
  # Contenuto di mio_pacchetto/modulo1.py
  def saluta():
      print("Ciao dal modulo1!")
  ```

- **Esecuzione del pacchetto:**
  ```sh
  python -m mio_pacchetto
  # Output:
  # Esecuzione diretta del pacchetto mio_pacchetto
  # Ciao dal modulo1!
  ```

  In questo esempio, `__main__.py` viene eseguito quando il pacchetto `mio_pacchetto` viene eseguito come script, utilizzando l'opzione `-m`.

---

### Differenze tra `__main__.py` e `__init__.py`

- **`__main__.py`:**
  - Scopo: Definisce il punto di ingresso per l'esecuzione di un pacchetto come script.
  - Esecuzione: Viene eseguito quando il pacchetto viene eseguito direttamente con `python -m nome_pacchetto`.
  - Utilizzo: Include codice che deve essere eseguito quando il pacchetto viene eseguito direttamente, non quando viene importato.

  **Esempio di utilizzo:**
  ```python
  # Contenuto di mio_pacchetto/__main__.py
  def main():
      print("Esecuzione come script")

  if __name__ == "__main__":
      main()
  ```

- **`__init__.py`:**
  - Scopo: Inizializza un pacchetto, rendendo la directory che lo contiene riconoscibile come pacchetto Python.
  - Esecuzione: Viene eseguito quando il pacchetto viene importato.
  - Utilizzo: Include importazioni e codice di inizializzazione per il pacchetto.

  **Esempio di utilizzo:**
  ```python
  # Contenuto di mio_pacchetto/__init__.py
  print("Inizializzazione del pacchetto mio_pacchetto")
  ```

  **Importazione del pacchetto:**
  ```python
  import mio_pacchetto
  # Output: Inizializzazione del pacchetto mio_pacchetto
  ```

In sintesi, `__main__.py` è utilizzato per eseguire un pacchetto come script, mentre `__init__.py` è utilizzato per inizializzare il pacchetto quando viene importato. Entrambi i file svolgono ruoli specifici e complementari nella gestione e nell'uso dei pacchetti Python.

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