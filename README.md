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
console.log("Hello")
```

Ekraanile errori teate näitamine
```Javascript
console.error("See on errori teade")
```

Ekraanile hoiatuse kuvamine
```Javascript
console.warn("See on hoiatus");
```

Kuvad info teada, võimalik kujundada selle välimust
```Javascript
console.info("%c see on muudetud kujundusega info kiri", "color:green; font-size: 15px; font-weight:bold:")
```

Struktureeritud tabli formaadis andmete esitamiseks. Võtab sisestatud andmete omadused või elemendid ja paneb need ridadesse ja tulpadesse.
```Javascript
console.table([{nimi: "Tom", vanus: 25, sugu: "M"}, {nimi: "Mari", vanus: 27, sugu: "N"}])
```