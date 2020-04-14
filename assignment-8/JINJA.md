# Assignment 8 (Jinja templates and session)

In this assignment, you will extend you web-shop mockup from Assignment 3 to a full web application.

You can use the [solution](https://github.com/dat310-spring20/assignments-solutions/tree/master/3) for Assignment 3 in this assignment.
However, there will be extra credit if you use your own solution.

There are again two variants of this assignment. 
 * Using vue (described in a separate file) or
 * using jinja-templates and session.
 
I added a [hint](#hint-saving-order-rows) on saving order rows.
 
Database access will be the same in both assignments:

### Mysql

Your application should use a database called `dat310`. 
The database contains 3 tables `products`, `orders` and `order_rows`.
Write SQL scripts in `script.sql` for 
* CREATING `products` table
* INSERTING data into `products` table
* CREATING `orders` table
* CREATING `order_rows` table

The CREATE script for `products` is already written. The other tables should contain the following columns:

- `orders` has the following columns:
    - `order_id` an integer, the PRIMARI KEY identifying an order. You can use AUTO INCREMENT here.
    - `first_name` the customers first name
    - `last_name` the customers last name
    - `email` the customers email
    - `street` the street in delivery address
    - `city` city in delivery address
    - `postcode` postcode in delivery addresss

- `order_rows` has the following columns:
    - `row_id` an integer, the PRIMARI KEY identifying an order_row. You can use AUTO INCREMENT here.
    - `product_id` an integer. This is the `product_id` of the product that was ordered. Can be a [FOREIGN KEY](https://www.w3schools.com/sql/sql_foreignkey.asp)
    - `order_id` an integer. This is the `order_id` of the order that this row belongs to. Can be a [FOREIGN KEY](https://www.w3schools.com/sql/sql_foreignkey.asp)
    - `count` an integer. How often this product is ordered.
    - `size` the size in which this product is ordered. Can be a string.

### Starter files

Starter files are in the folder called `jinja-templates`.
The starter files already contain a quite complex application.
While browsing the page the shopping cart is stored in the session.
The starter files already contain the following:
 * `app.py` with the following routes:
    - `/` this route renders the `index.html` template.
        You will have to implement retrieving the products from the database.
    - `/product/<pid>` renders the `product.html` template.
        You will have to implement retrieving the products from the database.

### TODO:

* `/add` route. 
This processes the product form, when hitting **add to cart**.
Add the new item to the cart and redirect the user to `/product.html`.
* `/cart`, `/checkout` and `/checkout2` implement the checkout flow. You need to create new templates for these.

#### Checkout flow:

* `/cart`: displays the cart and address form.
    - All fields in the form should be required.
    
![Cart](samples/cart.png)
![Cart](samples/cart2.png)

  * hitting submit on the cart, the user comes to `/checkout` where he can review and approve his order.

![Checkout](samples/checkout.png)
 
  * hitting submit on checkout, the address and cart is stored in the database, the user is shown a confirmation.

![Confirmation](samples/confirmation.png)

#### Hint: Saving order rows:

If your orders table has a `order_id` that is set to autoincrement, you can do the following:
To save the order, first insert the address data into the `orders` table. Then you can retrieve the id of your new order as `lastrowid` and use it when inserting into the order_row table. 
This might look like the code below:

```python
cur.execute(orders_table_sql, arguments)
orderid = cur.lastrowid
for item in cart:
  item['orderid'] = orderid
  cur.execute(order_rows_sql, item)
```

# Øving 8 (Jinja templates og session)

I denne oppgaven skal du utvide din web-shop-mockup fra Innlevering 3 til en fulstendig webapplikasjon.

Du kan bruke [løsningen](https://github.com/dat310-spring20/assignments-solutions/tree/master/3) for Innlevering 3 i denne oppgaven. Det vil imidlertid bli gitt ekstra kreditt hvis du bruker din egen løsning.

Det er igjen to varianter av denne oppgaven.
  * Bruke vue (beskrevet i en egen fil), eller
  * bruk jinja-templates og session som beskrevet under.
  
Jeg la til et [tips](#hint-saving-order-rows) on saving order rows.  
  
Databasetilgang vil være den samme i begge oppgavene:

### Mysql

Din applikasjon skal bruke en database nevnt `dat310`. 
Databasen innehoder 3 tabeller `products`, `orders`, og `order_rows`.
Skriv SQL scripts i `script.sql` for 
* CREATING `products` tabellen
* INSERTING data i `products` tabellen
* CREATING `orders` tabellen
* CREATING `order_rows` tabellen

CREATE scriptet for `products` er allerede på plass. De andre tabellene skal inneholde følgende kolonner:

- `orders` har følgende kolonner:
    - `order_id` en integer, PRIMARI KEY som identifiserer en order. Du kan bruke AUTO INCREMENT her.
    - `first_name` kundens fornavn
    - `last_name` kundens etternavn
    - `email` kundens epost
    - `street` gateadresse til kunden
    - `city` bosted til kunden
    - `postcode` postkode i addressen

- `order_rows` har følgende kolonner:
    - `row_id` en integer, PRIMARI KEY som identifiserer en order_row. Du kan bruke AUTO INCREMENT her.
    - `product_id` en integer. Dette er `product_id` av produktet som er bestillt. Kan være en  [FOREIGN KEY](https://www.w3schools.com/sql/sql_foreignkey.asp)
    - `order_id` en integer. Dette er `order_id` for bestillingen denne raden hører til. Kan være en [FOREIGN KEY](https://www.w3schools.com/sql/sql_foreignkey.asp)
    - `count` en integer. Hvor ofte dette produktet ble bestilt.
    - `size` størrelsen som dette produktet bestilles i. Kan være en streng.

### Start filer

Startfiler er i mappen som heter `jinja-maler`.
Startfilene inneholder allerede et ganske komplekst program.
Når du surfer på siden, blir handlekurven lagret i en session.
Startfilene inneholder allerede følgende:
 * `app.py` med følgende routes:
    - `/` denne viser `index.html` templaten.
        Du må implementere henting av produktene fra databasen.
    - `/product/<pid>` renderer `product.html` templaten.
        Du må implementere henting av produktet fra databasen.
    
### TODO:

* `/add` route. 
Denne behandelr protuct skjemaet, når **add to cart** klikkes.
Legg til den nye varen i handlekurven og redirect brukeren til `/product.html`.
* `/cart`, `/checkout` og `/checkout2` implement checkout flow. Du må lage nye templates for disse.

### Checkout flow:
Du må implementere følgende checkout flow:
  * `/cart`: viser handlekurven or et skjema for leveringsaddressen.
    - Alle felt i skjemaet skal være **required**.

![Cart](samples/cart.png)
![Cart](samples/cart2.png)

  * ved å trykke submit kommer brukeren til `/checkout` hvor han kan se gjennom og godkjenne bestillingen.

![Checkout](samples/checkout.png)
 
  * ved å trykke submit igjen, blir addressen og innhold i hanldevognen  lagret i databasen. Brukeren får en bekreftelse.

![Confirmation](samples/confirmation.png)

#### Hint: Saving order rows:

If your orders table has a `order_id` that is set to autoincrement, you can do the following:
To save the order, first insert the address data into the `orders` table. Then you can retrieve the id of your new order as `lastrowid` and use it when inserting into the order_row table. 
This might look like the code below:

```python
cur.execute(orders_table_sql, arguments)
orderid = cur.lastrowid
for item in cart:
  item['orderid'] = orderid
  cur.execute(order_rows_sql, item)
```
