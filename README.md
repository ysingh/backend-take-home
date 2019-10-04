# Rooms To Go Engineering: Take Home Assignment

## How we will run your program
1. Clone your repository
2. npm install (or pip install, if your language does not have a installer please provide a bash script called install.sh)
3. npm start (another way to run the app)
4. EOF to quit the REPL

Thank you for your continued interest in Rooms to Go!

This at-home coding challenge is an opportunity for you to write some clean code that shows us how you use data structures to solve algorithmic problems.

  * Write code as if you were shipping it: Assume you are going to be code reviewed, articulate a test plan, etc.
  * We expect this solution to be written in nodejs, but you are welcome to use another language.
  * Use your preferred IDE or editor and whatever tooling you're comfortable with.
  * Feel free to use whatever references you'd like, including Google.
  * Your solution does not have to persist data between runs.
  * When you’re finished, make sure your code is committed to the repo with instructions on how to run it.
  * Your solution should be self-contained and not require additional software to run it.
  * Got an idea for a cool feature to add? Do it! We love seeing your creative side

## Problem Statement
Create a command line REPL to manage product inventory.

Managing product inventory requires adding products to a product catalog and adding warehouses to store the products.

We will use 7 commands to enable this functionality:
1. ADD PRODUCT
2. ADD WAREHOUSE
3. STOCK
4. UNSTOCK
5. LIST PRODUCTS
6. LIST WAREHOUSES
7. LIST WAREHOUSE

## Details
- Our application will take in user input one line at a time.

Bold text denotes text that will be entered as-is, italics denote arguments that will be replaced by a value. Optional arguments are surrounded by square brackets ([]).

1. **ADD PRODUCT** *"PRODUCT NAME"* *SKU*
- This command adds a new product to our product catalog.
- We can have products with the same names but not the same SKU.
- "PRODUCT NAME" - STRING (Do not store the enclosing quotes they are there for us to be able to pass in space seperated product names.
- SKU - Unique Identifier.

2. **ADD WAREHOUSE** *WAREHOUSE#*  *[STOCK_LIMIT]*
- Creates a new warehouse where we can stock products.
- We assume that our warehouses can store infinitely many products if an optional stock limit argument is not specified.
- WAREHOUSE# - INTEGER
- STOCK_LIMIT - Optional, INTEGER

3. **STOCK** *SKU* *WAREHOUSE#* *QTY*
- Stocks QTY amount of product with SKU in WAREHOUSE# warehouse.
- SKU - Unique Identifier, must be a valid sku (is in product catalog).
- Warehouse# - INTEGER, must be a valid warehouse number
- QTY - Integer
- If a store has a stock limit that will be exceeded by this shipment, ship enough product so that the Stock Limit is fulfilled.

4. **UNSTOCK** *SKU* *WAREHOUSE#* *QTY*
- Unstocks QTY amount of product with SKU in WAREHOUSE# warehouse.
- SKU - Unique Identifier, must be a valid sku (is in product catalog).
- Warehouse# - INTEGER, must be a valid warehouse number
- QTY - Integer
- If a store has a stock that will go below 0 for this shipment only unstock enough products so stock stays at 0.

5. **LIST PRODUCTS**
- List all produts in the product catalog.

6. **LIST WAREHOUSES**
- List all warehouses.

7. **LIST WAREHOUSE** *WAREHOUSE#**
- List information about the warehouse with the given warehouse# along with a listing of all product stocked in the warehouse.


## COMMAND HISTORY
We like to keep a log of commands issued in the product management software so we can debug issues that arose during manual data entry.
While the REPL is active, asynchrously stream history to a file in batches of 2.
If a user types in two commands we want those two to be in the same batch, if they type 3 commands stream the first two and wait for the fourth command.
Do not stream more than one batch at a time.


## EXAMPLE SESSION
Here is an example session to show you what a run of your program should look like.
- Example Input is prepended with >
- Example output is not prepended with >.

```
> ADD WAREHOUSE 970
> ADD WAREHOUSE 45
> ADD WAREHOUSE 2

> LIST WAREHOUSES
WAREHOUSES
970
45
2

> ADD PRODUCT "Sofia Vegara 5 Piece Living Room Set" 38538505-0767-453f-89af-d11c809ebb3b
> ADD PRODUCT "BED" 5ce956fa-a71e-4bfb-b6ae-5eeaa5eb0a70
> ADD PRODUCT "TRUNK" 5ce956fa-a71e-4bfb-b6ae-5eeaa5eb0a70
ERROR ADDING PRODUCT PRODUCT with SKU 5ce956fa-a71e-4bfb-b6ae-5eeaa5eb0a70 ALREADY EXISTS

> LIST PRODUCTS
Sofia Vegara 5 Piece Living Room Set 38538505-0767-453f-89af-d11c809ebb3b
BED 5ce956fa-a71e-4bfb-b6ae-5eeaa5eb0a70

> STOCK 38538505-0767-453f-89af-d11c809ebb3b 970 1000
> LIST WAREHOUSE 970
ITEM NAME                               ITEM_SKU                              QTY
Sofia Vegara 5 Piece Living Room Set    38538505-0767-453f-89af-d11c809ebb3b  1000

```

## SUBMISSION
- You can assume that stocking happens without delay and as soon as the command is issued.
- Add documentation needed to install any packages, run the tests and code to this README/ replace this README with one of your own with information on how to install and run code and tests.
- Add your code to a github repository and share it with us.


Good luck!
