# appunti-swift-ios


> Come creare un README.md https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

> Per cambiare il tema di lavoro
> Light vs Dark si può utilizzare

Code > Preferencies > Apparence > Light | Dark
Dal menu Fonts & colors posso scegliermi il theme

> Risorse :

Color Hunt www.colorhunt.co
PaintCodeApp www.paintcodeapp.com
App Icon Generator www.appicon.co
spostarsi nella sezione di ImageSet


# Clone an Existing project

> Dal menu Source Control
> Oppure dal menu iniziale di Xcode
> Clone an Existing project

Clonare i seguenti progetti :

https://github.com/dkhamsing/open-source-ios-apps#calculator
https://github.com/fullstackio/FlappySwift

Esercizio Clonare i progetti e provarli sul Simulatore

> Gestione delle Immagini

1. Aspect Fit
2. Scale to Fill
3. Aspect Fill

Per copiare un elemento UI , posso utilizzare
Il tasto alt


# Collegare immagine a codice :

> Splittare la view : tra codice sorgente e UI
> Tasto control drag and drop sul codice
> Eseguire le varie procedure

Importante se devo rinominare il nome
@IBOutlet var diceImageView1: UIImageView!

tasto destro Refactor altrimenti produco un crash
perchè non trova più la reference


# Convenzioni tra programmatori

CamelCase
Kebab-case
snake_case



Come si genera un numero pseudoCasuale
Kjanacademy.org/computing/

> random vs psudorandom-number-generators


Int.random(in : 1 ... 3 ) //numeri compresi tra 1 e 3
Int.random(in : low ..< upper ) non include upperBound

Float.random()
Bool.random()
array.randomElement()
array.shuffle()


Esercizio
Creare un password generator


# Auto-layout and Responsive UI

Si attivano le constrains nella schermata
view dove sono presenti View as : Iphone ... - 50 % +

-[]- attivare con il rosso le constrains

Per allineare gli elementi usare il tasto
vicino al constrains

Per creare delle zone di lavoro
dei contenitori di tipo view --->
posso

1. cercare uiview e poi fare drag and drop
2. Oppure selezionare gli elementi Editor - embed in View
3. oppure selezionare l'object tasto vicino a constrains (menu basso)

a loro volta le view possono essere inserte in una struttura
di tipo stack view ...
Posso raggrupparle ricorsivamente


# Come si programma ?

> Cerca su google
> stack overflow
> implementa
> Documentazione
> adatta al tuo codice

Es play sound swift

> guardare nella documentazione apple

developer.apple.com/documentation/

Nota : per aprire la documentazione
rapida del codice spostarsi sul nome
dell funzione e premere options
(tasto vicino al cmd)



# Funzioni che ritornano piu' parametri.

```
func calcoloMinMax(array: [Int]) -> (min: Int, max: Int)
{

    //setto minimo e massimo uguali al primo valore dell'array
    var minimo = array[0] 
    var massimo = array[0]
    
    for valore in array {
        if valore < minimo {
            minimo = valore
        } else if valore > massimo {
            massimo = valore
        }
    }
    
    return (minimo, massimo)
}


var array = [123, 0, 22, -1, 155, 43]
let minMax = calcoloMinMax(array: array) // restituisce la tupla (min,max) che conservo in una costante qualsiasi
// ti ricordo che il tipo di dato viene acquistato all'inizializzazione. minMax ora rappresenta una tupla di tipo (min,max)
print("il minimo è \(minMax.min) e il massimo è \(minMax.max)") //accedo ai valori della tupla
//con .min e .max

```



#Parametri di ingresso e uscita opzionali







