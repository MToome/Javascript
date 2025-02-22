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

**Kasutades '_' omaduse nime alguses annab märku teistele arendajatele märku, et ei muudaks seda omadust ei muudaks**

**Loogika operaatorid**
```
&& and
|| or
! not
```

**'!' boolean väärtuse muutmine**
```Javascript
let late = true;
let oposite = !late;

console.log(oposite) // Output: false
```

**Võrdlus operaatorid**
```
== võrdub
=== võrdne väärtus ja võrdne tüüpe
!= ei ole võrdne
!== ei ole võrdne väärtus või tüüp
```

```Javascript
console.log(1 != '1'); // Output: false
console.log(1 !== '1'); // Output: true
```

**Ternary Operator**
'===' lubab kui olukorda peale '?' märki kui see sünteks on kompaktne
```Javascript
let price = 10.5;
let day = "Monday";

day === "Monday" ? price -= 1.5 : price += 1.5; // kui päev on monday siis rakendub esimene väljend, kui ei ole siis teine
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

## Interpolation

**Automaatselt muutujate asendamine nende väärtustega on string Interpolation**
Selleks vaja kasutada kald juttumärke `...` ja panna muutuja nimi ${...} sisse
```Javascript
let firstName = 'Tom';
let lastName = 'Tomson';

let helloString = `Welcome ${firstName}, ${lastName}!`;
```

**Array, võib sisestatud erinevat tüüpe väärtusid, lihtsamask vaatamiseks võib panna kõik väärtused eri reale, aga võib olla ka kõik ühes reas,** 
**on võimalik hiljem muuta(mutable)**
```Javascript
const listOne= [
    'Esimene', 
    2, 
    true, 
    () => 'hello', 
    {cat: 'Susi'}, 
    [1, 2, 'hello']
    ];

console.log(listOne);
console.log(listOne[0]);
console.log(listOne[4].cat);
console.log(listOne[5][1]);

listOne.push('T', 5); // .push saab array lõppu panna ühe või mitu elementi
listOne.pop(); // .pop võtab array lõpust elemendi ja tagastab selle
console.log(listOne.length); // Output: 7, tagastab array elementide arvu, loendamine algab nullist
```

**.reduce() käib listi läbi ja tagastab ühe väärtuse**
```Javascript
const arrayOfNumbers = [1, 2, 3, 4];

const sum = arrayOfNumbers.reduce((accumulator, currentValue) => {  // accumulator on eelmise iteratsiooni väärtus ja currentValue praegune mis juurde pannakse
  return accumulator + currentValue;
});
console.log(sum); // Output: 10, 1+2+3+4
```

**.forEach() iga listi elemendi kohta teeb midagi**
```Javascript
const listTwo = [34, 'Tom', 5, 'Mari'];

listTwo.forEach(item => {
    console.log(item);      // Kõik elemendid listis kuvatakse ükshaaval
})
```

**.filter() filtreerib listi vastavalt ette antud tingimusele ja koostab uue listi elementidest mis tingimuses olid true**
```Javascript
const numbers = [1, 2, 42 , 43, 64];
const filteredNumbers = numbers.filter(i => {
    return i % 2 == 0                           // 2, 42, 64
})
```

**.map() kutsub iga elementi tagasi listis**
```JavaScript
const listTree = ['Mark', 'Tiina', 'Matias'];

const hiListTree = listTree.map(name => {
    return 'hi ' + name;    // lisab iga nime juurde hi ja teeb sellest uue nimekirja
})
```

## Objects
```Javascript
const inimene = {eesnimi: 'Tom', perekonnanimi:'Tiik', vanus:25};
```

### Shorthand property name syntax for object creation
```JavaScript
const activity = 'Running';
const forest = { activity };
console.log(forest); // { activity: 'Running' }
```

### Destructuring assignment shorthand syntex
**Lubab objekti omadusi täpseteks muutuja väärtusteks**
```Javascript
const rubiksCubeFacts = {
  possiblePermutations: '43,252,003,274,489,856,000',
  invented: '1974',
  largestCube: '17x17x17'
};
const {possiblePermutations, invented, largestCube} = rubiksCubeFacts;
console.log(possiblePermutations); // '43,252,003,274,489,856,000'
console.log(invented); // '1974'
console.log(largestCube); // '17x17x17'
```

### Getters and setters
**Võimaldavad lisa tegevusi teha muutujatega**
**Võimalik tagastama teistsugust väärtust kasutades tingimusi**
**Saab kasutada *.this* ,et objekti siseseid omadusi kutsuda**
**Getters võtavad ja tagastavad objekti sisesed omadused, aga on võimelised enamaks**
```JavaScript
const person = {
  _firstName: 'John',
  _lastName: 'Doe',
  get fullName() {
    if (this._firstName && this._lastName){
      return `${this._firstName} ${this._lastName}`;
    } else {
      return 'Missing a first name or a last name.';
    }
  }
}

// To call the getter method: 
person.fullName; // 'John Doe'
```

**Setters taas määravad omadused objektis**
```JavaScript
const person = {
  _age: 37,
  set age(newAge){
    if (typeof newAge === 'number'){
      this._age = newAge;
    } else {
      console.log('You must assign a number to age');
    }
  }
};
person.age = 40;
console.log(person._age); // Logs: 40
person.age = '40'; // Logs: You must assign a number to age

// Vanust saab otse ikkagi määrata
person._age = 'forty-five'
console.log(person._age); // Prints forty-five
```

### Built-in object Methods
**Järgnevalt lingilt on võimalik nende kohta rohkem õppida**
[MDN's object instance documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#Methods)
**On olemas mitmeid sisse ehitatud objektide meetodeid**
```JavaScript
const robot = {
	model: 'SAL-1000',
  mobile: true,
  sentient: false,
  armor: 'Steel-plated',
  energyLevel: 75
};

const robotKeys = Object.keys(robot);
console.log(robotKeys); 
// output: [ 'model', 'mobile', 'sentient', 'armor', 'energyLevel' ]

const robotEntries = Object.entries(robot);
console.log(robotEntries); 
/* output:
[ [ 'model', 'SAL-1000' ],
  [ 'mobile', true ],
  [ 'sentient', false ],
  [ 'armor', 'Steel-plated' ],
  [ 'energyLevel', 75 ] ]
*/

// Declare newRobot below this line:
const newRobot = Object.assign({}, robot, {laserBlaster: true, voiceRecognition: true}) // {} see näitab, et ei muudeta mingit objekti
console.log(newRobot);

/* output:
{ model: 'SAL-1000',
  mobile: true,
  sentient: false,
  armor: 'Steel-plated',
  energyLevel: 75,
  laserBlaster: true,
  voiceRecognition: true }
*/
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

**Nested for loops**
```Javascript
for (let outer = 0; outer < 2; outer += 1) {   // loeb ühe korra selle
  for (let inner = 0; inner < 3; inner += 1) { // siis teeb selle täielikult ära, teeb jälle ühe korra ülemise ja tule siia tagasi
    console.log(`${outer}-${inner}`);
  }
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
## Funktsioonid
**Javascriptis on funktsioonid objektid ja seetõttu saab neid argumentidena sisestada**
**Javascripti enda funktsioonid on esmaklaasilised objektid, neil on sisseehitatud omadused ja meetodid, omadusi ja meetodeid saab neile lisada,**
**neid saab lisada argumentidena ja tagastada teistest funktsioonidest, neid saab määrata muutujatesse, listi elementidesse ja teistesse objektidesse** 

### Klassikaline
```Javascript
function hello(name){
    return 'Hello ' + name;
}

let greeting = hello('Kevin');
console.log(greeting)
```

### Anonüümne funktsioon
```Javascript
// Nimega funktsioon
function hello() {
  return 'Hi';
}

// Anonüümne funktsioon
const hello = function() {
  return 'hi';
}
```

### Muutujas
Võivad olla anonüümsed
```Javascript
let goodbye = function (name) {
    return 'goodbye ' + name;
}
```

### Ilma function märkimata, arrow function =>
```Javascript
goodbye = (name) => {
    return 'goodbye ' + name;
}

let farewell = goodbye('Tim');
console.log(farewell);
```

### Tehasefunktsioon on funktsioon, mis tagastab objekti ja mida saab uuesti kasutada mitme objekti eksemplari loomiseks.
```JavaScript
const monsterFactory = (name, age, energySource, catchPhrase) => {
  return { 
    name: name,
    age: age, 
    energySource: energySource,
    scare() {
      console.log(catchPhrase);
    } 
  }
};
```

### Destructuring techinque - property value shorthand
**Sama nimega võti ja väärtus ilma seda välja trükkimata**
Ülemine näide lihtsamalt.
```JavaScript
const monsterFactory = (name, age, energySource, catchPhrase) => {
  return { 
    name,
    age, 
    energySource,
    scare() {
      console.log(catchPhrase);
    } 
  }
};
```

### Destructured assignment
**Loome muutuja objekti võtmega mis on looklevate sulgude vahel {} ja määrama sellele objekti**
```Javascript
const residence = vampire.residence; 
console.log(residence); // Prints 'Transylvania' 

// Destructured assignment
const { residence } = vampire; 
console.log(residence); // Prints 'Transylvania'
```


### Ilma sulgudeta saab kui on ainult üks parameeter
```Javascript
goodbye = name => {
    return 'goodbye ' + name;
}

let farewell = goodbye('Tim');
console.log(farewell);
```

### Kui loogika lühike
```Javascript
goodbye = name => 'goodbye ' + name;

let farewell = goodbye('Tim');
console.log(farewell);
```

### Objektide vahel
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

### Rekursiivse funktsioonid
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

## Math matemaatilised tehted
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

## If else
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
    case 5:                     // Kui päev kas 5 või 6 on pidupäev
    case 6:
        answer = 'pidupäev';
        break;
    default:
        answer = 'Imelik';
}
```

# Lisad
## Javascript compiler
[Babel](babeljs.io)

## Nunjucks
Javascripti šabloonimis keel

## TypeScript 
typescript on javascript tüüpide sünteksiga
[TypeScript](typescriptlang.org)

## Haxe 4 
Tõlgib erinevatese keeltesse
[Haxe](haxe.org)

## Webassembly
Saab tõlgendada programeerimis keel veebi tarbeks
[Webassambly](webassamnly.org)

## Css 
Sass(algaja sõbralik)
Sass on paljude võimalustega ja lihtsam kirjutamis keel kui css, saab tõlkida ümber css`i
[Sass](sass-lang.com)