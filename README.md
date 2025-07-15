# Online-Shop-Simulation-Using-Python-SQL
Explore the backend of an e-commerce platform with this Python project! It simulates a basic online shop's database, covering schema design, data management, and interactive user flows for both customers and sellers using SQLite.

The core of the project is a Jupyter Notebook (`Project_akhir.ipynb`) that sets up the database, populates it with sample data, and includes an interactive loop for simulating transactions.

## Features

-   **Database Creation:** Defines tables for `Customers`, `Seller`, `Product`, `Cart`, `Payment`, `Shipping`, `Brand`, `Category`, and `Transactions`.
-   **Data Insertion:** Populates the tables with sample data.
-   **Interactive Interface:** A command-line interface that allows users to act as a customer or a seller, view products, add items to a cart, make payments, and simulate shipping.
-   **Data Analyst Mode:** A special mode to view all database tables, useful for debugging and understanding the data.

## Database Schema

The SQLite database (`olshop.db`) contains the following tables:

-   **`Customers`**:
    -   `customer_ID` (INTEGER)
    -   `customer_number` (INTEGER)
    -   `customer_name` (VARCHAR(50))
    -   `customer_email` (VARCHAR(50))
    -   `customer_gender` (VARCHAR(10))
    -   `customer_address` (VARCHAR(100))

-   **`Seller`**:
    -   `seller_ID` (INTEGER)
    -   `seller_number` (INTEGER)
    -   `seller_name` (VARCHAR(50))
    -   `seller_address` (VARCHAR(100))

-   **`Product`**:
    -   `product_ID` (INTEGER)
    -   `brand_ID` (INTEGER)
    -   `seller_ID` (INTEGER)
    -   `product_name` (VARCHAR(50))
    -   `product_price` (INTEGER)

-   **`Cart`**:
    -   `cart_ID` (INTEGER)
    -   `customer_ID` (INTEGER)
    -   `product_ID` (INTEGER)
    -   `number_of_product` (INTEGER)

-   **`Payment`**:
    -   `payment_ID` (INTEGER)
    -   `payment_date` (DATE)
    -   `payment_amount` (FLOAT)
    -   `payment_methods` (VARCHAR(20))
    -   `seller_ID` (INTEGER)
    -   `cart_ID` (INTEGER)
    -   `payment_status` (STRING)

-   **`Shipping`**:
    -   `shipping_ID` (INTEGER)
    -   `shipping_duration` (TIME)
    -   `shipping_date` (DATE)
    -   `shipping_price` (FLOAT)
    -   `seller_ID` (INTEGER)
    -   `customer_ID` (INTEGER)

-   **`Brand`**:
    -   `brand_ID` (INTEGER)
    -   `brand_name` (VARCHAR(20))
    -   `category_ID` (INTEGER)

-   **`Category`**:
    -   `category_ID` (INTEGER)
    -   `category_name` (VARCHAR(20))

-   **`Transactions`**:
    -   `customer_ID` (INTEGER)
    -   `seller_ID` (INTEGER)
    -   `product_ID` (INTEGER)
    -   `cart_id` (INTEGER)
    -   `payment_ID` (INTEGER)
    -   `shipping_ID` (INTEGER)
    -   `payment_amount` (FLOAT)

## Getting Started

### Prerequisites

-   Python 3.x installed.
-   Jupyter Notebook or JupyterLab.

### Running the Project

1.  **Start Jupyter Notebook/Lab:**
    ```bash
    jupyter notebook
    # or jupyter lab
    ```

2.  **Open `Project_akhir.ipynb`:**
    Navigate to the `Project_akhir.ipynb` file in the Jupyter interface and open it.

3.  **Run all cells:**
    Execute all cells in the notebook sequentially. The script will create the `olshop.db` SQLite database file in the same directory as the notebook.

4.  **Interact with the simulation:**
    Follow the prompts in the output cells to interact with the online shop simulation as a customer or seller.

    -   **User Type Prompt:** `What is your purpose here? (User includes seller or customer (0)/Data Analyst (enter company code)):`
        -   Enter `0` for a regular user (customer/seller).
        -   Enter `5555` for Data Analyst mode (to view all tables).

    -   **Customer/Seller Prompt (if you entered `0` above):** `Are you here as a customer (0) or a seller (1)?:`
        -   Enter `0` to simulate as a customer.
        -   Enter `1` to simulate as a seller.

    -   **Seller Prompts:**
        -   `Enter your full name:`
        -   `Enter your phone number:`
        -   `Enter your address:`
        -   `Do you want to sell a product on the app? YES(0)/NO(1):`
        -   `What is the brand name of the product you want to sell?:`
        -   `What category does your product fall under?:`
        -   `What is the name of the product you want to sell?:`
        -   `What is the price of your product? (numbers only, e.g. 20000):`

    -   **Customer Prompts:**
        -   `Do you want to purchase a product?`
        -   `Enter 0 if you do not want to buy anything and 1 if you do:`
        -   `Please enter your personal details!`
        -   `Enter your full name:`
        -   `Enter your phone number:`
        -   `Enter your email address:`
        -   `Enter your gender, M/F:`
        -   `Enter your shipping address:`
        -   `Do you want to add a product to the cart? (Yes=0/No=1):`
        -   `Enter how many products you want to buy!:`
        -   `Please enter the details of the product you want to buy`
        -   `Enter the product id of the product you want to buy!:`
        -   `Enter the seller id of the product you want to buy!:`
        -   `Enter the total amount of your purchase in Rupiah (e.g. 100000):`
        -   `Which payment method would you like to use? (debit, credit, e-wallet):`
        -   `Choose your preferred shipping price and duration, (0) for 5 days at Rp.10,000 or (1) for 1 day at Rp.30,000:`

