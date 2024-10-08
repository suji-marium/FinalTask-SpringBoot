# Inventory management system 

## Database Diagram
<center>
<img src = "databasediagram_part2.png" alt ="employee-entity-design" style="width:450px">
</center>

## API Methods

1. POST /api/ims/create-category

    - request-body: category details as JSON
    ```json
    {
        "category_name":"Groceries"
    }
    ```
    - response-status : 200
    - response-body: Response message as JSON
     ```json
    {
        "message": "Category created successfully"
    }
    ```

2. POST /api/ims/create-product 

    - request-body: product details as JSON
    ```json
    {
        "product_name":"Rice",
        "category_id":1,
        "price":45,
        "quantity":80
    }
    ```
    - response-status : 200
    - response-body: Response message as JSON
     ```json
    {
        "message":"Product created successfully"
    }
    ```

3. GET /api/ims/getproduct?category_id=1
    - query-param : category_id
    - query-param-required : false
    - query-param : product_id
    - query-param-required : false
    - response-status : 200
    - response : product details as JSON

    ```json
    [
        {
            "product_id": 1,
            "product_name": "Rice",
            "category": {
                "category_id": 1,
                "category_name": "Groceries"
            },
            "price": 45.0,
            "quantity": 80
        },
        {
            "product_id": 2,
            "product_name": "Wheat",
            "category": {
                "category_id": 1,
                "category_name": "Groceries"
            },
            "price": 55.0,
            "quantity": 18
        }
    ]
    
    ```

4. GET /api/ims/getcategory?category_id=1

    - query-param : category-id
    - query-param-required : false
    - response-status : 200
    - response : category details as JSON
    
    ```json

    {
        "category_id": 1,
        "category_name": "Groceries"
    }

    ```
5. UPDATE api/ims/updateProduct?productId=1&quantity=30
 
    - query-param : productId
    - query-param-required : true
    - query-param : productName
    - query-param-required : false
    - query-param : categoryId
    - query-param-required : false
    - query-param : price
    - query-param-required : false
    - query-param : quantity
    - query-param-required : false
 
    - response-status : 200
    - response-body:
 
     ```json
        {
            "message" : "Product updated successfully"
        }
    ```
 
6. UPDATE api/ims/updateCategory?categoryId=1&categoryName=Groceries
 
    - query-param : categoryId
    - query-param-required : true
    - query-param : categoryName
    - query-param-required : true
    - response-status : 200
    - response-body:
 
     ```json
        {
            "message": "Category updated successfully"
        }
    ```

7. DELETE /api/ims/delete_category?category-id=1

    - query-param : category-id
    - query-param-required : true
    - response-status : 200
    - response : 

    ```json
    {
        "message":"Successfully deleted grocery from the category list"
    }
    ```

8. DELETE /api/ims/delete_product?product-id=1

    - query-param : product-id
    - query-param-required : true
    - response-status : 200
    - response : 
    
    ```json
    {
        "message":"Successfully deleted rice from the product list"
    }
    ```

9. UPDATE /api/ims/sell

    - request
    ```json
    {
        "product_id":6,
        "userid":6,
        "quantity":10
    }
    ```
    - response-status : 200
    - response : 

    ```json
    {
        "message":"Successfully sold out the product with id: 6"
    }

    ```

10. UPDATE /api/ims/restock
    - request
    ```json
    {
        "product_id":6,
        "userid":1,
        "quantity":10
    }
    ```
    - response-status : 200
    - response : 

    ```json
    {
        "message":"Successfully restocked the product with id: 6"
    }
    
    ```



