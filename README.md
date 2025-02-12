# Javascript

Muutujate puhul kasutada let mitte var(var on vana, let uus)
``` Javascript
let y = 10
```
Püsiva muutuja puhul const

```Javascript
const x = 1
```

Console võimaldab ligipääsu browseri debuggingule 
Kõige tavalisemad käsklused:

Ekraanile printimiseks kasut console.log
``` Javascript
console.log("Hello");
```

Ekraanile errori teate näitamine
```Javascript
console.error("See on errori teade");
```

Ekraanile hoiatuse kuvamine
```Javascript
console.warn("See on hoiatus");
```

Kuvad info teada, võimalik kujundada selle välimust
```Javascript
console.info("%c see on muudetud kujundusega info kiri", "color:green; font-size: 15px; font-weight:bold:");
```

Struktureeritud tabli formaadis andmete esitamiseks. Võtab sisestatud andmete omadused või elemendid ja paneb need ridadesse ja tulpadesse.
```Javascript
console.table([{nimi: "Tom", vanus: 25, sugu: "M"}, {nimi: "Mari", vanus: 27, sugu: "N"}]);
```

Ajamõõtmiseks
```Javascript
console.time("Ajamõõtmine");
function loops()
{
    for (let i = 0; 1 <= 10000; i++)
    {

    }
}
loops();
console.timeEnd("Ajamõõtmine");
```

Annab ette viga teate kui teatud tingimus on vale, aitab leida vigu arendamise käigus. Kui tingimus on tõene siis ei tule ühtegi teadet.
```Javascript
console.assert(5>10, "See väide ei õnnestunud");
```

Console käskude grupeerimiseks console.group() alustamiseks ja groupEnd() gruppi lõpetamiseks.
```Javascript
console.group("Kasutaja info");
console.log("Nimi: Mati");
console.log("Sugu:M");
console.groupEnd();
```

Loendamiseks mitu korda käsklust on kutsutud
```Javascript
console.count("Loenda");
console.count("Loenda");
```
**Output**
```
Loenda: 1
Loenda: 2
```

Koodi teekonna nägemiseks
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

**Array**
```Javascript
const listing = ["Esimene", "Teine", "Kolmas"];
```

**Objects**
```Javascript
const inimene = {eesnimi: "Tom", perekonnanimi:"Tiik", vanus:25};
```

**Muutuja tüübi saamiseks**
```Javascript
typeof "Lukk"  // string
typeof 0       // number
typeof 2.15    // number
```

**Funktsioonid**
**Klassikaline**
```Javascript
function hello(name){
    return "Hello" + name;
}

let greeting = hello("Kevin");
console.log(greeting)
```

**Muutujas**
```Javascript
let goodbye = function (name) {
    return "goodbye" + name;
}
```

**ilma function märkimata**
```Javascript
goodbye = (name) => {
    return "goodbye" + name;
}

let farewell = goodbye("Tim");
console.log(farewell);
```

**ilma sulgudeta saab kui on ainult üks parameeter**
```Javascript
goodbye = name => {
    return "goodbye" + name;
}

let farewell = goodbye("Tim");
console.log(farewell);
```

**kui loogika lühike**
```Javascript
goodbye = name => return "goodbye" + name;

let farewell = goodbye("Tim");
console.log(farewell);
```
