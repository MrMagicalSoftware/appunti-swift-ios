# appunti-swift-ios


> Come creare un README.md https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

> Per cambiare il tema di lavoro
> Light vs Dark si può utilizzare

Code > Preferencies > Apparence > Light | Dark
Dal menu Fonts & colors posso scegliermi il theme

> Risorse :

Color Hunt www.colorhunt.co
PaintCodeApp www.paintcodeapp.com
App Icon Generaton https://appicon.co/
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

Per fare riferimento alle immagini scrivere imageLiteral nel
codice solo per le versioni di xcode 11


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



# Parametri di ingresso e uscita opzionali

```
var mioArray: [Int]?

func contaElementi(array: [Int]?) {
    if array == nil {
        print("il vettore è nullo per favore inizializzalo")
        return
    }
    print("l'array contiene \(array!.count) elementi")
}

contaElementi(array: mioArray)



var vettoreInteri: [Int]?

func contaElementi(array: [Int]?) -> Int? {
    if array == nil {
        return nil
    }
    return array!.count
}


if let numElementi = contaElementi(array: vettoreInteri) {
    print("l'array contiene \(numElementi)")
} else {
    print("per favore inizializza l'array")
}


```

# Parametro Inout

La modifica di un parametro di una funzione, fino ad ora, è impossibile. I parametri, di default, vengono considerati come costanti (let). Cioè, nel caso in cui ti servisse modificare, dall’interno della funzione, la variabile passata al parametro verrebbe a crearsi un problema:

```
var a = 2

func modifica(variabile: Int) {
   variabile = 4 // Errore!!! Il parametro è considerato come let

}

```


Per poter risolvere questo problema, il linguaggio Swift ti mette a disposizione la parola chiave inout che permette di modificare direttamente la variabile passata come parametro.

Il parametro inout va inserito prima della definizione del tipo di dato del parametro:

func nomeFunc(parametro: inout Tipo) {} // Pseudo codice

Per capire meglio l’utilità del parametro inout, proviamo a creare una funzione che scambi i valori di due variabili:
```
var primo = 2

var secondo = 7

func scambiaValori(a: inout Int, b: inout Int) {

    let c = a
    a = b
    b = c
}
```

Quando passi una variabile ad un parametro inout devi inserire il prefisso & seguito dal nome della var/let, il perché dell’inserimento di questo prefisso è un po’ complicato e molto grossolanamente serve ad avvisare la funzione che stai passando un riferimento ad una variabile presente nel progetto.

```

print("\(primo) e \(secondo) ")

scambiaValori(a: &primo, b: &secondo)

print("\(primo) e \(secondo) ")

```


# How to Make Timer in Swift 
```


var timer = Timer()

timer = Timer.scheduledTimer(timeInterval : 1.0 , target : self , selector : #selector(updateTimer), userInfo : nil , repeats : true)

@objc funct updateTimer(){
    
    if(condition){
        timer.invalidate()
    }

}
```


# How to move an object 




```

@IBAction func tapButton() {
    UIView.animateWithDuration(0.75, delay: 0, options: .CurveLinear, animations: {
        // this will change Y position of your imageView center
        // by 1 every time you press button
        self.puppy.center.y -= 1  
    }, completion: nil)
}

```


# How to make a Sound 

```
var player : AVAudioPlayer!

guard let url = Bundle.main.url(forResource: "mp3/" + nameOfSound, withExtension: "mp3") else {
    print("RETURNING ")
    return
}
                
do {
    try AVAudioSession.sharedInstance().setCategory(.playback, mode: .default)
    try AVAudioSession.sharedInstance().setActive(true)
            
    /* The following line is required for the player to work on iOS 11. Change the file type accordingly*/
    player = try AVAudioPlayer(contentsOf: url, fileTypeHint: AVFileType.mp3.rawValue)
            
    /* iOS 10 and earlier require the following line:
    player = try AVAudioPlayer(contentsOf: url, fileTypeHint: AVFileTypeMPEGLayer3) */
          
    guard let player = player else { return }        
    player.play()
            
} catch let error {
    print("Error was detected")
    print(error.localizedDescription)
}

```


# How to install Cocoapods

> sudo gem install cocoapods


Once we complete setting up are cocoapods we should be ready to add a third party library to our project, 
you can use cocoapods.org to browse the available libraries, for this example we’ll be using NavigationDrawer,
so let’s go ahead and open it the page


Once there you should do a “pod init” in your terminal

It will then output a file named Podfile.


Step 2:

Once we have selected our pods we should now create/open the project that we want to integrate the pod to. Once our project is ready just open a terminal and navigate to the project folder





# Data Fetcher

See this https://www.json4swift.com/




