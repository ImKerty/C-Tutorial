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

**Ultimo aggiornamento:** 29 gennaio 2026