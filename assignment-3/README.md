# Assignment 3 - Booking prototype

In this assignment you need to create a prototype for a (online shopping) site using HTML and CSS. The prototype consists of three HTML pages (front page `index.html`, product page `product.html`, and shopping cart/checkout `cart.html`) and a single stylesheet file (`style.css`).

Under the `samples/` folder of the starting files (in your private GitHub repository) you will find screenshots that serve as examples of what you need to create. You don't have to produce the exact same output that is shown on the samples, you can deviate from it in any way you want (especially in the content) as long as you follow the instructions given below.


### Fonts and colors

  *	Sans-serif font family.
  * All headings are typeset Montserrat, all other text is typeset Raleway.
    -	https://fonts.google.com/specimen/Montserrat
    -	https://fonts.google.com/specimen/Raleway
  *	Font sizes are controlled by the browser; all font sizes need to be set relative, using *em*.
  *	Background color is white.
  *	You need to select a color palette from http://www.colourlovers.com/palettes, with maximum five colors, and use only those colors (plus white for page background).
    -	Provide in the `README.md` file the link to the chosen palette and also list the hex codes of the colors from that palette.


### Layout

  *	Use the `<header>`,` <main>`, and `<footer>` HTML5 tags for structuring the page.
  *	The elements below are the same on all pages.
  *	**Header**
    -	Height is 40px. The header is always visible, even when the page is scrolled down.
    -	The logo area has a height of 60px. It is positioned 5% from the left of the page.
        -	You can write the name of your site here and/or create a logo.
        -	The logo needs to overlay any content (i.e., needs to have the highest z-index).
    -	The main menu is part of the header and is horizontally aligned.
        -	It has to be an unordered list inside a `<nav>` element.
        -	It is right aligned and 5% from the right side of the page.
        -	It contains 3 links, pointing to index.html, product.html and cart.html.
        - Every link is represented by an icon.
  *	**Main**
    -	There has to be 100px vertical space (margin or padding) on top of the main area.
    -	The main area is 90% of the width of the page and is center-aligned. That means it resizes automatically when the window is resized, but has a maximum width of 1400px (see the screenshots under `samples/`).
    -	Main headers (h1) inside `<main>` have a background color, 1.2em font size, and 5px padding around (see Product Page).
    -	Framed boxes have a solid 1px border and 5px padding. The font-size is 0.8em.
  *	**Footer**
    -	The footer always stays at the bottom of the page, but the footer is "sticky" (i.e., when the page is long, you need to scroll down to see the footer)
        - Main idea is to set `min-height: 100%` on the `<html>` element.
        - Then position the footer absolute, or use a flexbox.
        -	See, e.g.,: https://css-tricks.com/couple-takes-sticky-footer/
    -	The height of the footer is 120px. It has a 5px wide top border.
    -	The footer contains contact information (tel, email). These are center-aligned both vertically and horizontally.


### Front page (`index.html`)

  * The front page contains a summary of the shopping cart in an `<aside>` element and the shop content.
  * The shopping cart summary:
    - Has a width of 300px.
    - Is placed to the right, inside the `<main>` element.
    - Contains a clickable `<h2>` heading that links to `cart.html`.
    - Contains a table with contents of the shopping cart (at least 3 rows).
    - Is highlighted with a different background color.
  * The shop content:
    - Contains an image banner that spans the width (i.e. 100%) of the shop content and resizes with the page. It has 5px wide solid top and bottom borders.
    - Contains (at least) 6 products.
      - Put each product inside an `<article>` element.
      - The products have a target width of 280px, but may grow or shrink to fit on a line.
      - Depending on screen size, 1 to 3 products are shown per line.
      - Products contain an image, product name and a short summary.
      - Image span the complete width of the `<article>`, is quadratic, and has a border.
      - Product name is an `<h3>`, with no margins.
      - Price is displayed together with the product name, but is right aligned.
      - The complete product `<article>` is a link to `product.html`.
    - Change the appearance of the product on mouseover, e.g. change background or borders)
    - Some of the products should contain a discount batch that is displayed on top of the image (hint: set z-index).
    - Discount batch should be located 30px from the top and right side of the image.

### Product page (`product.html`)

  * Just like the front page, product page contains a summary of the shopping cart in an `<aside>` element
  *	Show the image, name, and short description of the product at the top of the page in a framed box.
  * Show a form to select amount and size of the elements.
  * The form contains a field that shows the price that does not allow input.
  * Size should be a select containing at least 3 options.
  * Form labels are right aligned, and both form elements have the same size.
  * Display an "Add to Cart" button which is highlighted through background color.
  * Depending on the page width, the product information and form is displayed to the right or below the image (hint flexbox).
  *	Display a "Details" header (h1).
  *	Display a long description in a framed box.


### Shopping cart page (`cart.html`)

  *	Display a "Cart" header (h1).
  * Display the cart as a table in a framed box.
  * The table contains the product name, size, count, price, discount, calculated price, and for every row a cancel button.
  *	Display a "Checkout header" header (h1).
  * Display the checkout form in a framed box.
  * Checkout form contains the fields with appropriate input types
    - First name
    - Last name
    - Email
    - Street
    - City
    - Postal code
  * Form also contains a checkbox for agreeing to terms of service and a submit button.
  * Form elements are structured into Billing details, Delivery address and Submit order, as shown in images.
  * Form elements are horizontally and vertically aligned.
  * Form fields have the same size and labels are right aligned. 

Commit and push the files you created (`index.html`, `product.html`, `cart.html`, `style.css`, plus optional images) to GitHub.

**Optional** Use a media query to display the `<aside>` element on top rather then next to the main content on small screens, as shown in [here](samples/optional_index_small.png). Hint: use a media query to change the flex-direction as in [this example](https://www.w3schools.com/csS/tryit.asp?filename=trycss3_flexbox_website2).

# Oppgave 3 - Webshop-prototype

I denne innleveringen skal du lage en prototype for en (online shopping) nettside ved bruk av HTML og CSS. Prototypen skal bestå av tre HTML sider (hovedsiden `index.html`, produktsiden `product.html` og handlekurv/utskjekk-siden `cart.html`) og en enkel css-fil (`style.css`).

Under `samples/` mappen finner du skjermbilder som skal fungere som eksempel av hva du skal lage. Du trenge ikke å lage en eksakt kopi av bildene, og så lenge du følger instruksjonene under kan du forandre på dem som du ønsker (spesielt i innhold).


### Skrift og farge

  *	Sans-serif font familie.
  *	Alle headings er av typen Montserrat, all annen tekst av typen Raleway.
    -	https://fonts.google.com/specimen/Montserrat
    -	https://fonts.google.com/specimen/Raleway
  *	Fontstørrelse er kontrollert av nettleser; ergo må de alle være relative, med bruk av *em*.
  *	Bakgrunnsfargen skal være hvit.
  *	Du må velge en color palette fra http://www.colourlovers.com/palettes, med max fem farger, og bruk kun disse fargene (pluss whit for sidebakgrunn).
    -	Oppgi i `README.md` lenken til den valgte paletten, og oppgi også heksekoder for fargene fra den paletten.


### Layout
  
  *	Bruk `<header>`, `<main>`, og `<footer>` HTML5 taggene for å strukturere siden.
  *	Elementene under er like på alle sider.
  *	**Header**
    -	Høyden er 40px. Headeren er alltid tilgjengelig, selv om vi blar nedover siden.
    -	Logoen skal ha en høyde på 60px. Den er posisjonert 5% fra venstre kant av siden.
        -	Du kan skrive navnet på siden din her og/eller lage en logo
        -	Logoen må ligge over alle andre typer innhold (ergo den trenger å ha den høyeste z-indexen).
    -	Hovedmenyen er en del av headeren og ligger på rekke horisontalt.
        -	Det skal være en uordnet liste inni et `<nav>` element.
        -	Den er justert mot høyre og ligger 5% fra høyre side av dokumentet.
        - Den inneholder 3 lenker, som peker til index.html, product.html og cart.html.
        - Hver lenke er representert med et ikon.
    
  *	**Main**
    -	Det skal være 100px vertikalt rom (margin eller padding) på toppen av mainområdet.
    -	Skal være 90% i bredden og være sentrert. Det betyr at den skal automatisk tilpasse seg når sidestørrelsen forandres, men den skal ha en maximum bredde på 1400px (se bildene under `samples/`).
    -	Hovedoverskrifter (h1) i `<main>` skal ha en bakgrunnsfarge, 1.2em font størrelse og 5px padding rundt (e.g. på produktsiden)
    -	Innrammede bokser har en solid 1px border og 5px padding. Font størrelse 0.8em.

  *	**Footer**
    -	Footeren skal alltid være på bunnen av siden, men den skal kunne "blas vekk" (dersom siden er for lang må brukeren bla ned for å kunne se den).
        - Hovedideen er å stille inn "min-høyde: 100%" på `<html>` elementet.
        - Deretter bruk absolutt posisjonering på footeren, eller bruk en flexbox.
        -	Eller se, for et eksempel: https://css-tricks.com/snippets/css/sticky-footer/
    -	Høyden skal være på 120px. Den skal ha en 5px bred topp border.
    -	Footeren skal inneholde kontaktinformasjon (telefon, e-post). Disse er sentrert både vertikalt og horisontalt.


### Hovedsiden (`index.html`)
  
  * Hovedsiden inneholder et sammendrag av handlekurven i et  `<aside>` element og butikk-innholdet.
  * Sammendrag av handlekurven:
    - Har en bredde på 300px.
    - Plasseres til høyre, inne i `<main>` elementet.
    - Inneholder en klikkbar `<h2>` overskrift som lenker til `cart.html`.
    - Inneholder en tabell med innholdet i handlekurven (minst 3 rader).
    - Blir fremhevet gjennom en annen bakgrunnsfarge.
  * Butikk-innholdet:
    - Inneholder et bildebanner som spenner over bredden (dvs. 100%) av butikk-innholdet og som tilpasses sidestørrelsen automatisk. Den har 5px bred solid topp og bunn border.
    - Det skal listes (minst) 6 produkter.
      - Plasser hvert produkt i et eget `<article>` element.
      - Produktene har en målbredde på 280px, men kan vokse eller krympe for å passe på en linje.
      - Avhengig av skjermstørrelse vises 1 til 3 produkter per linje.
      - Produktene inneholder et bilde, produktnavn, pris, og en kort oppsummering.
      - Bildet tar nesten hele bredden til `<article>` elementet, er kvadratisk og har en border.
      - Produktnavnet er en `<h3>` uten marginer.
      - Pris vises sammen med produktnavnet, men justert til høyre.
      - Den komplette produkt `<article>` er en lenke til `product.html`.
    - Endre utseendet til `<article>` elemented ved "mouseover", f.eks. endre bakgrunn eller border).
    - Noen av produktene skal inneholde en rabattmarker som vises øverst på bildet (hint: angi z-indeks).
    - Rabattmarkeren skal være plassert 30px fra oversiden og høyre siden av bildet.

### Produkt side (`product.html`)

   * Lik hovedsiden inneholder produktsiden et sammendrag av handlekurven i et `<aside >` element.
   * Vis bilde, navn og kort beskrivelse av et produkt øverst på siden i en innrammet boks.
   * Vis et skjema for å velge mengde og størrelse på elementene.
   * Skjemaet også inneholder et felt som viser prisen som ikke tillater input.
   * Størrelse skal være et select element som tilbyr minst 3 alternativer.
   * Skjema labels er aligned mot høyre, og skjemaelementene har samme størrelse.
   * Vis en "Legg i handlekurv" -knappen som er uthevet gjennom bakgrunnsfarge.
   * Avhengig av sidebredden, vises informasjonen og skjemaet til høyre eller under bildet (hint flexbox).
   * Vis en "Details" overskrift (h1).
   * Vis en lang beskrivelse i en innrammet boks.

### Handlekurv side (`cart.html`)

  * Vis en "Cart" overskrift (h1).
  * Vis handlekurven som en tabell i en innrammet boks.
  * Tabellen inneholder product name, size, count, item price, discount, calculated price, og for hver rad en cancel-knapp.
  * Vis en "Checkout" overskrift (h1).
  * Vis utsjekkingsskjema i en innrammet rute.
  * Skjemaet inneholder feltene med passende inndatatyper
    - Fornavn
    - Etternavn
    - E-post
    - Gate
    - By
    - Postnummer
  * Skjemaet inneholder også en avkrysningsrute (checkbox) for å godta tjenestevilkår og en sende-knapp.
  * Skjemaelementer er strukturert i Billing details, Delivery address, og Submit order, som vist på bilder.
  * Formelementer er horisontalt og vertikalt på linje.
  * Formfelt har samme størrelse og etikettene er riktig justert.

**Optional** Bruk en media query for å vise `<aside>` elementet overfor, heller en ved siden av hoved innholdet på skjermer mindre enn 1200px, som vist [her](samples/optional_index_small.png). Tip bruk en media query for å bytte ut flex-direction som i [dette eksempel](https://www.w3schools.com/csS/tryit.asp?filename=trycss3_flexbox_website2).

Commit og push filene du laget (`index.html`, `product.html`, `cart.html`, `style.css`, plus valgfrie bilder) til GitHub.
