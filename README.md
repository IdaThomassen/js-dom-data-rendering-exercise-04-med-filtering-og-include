Det er opgave 4!! ikke 3...
# 🎬 JavaScript DOM Data Rendering #4 med filtering og include
## Forbedring af DOM-rendering med `map()` og `join("")`  
### CineMaxx Movies – Improved Version

## Opgavebeskrivelse

Du skal bygge en lille movie-side, hvor filmdata fra JavaScript bliver vist i DOM’en.

Denne gang skal du ikke kun vise data i DOM’en.  
Du skal også **forbedre måden, HTML’en bliver opbygget på i JavaScript**.

I tidligere opgaver har du arbejdet med:

- JavaScript-datastruktur (**array med objekter**)
- DOM-manipulation
- funktioner med parametre
- forEach()
- querySelector()
- innerHTML
- template literals

I denne opgave skal du arbejde videre med de samme elementer, men nu skal du forbedre løsningen ved at bruge:

- `map()`
- `join("")`

Formålet med opgaven er at træne, om du kan:

- opbygge en JavaScript-datastruktur
- bruge en funktion med parameter
- hente et HTML-element med `querySelector()`
- oprette HTML med template literals
- bruge `map()` til at omdanne data til HTML-strenge
- samle HTML-strengene med `join("")`
- indsætte det færdige resultat i DOM’en med `innerHTML`

---

## Forudsætninger

Du må redigere i:

- `js/movies-script.js`
- `css/style.css`

---

## Trin-for-trin

1. Download projektkoden (ZIP-fil) fra GitHub, og udpak den på din computer.

2. Opret et nyt repository på GitHub.com med et passende navn, fx:

`dom-data-rendering-map-join-movies-exercise`

3. Kopiér linket til dit GitHub-repository.

4. Åbn GitHub Desktop og vælg **Clone repository**.

5. Vælg fanen **URL**, indsæt linket, og vælg en passende placering under **Local Path**.

6. Kopiér indholdet fra den udpakkede projektmappe over i den klonede mappe.

7. Åbn projektmappen i Visual Studio Code.

8. Løs nu opgaverne herunder.

---

## Projektmappe

Du får udleveret en projektmappe, som indeholder:

- en `index.html` fil
- en `css`-mappe
- en `js`-mappe
- en `img`-mappe med billeder
- en `movies.txt` fil med filmdata

Du skal **ikke** ændre HTML-strukturen i `index.html`.

---

### Opgave 1 – Link til CSS og JavaScript

I `index.html` skal du indsætte:

- et `<link>`-tag til `css/style.css`
- et `<script>`-tag til `js/movies-script.js`

CSS skal linkes i `<head>`, og JavaScript skal linkes lige før `</body>`.

---

### Opgave 2 – Tilføj Strict Mode

Åbn `js/movies-script.js`.

Tilføj denne linje som det allerførste i filen:

```javaScript
"use strict";
````

---

### Opgave 3 – Opret datastrukturen movies med de første 5 film

Åbn filen movies.txt.

I `js/movies-script.js` skal du nu:

- Opret en konstant variabel med navnet `movies`
- Få variablen `movies` til at pege på arrayet med objekter
- Brug oplysningerne fra **movies.txt**
- Vælg passende datatyper tol de forskellige properties
- Opret kun de første 5 film i arrayet

Hvert objekt skal have følgende properties:

- id
- title
- genre
- year
- duration
- img
- url

Du skal altså oprette de første 5 film i **movies.txt** og skrive dem ind i din JavaScript-datastruktur.

--- 

### Opgave 4 – Opret variablen `moviesContainer`

- Opret en konstant variabel med navnet `moviesContainer`
- Variablen skal pege på elementet med id `movies-container`

Hint: Brug `document.querySelector()`.

---

### Opgave 5 – Opret funktionen `displayMovies(movieList)`

- Opret en funktion med navnet `displayMovies`
- Funktionen skal have en parameter med navnet `movieList`
- Funktionen skal bruges til at vise filmene på siden

---

### Opgave 6 – Brug `map()` til at gennemløbe filmene

Inde i funktionen `displayMovies(movieList)` skal du bruge `map()` til at gennemløbe alle film i `movieList`.

`movieList` er den parameter, som modtager din JS-datastruktur med film.

Start med at skrive denne struktur:

```JavaScript
const html = movieList.map((movie) => {

});
```


---

### Opgave 7 – Returnér HTML inde i map()

Inde i de krøllede parenteser i `map()` skal du bruge `return`, så hver film bliver lavet om til en HTML-streng med et template literal.

Du skal altså bygge denne del op:

```JavaScript
return `indsæt HTML-struktur her`;
```

HTML-strukturen skal bygges op sådan her:

```HTML
<article>
    <h2>titel-placeholder</h2>
    <ul>
        <li>Genre: genre-placeholder</li>
        <li>År: year-placeholder</li>
        <li>Varighed: duration-placeholder</li>
    </ul>
    <figure>
        <a href="url-placeholder" target="_blank" rel="noopener noreferrer">
            <img src="img-placeholder" alt="title-placeholder">
        </a>
        <figcaption>Læs mere på IMDB</figcaption>
    </figure>
</article>
```

---

### Opgave 8 – Erstat pladsholderne med data fra movie

Din opgave er at erstatte pladsholderne i HTML-strukturen med data fra JavaScript-datastrukturen ved hjælp af `${}`.

Du skal opdatere følgende elementer:
- titel
- genre
- år
- varighed
- url
- img
- alt-tekst som skal pege på titel

Det betyder for eksempel, at `titel` skal erstattes med `${movie.title}`, `genre` med `${movie.genre}` osv.

Du skal altså ikke selv finde på HTML-strukturen. Den er allerede bestemt.
Det, du skal gøre, er at indsætte de rigtige værdier fra hvert `movie`-objekt de rigtige steder i strukturen.

--- 

### Opgave 9 – Saml HTML-strengene med `join("")`

Når du bruger `map()`, får du et array med HTML-strenge.

Du skal samle dem til én samlet tekststreng ved at tilføje:

```JavaScript
.join("")
```

Den samlede struktur skal se således ud:

```JavaScript
const html = movieList.map((movie) => {
    return `
        Indsæt din HTML-struktur her
    `;
}).join("");
```

--- 

### Opgave 10 – Indsæt den færdige HTML i DOM’en

Når variablen `html` indeholder den samlede HTML-streng, skal du indsætte den i `moviesContainer` med `innerHTML`.

JS-koden skal se sådan ud: 

```JavaScript
moviesContainer.innerHTML = html;
```

Denne linje skal stå inde i funktionen `displayMovies(movieList)`, efter din `map(...).join("")` og før den afsluttende `}` til funktionen.

---

### Opgave 11 – Kald funktionen med filmdata

Nu skal du kalde funktionen `displayMovies()` og sende din JS-datastruktur med filmdata ind som et argument.

---

### Opgave 12 – Tilføj de resterende film fra movies.txt

Åbn filen **movies.txt** igen.

Du har allerede oprettet de første 5 film i din JavaScript-datastruktur.

Nu skal du udvide din eksisterende variabel `movies`, så den også indeholder de resterende film fra **movies.txt**.

Det betyder, at dit `array` med `js objects` til sidst skal indeholde alle filmobjekter fra **movies.txt**.

---

### Opgave 13 – Grundlæggende CSS styling

Style siden i `css/style.css`.

Siden skal mindst have:

- en centreret overskrift
- luft omkring indholdet
- filmkort med kant eller baggrund
- ensartet afstand mellem elementer
- billeder i en passende størrelse

Du skal forsøge at style siden, så den minder så meget som muligt om referencebilledet, som vises efter opgave 14.

Du må gerne bruge følgende CSS properties:

- `margin`
- `padding`
- `border`
- `border-radius`
- `width`
- `height`
- `max-width`
- `background-color`

---

### Opgave 14 – Layout med CSS Flexbox

Brug CSS Flexbox til at lave layoutet til filmene.

Filmene skal vises som kort i rækker med luft imellem.

Du skal bruge Flexbox på #movies-container.

Her er nogle egenskaber, du kan arbejde med:

- `display: flex`
- `flex-wrap: wrap`
- `justify-content`
- `align-items`
- `gap`

Du skal forsøge at style siden, så den minder så meget som muligt om referencebilledet, som vises her.

![CineMaxx Movies Oversigt](img/cinemaxx-overview.png)
---

### 📚 Ressourcer og hjælp
- W3Schools – JavaScript Arrays - https://www.w3schools.com/js/js_arrays.asp
- W3Schools – JavaScript Objects - https://www.w3schools.com/js/js_objects.asp
- W3Schools – JavaScript Functions - https://www.w3schools.com/js/js_functions.asp
- W3Schools – JavaScript map() - https://www.w3schools.com/jsref/jsref_map.asp
- W3Schools – JavaScript join() - https://www.w3schools.com/jsref/jsref_join.asp
- W3Schools – JavaScript HTML DOM - https://www.w3schools.com/js/js_htmldom.asp
- W3Schools – querySelector() - https://www.w3schools.com/jsref/met_document_queryselector.asp
- W3Schools – innerHTML - https://www.w3schools.com/jsref/prop_html_innerhtml.asp
- W3Schools – Template literals - https://www.w3schools.com/js/js_string_templates.asp
- W3Schools – CSS Flexbox - https://www.w3schools.com/css/css3_flexbox.asp

---

### 📤 Aflevering

Indsæt linket (URL) til dit GitHub-repository på Canvas.

Sørg for, at repository’et er public.

---

### ⏰ Afleveringsfrist

Torsdag d. 23. april 2026, kl. 23.59 på Canvas.
