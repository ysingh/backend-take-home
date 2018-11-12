# Take Home Assignment for Backend Software Development Candidates at Rooms To Go

Create a command line application to manage product inventory.

Managing product inventory requires adding products to a product catalog, adding stores and warehouses where these products will be stored. 

We stock warehouses with products and finally move products from warehouses to stores.

We will use these 10 commands to enable this functionality: 
1. ADD STORE
2. ADD PRODUCT 
3. ADD WAREHOUSE 
4. STOCK 
5. SHIP 
6. LIST PRODUCTS
7. LIST WAREHOUSES
8. LIST STORES
9. LIST STORE#
10. LIST WAREHOUSE#

## Details
- Our application will take in user input one line at a time.

Bold text denotes text that will be entered as-is, italics denote arguments that will be replaced by some value. Optional arguments are surrounded by square brackets([]).

1. **ADD STORE** *STORE#* *[STOCK_LIMIT]*
Creates a new store where we can stock products. 
- STORE# - INTEGER. The number associated with a specific store location.
- STOCK_LIMIT - INTEGER. The maximum number of stock that can be stores at a store.

2. **ADD PRODUCT** *"PRODUCT NAME"* SKU
This command adds a new product to our product catalog. We can have products with the same names but not the same SKU.
- "PRODUCT NAME" - STRING (Do not store the enclosing quotes they are there for us to be able to pass in space seperated product names.
- SKU - Unique Identifier.

3. **ADD WAREHOUSE** *WAREHOUSE#* 
Creates a new warehouse where we can stock products. We assume that our warehouses can store infinitely many products.
- WAREHOUSE# - INTEGER

4. **STOCK** *SKU* *WAREHOUSE#* *QTY*
Stocks QTY amount of product with SKU in WAREHOUSE# warehouse.
- SKU - Unique Identifier, must be a valid sku (is in product catalog).
- Warehouse# - INTEGER, must be a valid warehouse number
- QTY - Integer

5. **SHIP** *WAREHOUSE#* *STORE#* *SKU* *QTY*
Ships QTY product with sku SKU from warehouse with WAREHOUSE# to store with STORE#.
If a store has a stock limit that will be exceeded by this shipment, either choose to not ship the product or ship enough product so that the Stock Limit is fulfilled.
- WAREHOUSE# - INTEGER, must be a valid warehouse
- STORE# - INTEGER, must be a valid store
- SKU - Unique Identifier
- QTY - INTEGER 

6. **LIST PRODUCTS**
List all produts in the product catalog.

7. **LIST WAREHOUSES**
List all warehouses.

8. **LIST STORES**
List all stores.

9. **LIST** *STORE#*
- List information about store with the given store number along with a listing of all product currently in the store.
- STORE# - INTEGER

10. **LIST** *WAREHOUSE#**
- List information about the warehouse with the given warehouse# along with a listing of all product stocked in the warehouse.


## OTHER INSTRUCTIONS
- Try and write this code as if it will be deployed to production. Including tests.

- Add documentation needed to run the tests and code to this README.

Good luck!

