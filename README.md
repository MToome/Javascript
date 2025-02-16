# Javascript

**Soovitav kasutada ', aga " sellel on väga väikesed vahed**
```Javascript
let nimi = 'Mati';
let vastus1= ' Tere tulemast koju "Madis"';
let vastus2 = " He is called 'John'";

let boo = 'hi';
// Kasutades kald juttumärke saab teha keerulisemaid asju
let template = ` Hello
 world
 ${vastus1}
 ${vastus2}
 !!!`;
```

**Loogika operaatorid**
```
&& and
|| or
! not
```

**Võrdlus operaatorid**
```
== võrdub
=== võrdne väärtus ja võrdne tüüpe
!= ei ole võrdne
!== ei ole võrdne väärtus või tüüp
```

**Nubrite paremaks arusaamiseks võib vahele panne _**
```Javascript
let x= 100_000_000_000;
```

**Muutujate puhul kasutada let mitte var(var on vana, let uus)**
``` Javascript
let y = 10
```
**Püsiva muutuja puhul const**
```Javascript
const x = 1
```

**Console võimaldab ligipääsu browseri debuggingule**
**Kõige tavalisemad käsklused:**

**Ekraanile printimiseks kasut console.log**
``` Javascript
console.log('Hello');
```

**Ekraanile errori teate näitamine**
```Javascript
console.error('See on errori teade');
```

**Ekraanile hoiatuse kuvamine**
```Javascript
console.warn('See on hoiatus');
```

**Kuvad info teada, võimalik kujundada selle välimust**
```Javascript
console.info(`%c see on muudetud kujundusega info kiri`, 'color:green; font-size: 15px; font-weight:bold:');
```

**Struktureeritud tabli formaadis andmete esitamiseks. Võtab sisestatud andmete omadused või elemendid ja paneb need ridadesse ja tulpadesse**
```Javascript
console.table([{nimi: 'Tom', vanus: 25, sugu: 'M'}, {nimi: 'Mari', vanus: 27, sugu: 'N'}]);
```

**Ajamõõtmiseks**
```Javascript
console.time('Ajamõõtmine');
function loops()
{
    for (let i = 0; i <= 10000; i++)
    {

    }
}
loops();
console.timeEnd('Ajamõõtmine');
```

**Annab ette viga teate kui teatud tingimus on vale, aitab leida vigu arendamise käigus. Kui tingimus on tõene siis ei tule ühtegi teadet**
```Javascript
console.assert(5>10, 'See väide ei õnnestunud');
```

**Console käskude grupeerimiseks console.group() alustamiseks ja groupEnd() gruppi lõpetamiseks**
```Javascript
console.group('Kasutaja info');
console.log('Nimi: Mati');
console.log('Sugu:M');
console.groupEnd();
```

**Loendamiseks mitu korda käsklust on kutsutud**
```Javascript
console.count('Loenda');
console.count('Loenda');
```
**Output**
```
Loenda: 1
Loenda: 2
```

**Koodi teekonna nägemiseks**
```Javascript
function a(){
    b();
}
function b(){
    c();
}
function c(){
    console.trace();
}
a();
```

**Array, võib sisestatud erinevat tüüpe väärtusid, lihtsamask vaatamiseks võib panna kõik väärtused eri reale, aga võib olla ka kõik ühes reas**
```Javascript
const list= [
    'Esimene', 
    2, 
    true, 
    () => 'hello', 
    {cat: 'Susi'}, 
    [1, 2, 'hello']
    ];

console.log(list);
console.log(list[0]);
console.log(list[4].cat);
console.log(list[5][1]);
```

## Objects
```Javascript
const inimene = {eesnimi: 'Tom', perekonnanimi:'Tiik', vanus:25};
```

## Muutuja tüübi saamiseks
```Javascript
typeof 'Lukk'  // string
typeof 0       // number
typeof 2.15    // number
```

## Loops
**while(true)**
```Javascript
let startSec = new Date().getSeconds();
let currentSec = new Date().getSeconds();
let count =0
while(currentSec == startSec){ // teeb niikaua kuni on tõene
    currentSec = new Date().getSeconds();
    console.log(count);
    count++;
}
```

**do while**
```Javascript
let a=1;

while(a<1){ // tingimust kontrollitakse alguses
    console.log('did stuff');
}

do {
    console.log('did stuff');
} while(a<1); // tingimust kontrollitakse lõpus, vähemalt ühe korra jookseb

let arra= ['Tom',1 , 'Hom'];

for(value in arra){
    console.log(arra[value]);
}

for(let i=0; i<10; i++){
    if(i==3){
        continue; // hüppab algusesse tagasi
    }
    if(i==7){
        break; // lõpetab loopi
    }
    console.log(i);
}
```
# Funktsioonid
## Klassikaline
```Javascript
function hello(name){
    return 'Hello ' + name;
}

let greeting = hello('Kevin');
console.log(greeting)
```

## Muutujas
```Javascript
let goodbye = function (name) {
    return 'goodbye ' + name;
}
```

## Ilma function märkimata
```Javascript
goodbye = (name) => {
    return 'goodbye ' + name;
}

let farewell = goodbye('Tim');
console.log(farewell);
```

## Ilma sulgudeta saab kui on ainult üks parameeter
```Javascript
goodbye = name => {
    return 'goodbye ' + name;
}

let farewell = goodbye('Tim');
console.log(farewell);
```

## Kui loogika lühike
```Javascript
goodbye = name => 'goodbye ' + name;

let farewell = goodbye('Tim');
console.log(farewell);
```

## Objektide vahel
```Javascript
let person ={
    name: 'Toomas',
    age: 25,
    greeting(){
        console.log(this); //this viitab objektile endale, this.name, this.age
        return 'hello '+ this.name; 
    },
    goodbye: () => {
        console.log(this) // viitab brauserile
        return 'goodbye';
    }
}

console.log(person.greeting())
console.log(person.goodbye())
```

## Rekursiivse funktsioonid
```Javascript
function recursive(i){
    console.log(i);
    if(i<10){
    recursive(i+1);
    }
}

recursive(0);

// alternatiiv
for (let i = 0; i < 10; i++) {
    console.log(i);
}
```

# Math matemaatilised tehted
```Javascript
Math.PI; // Annab PI
Math.sqrt(2); // Ruutjuur 2
Math.round(3.4); //3, ümardab lähima täisarvuni
Math.random(); // annab suvalise arvu 0 ja 1 vahel
Math.random() * 100; // 0 ja 100 vahel
(Math.random() * 100) + 100; // 100 ja 200 vahel
Math.ceil(4.2); // 5, ümardab ümardab ülesse lähima täis arvuni
Math.floor(4.9); // 4, ümardab alla lähima täis arvuni
Math.trunc(3.7); // 3, tagastab täisarvu
```

# If else
```Javascript
let day = new Date().getDay(); // pühapäev on 0 ja laupäev 6
console.log(day)

let answer = '';
if(day==0){
    answer = 'Pühapäev';
} else if(day==1){
    answer = 'ESmaspäev';    
} else if(day==2){
    answer = 'Teisipäev';  
} else if(day==3){
    answer = 'Kolmapäev';  
} else if(day==4){
    answer = 'Neljapäev';  
} else if(day==5){
    answer = 'Reede';  
} else if(day==6){
    answer = 'Laupäev';  
} else {
    answer = 'Imelik';
}
console.log(answer);

// Lihtsamalt saaks, switch case on tähtis break
switch(day){
    case 0:                     // Kas päev 0
        answer = 'Pühapäev';
        break;
    case 1:                     // Kas päev 0
        answer = 'Esmaspäev';
        break;
    case 2:                     // Kas päev 0
        answer = 'Teisipäev';
        break;
    case 3:                     // Kas päev 0
        answer = 'Kolmapäev';
        break;
    case 4:                     // Kas päev 0
        answer = 'Neljapäev';
        break;
    case 5:                     // Kui päev kas 5 või 6 päev on pidupäev
    case 6:
        answer = 'pidupäev';
        break;
    default:
        answer = 'Imelik';
}
```

# Interpolation

**Automaatselt muutujate asendamine nende väärtustega on string Interpolation**
Selleks vaja kasutada kald juttumärke `...` ja panna muutuja nimi ${...} sisse
```Javascript
let firstName = 'Tom';
let lastName = 'Tomson';

let helloString = `Welcome ${firstName}, ${lastName}!`;
```

