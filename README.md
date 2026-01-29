# C++ Tutorial Completo

Questa repository offre una guida essenziale alla sintassi e alle funzionalità del linguaggio C++, partendo dalle basi fino alla programmazione a oggetti.

## Indice
- [C++ Tutorial Completo](#c-tutorial-completo)
  - [Indice](#indice)
- [Basi del Linguaggio](#basi-del-linguaggio)
  - [Struttura Base (Hello World)](#struttura-base-hello-world)
  - [Variabili e Input/Output](#variabili-e-inputoutput)
- [Controllo del Flusso](#controllo-del-flusso)
  - [Condizioni (If/Else)](#condizioni-ifelse)
  - [Switch Case](#switch-case)
  - [Ciclo For](#ciclo-for)
  - [Ciclo While](#ciclo-while)
- [Funzioni](#funzioni)
  - [Dichiarazione Funzioni](#dichiarazione-funzioni)
  - [Passaggio per Riferimento (\&)](#passaggio-per-riferimento-)
- [Dati Strutturati](#dati-strutturati)
  - [Array (Vettori)](#array-vettori)
  - [Stringhe](#stringhe)
  - [Strutture (Struct)](#strutture-struct)
- [Programmazione a Oggetti (OOP)](#programmazione-a-oggetti-oop)
  - [Classi e Oggetti](#classi-e-oggetti)
  - [Costruttori](#costruttori)
- [Concetti Avanzati - Gestione Dati](#concetti-avanzati---gestione-dati)
  - [Validazione dell'Input](#validazione-dellinput)
    - [Perché validare?](#perché-validare)
  - [Gestione delle Stringhe Non Vuote](#gestione-delle-stringhe-non-vuote)
  - [Strutture Dati come Contenitori](#strutture-dati-come-contenitori)
    - [Il Concetto di Indicatore](#il-concetto-di-indicatore)
  - [Operazioni sulla Lista](#operazioni-sulla-lista)
    - [Aggiungere in Coda](#aggiungere-in-coda)
    - [Rimuovere in Posizione](#rimuovere-in-posizione)
  - [Filtraggio e Ricerca](#filtraggio-e-ricerca)
    - [Cercare Studenti Ammessi](#cercare-studenti-ammessi)
    - [Ricerca per Nome (String Matching)](#ricerca-per-nome-string-matching)
  - [Calcolo di Statistiche](#calcolo-di-statistiche)
    - [Trovare il Valore Massimo](#trovare-il-valore-massimo)
    - [Calcolare la Media](#calcolare-la-media)
  - [Confronto tra Collezioni](#confronto-tra-collezioni)
  - [Verifica dello Stato della Lista](#verifica-dello-stato-della-lista)
      
---

# Basi del Linguaggio

## Struttura Base (Hello World)

Ogni programma C++ deve avere una funzione `main`. È il punto di ingresso del programma.

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Ciao Mondo!" << endl;
    return 0;
}
```

## Variabili e Input/Output

Le variabili memorizzano dati. C++ è fortemente tipizzato.

```cpp
#include <iostream>
using namespace std;

int main() {
    int età = 25;
    string nome = "Marco";
    double altezza = 1.75;
    
    cout << "Nome: " << nome << endl;
    cout << "Età: " << età << endl;
    cout << "Altezza: " << altezza << endl;
    
    // Input da tastiera
    int numero;
    cout << "Inserisci un numero: ";
    cin >> numero;
    
    return 0;
}
```

---

# Controllo del Flusso

## Condizioni (If/Else)

Esegui codice in base a condizioni.

```cpp
#include <iostream>
using namespace std;

int main() {
    int voto = 7;
    
    if (voto >= 8) {
        cout << "Eccellente!" << endl;
    } else if (voto >= 6) {
        cout << "Buono!" << endl;
    } else {
        cout << "Insufficiente" << endl;
    }
    
    return 0;
}
```

## Switch Case

Scegli tra più opzioni.

```cpp
#include <iostream>
using namespace std;

int main() {
    int giorno = 2;
    
    switch(giorno) {
        case 1:
            cout << "Lunedì" << endl;
            break;
        case 2:
            cout << "Martedì" << endl;
            break;
        default:
            cout << "Giorno non valido" << endl;
    }
    
    return 0;
}
```

## Ciclo For

Ripeti codice un numero definito di volte.

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "Numero: " << i << endl;
    }
    
    return 0;
}
```

## Ciclo While

Ripeti finché una condizione è vera.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    
    while (i < 5) {
        cout << "Numero: " << i << endl;
        i++;
    }
    
    return 0;
}
```

---

# Funzioni

## Dichiarazione Funzioni

Le funzioni permettono di organizzare il codice.

```cpp
#include <iostream>
using namespace std;

int somma(int a, int b) {
    return a + b;
}

int main() {
    int risultato = somma(5, 3);
    cout << "Risultato: " << risultato << endl;
    
    return 0;
}
```

## Passaggio per Riferimento (&)

Modifica le variabili originali passate come parametri.

```cpp
#include <iostream>
using namespace std;

void incrementa(int &numero) {
    numero++;
}

int main() {
    int valore = 5;
    incrementa(valore);
    cout << "Valore: " << valore << endl; // Output: 6
    
    return 0;
}
```

---

# Dati Strutturati

## Array (Vettori)

Memorizza più elementi dello stesso tipo.

```cpp
#include <iostream>
using namespace std;

int main() {
    int numeri[5] = {10, 20, 30, 40, 50};
    
    for (int i = 0; i < 5; i++) {
        cout << "Elemento " << i << ": " << numeri[i] << endl;
    }
    
    return 0;
}
```

## Stringhe

Memorizza sequenze di caratteri.

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string messaggio = "Ciao C++";
    cout << "Messaggio: " << messaggio << endl;
    cout << "Lunghezza: " << messaggio.length() << endl;
    
    string saluto = "Buongiorno";
    saluto.append(" Marco");
    cout << saluto << endl;
    
    return 0;
}
```

## Strutture (Struct)

Raggruppa variabili di tipi diversi.

```cpp
#include <iostream>
using namespace std;

struct Persona {
    string nome;
    int età;
    double altezza;
};

int main() {
    Persona p1;
    p1.nome = "Marco";
    p1.età = 25;
    p1.altezza = 1.75;
    
    cout << "Nome: " << p1.nome << endl;
    cout << "Età: " << p1.età << endl;
    
    return 0;
}
```

---

# Programmazione a Oggetti (OOP)

## Classi e Oggetti

Una classe è un modello per creare oggetti.

```cpp
#include <iostream>
using namespace std;

class Auto {
public:
    string marca;
    string modello;
    int anno;
    
    void mostraInfo() {
        cout << marca << " " << modello << " (" << anno << ")" << endl;
    }
};

int main() {
    Auto auto1;
    auto1.marca = "Ferrari";
    auto1.modello = "F8";
    auto1.anno = 2023;
    
    auto1.mostraInfo();
    
    return 0;
}
```

## Costruttori

Inizializzano gli oggetti automaticamente.

```cpp
#include <iostream>
using namespace std;

class Conto {
private:
    double saldo;
    
public:
    Conto(double iniziale) {
        saldo = iniziale;
    }
    
    void deposita(double importo) {
        saldo += importo;
    }
    
    double leggiSaldo() {
        return saldo;
    }
};

int main() {
    Conto conto1(1000);
    conto1.deposita(500);
    cout << "Saldo: " << conto1.leggiSaldo() << endl;
    
    return 0;
}
```

---

# Concetti Avanzati - Gestione Dati

## Validazione dell'Input

### Perché validare?

La validazione è fondamentale per evitare errori e comportamenti inaspettati. Quando un utente inserisce dati, potrebbe sbagliare: per questo controlliamo che il valore rientri in un intervallo accettabile.

```cpp
void leggiIntero(int &valore, string messaggio, int min, int max) {
    cout << messaggio;
    cin >> valore;
    while(valore < min || valore > max) {  // Controlla se è fuori range
        cout << "*** Errore. Inserire un numero compreso fra " << min << " e " << max << endl;
        cout << messaggio;
        cin >> valore;
    }
}
```

**Ragionamento:**
- Il ciclo `while` rimane attivo finché il valore è errato
- Dopo ogni tentativo fallito, richiediamo l'input
- Questo garantisce che procediamo solo con dati validi

## Gestione delle Stringhe Non Vuote

Simile alla validazione numerica, ma per le stringhe:

```cpp
void leggiStringa(string &valore, string messaggio) {
    cout << messaggio;
    getline(cin, valore);  // Legge l'intera riga (inclusi spazi)
    while(valore.size() == 0) {  // Controlla se è vuota
        cout << "*** Errore. Inserire una stringa non vuota" << endl;
        cout << messaggio;
        getline(cin, valore);
    }
}
```

**Perché `getline()` invece di `cin >>`?**
- `cin >>` si ferma al primo spazio
- `getline()` legge l'intera riga
- Perfetto per nomi e cognomi con spazi

## Strutture Dati come Contenitori

### Il Concetto di Indicatore

```cpp
struct lista {
    int indicatore;           // Tiene traccia di quanti elementi abbiamo
    studente studenti[MAX_DIM];  // Array di studenti
};
```

**Ragionamento:**
- L'array ha una dimensione fissa (MAX_DIM = 100)
- L'`indicatore` ci dice quanti elementi sono **effettivamente** usati
- Se abbiamo 3 studenti, indicatore = 3, anche se l'array può contenerne 100

**Vantaggi:**
- Risparmiamo memoria (non usiamo spazi inutili)
- Sappiamo dove finiscono i dati validi
- Possiamo controllare se è piena o vuota

## Operazioni sulla Lista

### Aggiungere in Coda

```cpp
void aggiungiInCoda(lista &studenti, studente studente) {
    studenti.studenti[studenti.indicatore] = studente;  // Metti in posizione libera
    studenti.indicatore++;  // Incrementa il contatore
}
```

**Ragionamento:**
- Inseriamo nella posizione indicata da `indicatore`
- Poi lo incrementiamo per la prossima inserzione
- È efficiente: O(1), tempo costante

### Rimuovere in Posizione

```cpp
void rimuoviInPosizione(lista &studenti, int pos) {
    for (int i = pos; i < studenti.indicatore - 1; i++) {
        studenti.studenti[i] = studenti.studenti[i+1];  // Sposta elementi
    }
    studenti.indicatore--;  // Diminuisci il contatore
}
```

**Ragionamento:**
- Quando rimuoviamo, creiamo un buco
- Spostiamo tutti gli elementi successivi una posizione indietro
- Infine, decrementiamo l'indicatore

**Esempio:**
```
Prima:  [A, B, C, D] indicatore=4
Tolgo C (pos=2):
        [A, B, D, D] (sposta D)
        [A, B, D]    (decrementa indicatore=3)
```

## Filtraggio e Ricerca

### Cercare Studenti Ammessi

```cpp
lista cercaStudentiAmmessi(lista studenti) {
    lista ammessi;
    ammessi.indicatore = 0;
    for (int i = 0; i < studenti.indicatore; i++) {
        studente studente = studenti.studenti[i];
        if (studente.voto >= VOTO_AMMESSO) {  // Condizione di filtro
            aggiungiInCoda(ammessi, studente);  // Aggiungi se soddisfa
        }
    }
    return ammessi;
}
```

**Ragionamento:**
- Creiamo una **nuova lista vuota** per i risultati
- Iteriamo su tutti gli elementi
- Se soddisfano la condizione, li aggiungiamo alla nuova lista
- Restituiamo una lista filtrata

**Vantaggi:**
- La lista originale non viene modificata
- Possiamo riusare questa funzione per altri filtri
- È un modello di programmazione riutilizzabile

### Ricerca per Nome (String Matching)

```cpp
lista ricercaPerNome(lista studenti, string nome) {
    lista ricerca;
    ricerca.indicatore = 0;
    for(int i = 0; i < studenti.indicatore; i++) {
        if (studenti.studenti[i].nome.find(nome) != -1) {  // Cerca substring
            aggiungiInCoda(ricerca, studenti.studenti[i]);
        }
    }
    return ricerca;
}
```

**Cosa significa `find()`?**
- Cerca una sottostringa all'interno di una stringa
- Restituisce la posizione se trovata
- Restituisce `-1` (in realtà `string::npos`) se non trovata

**Esempio:**
```
nome cercato: "Mar"
studente.nome: "Marco Rossi"
"Marco Rossi".find("Mar") → 0 (trovato all'inizio)
"Marco Rossi".find("xyz") → -1 (non trovato)
```

## Calcolo di Statistiche

### Trovare il Valore Massimo

```cpp
int trovaVotoMax(lista studenti) {
    int votoMax = studenti.studenti[0].voto;  // Inizia dal primo
    for (int i = 1; i < studenti.indicatore; i++) {
        if (studenti.studenti[i].voto > votoMax) {  // Confronta
            votoMax = studenti.studenti[i].voto;     // Aggiorna
        }
    }
    return votoMax;
}
```

**Ragionamento:**
- Partiamo dal primo elemento come "massimo provvisorio"
- Iteriamo dal secondo elemento
- Se ne troviamo uno più grande, lo aggiorniamo
- Questo è più efficiente che cercare ogni volta

### Calcolare la Media

```cpp
float calcolaMedia(lista stud) {
    float sommaVoti = 0;
    for(int i = 0; i < stud.indicatore; i++) {
        sommaVoti += stud.studenti[i].voto;  // Accumula
    }
    return sommaVoti / stud.indicatore;  // Dividi per la quantità
}
```

**Ragionamento:**
- Accumuliamo tutti i voti in una variabile
- Dividiamo per il numero di elementi
- Usiamo `float` per preservare i decimali

## Confronto tra Collezioni

Il programma confronta due coorti usando la stessa logica:

```cpp
// Confronta voti massimi
int maxStudenti = trovaVotoMax(studenti);
int maxNuovaCoorte = trovaVotoMax(nuovaCoorte);

if (maxStudenti > maxNuovaCoorte) {
    // Prima coorte vince
} else if (maxStudenti < maxNuovaCoorte) {
    // Seconda coorte vince
} else {
    // Pareggio
}
```

**Perché riusare le funzioni?**
- Meno codice duplicato
- Meno errori
- Più facile da mantenere

## Verifica dello Stato della Lista

```cpp
bool listaPiena(lista studenti) {
    return studenti.indicatore == MAX_DIM;
}

bool listaVuota(lista studenti) {
    return studenti.indicatore == 0;
}
```

**Ragionamento:**
- Prima di operazioni critiche, verifichiamo lo stato
- Se la lista è piena, non possiamo aggiungere
- Se è vuota, non possiamo cercare

Queste funzioni rendono il codice **leggibile** e **sicuro**.

---

**Ultimo aggiornamento:** 29 gennaio 2026