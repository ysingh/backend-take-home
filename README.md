# Take Home Assignment for Backend Software Development Candidates at Rooms To Go

Create a command line nodejs application to manage product inventory.

Managing product inventory requires adding products to a product catalog and adding warehouses to store the products. 

We will use 6 commands to enable this functionality: 
1. ADD PRODUCT 
2. ADD WAREHOUSE 
3. STOCK 
4. LIST PRODUCTS
5. LIST WAREHOUSES
6. LIST WAREHOUSE

## Details
- Our application will take in user input one line at a time.

Bold text denotes text that will be entered as-is, italics denote arguments that will be replaced by a value. Optional arguments are surrounded by square brackets ([]).

1. **ADD PRODUCT** *"PRODUCT NAME"* SKU
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
- If a store has a stock limit that will be exceeded by this shipment, either choose to not ship the product or ship enough product so that the Stock Limit is fulfilled.

4. **LIST PRODUCTS**
- List all produts in the product catalog.

5. **LIST WAREHOUSES**
- List all warehouses.

6. **LIST WAREHOUSE** *WAREHOUSE#**
- List information about the warehouse with the given warehouse# along with a listing of all product stocked in the warehouse.

7. **COMMAND HISTORY**
- Lastly we want you to create a stream that writes the command history to a file and write a function that uses promises to uploads the file to s3.

## EXAMPLE SESSION
- Input is prepended with >
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
- Try and write this code as if it will be deployed to production. Including tests.
- Add documentation needed to install any packages, run the tests and code to this README/ replace this README with one of your own with information on how to install and run code and tests.
- Add your code to a github repository and share it with us.
- Lets discuss your solution

Good luck!

