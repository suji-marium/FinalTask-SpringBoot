# Employee 

## Database Diagram

<center>
<img src = "databasediagram_part1.png" alt ="employee-entity-design" style="width:500px">
</center>

## API Methods

1. GET /api/employees/employee-name-start?starts-with-letter="s"

    - query-param : starts-with-letter 
    - query-param-required : true
    - response-status : 200
    - response : employee details as JSON
    ```json
    
    {
        "message": "Successfully fetched",
        "employeeDetails": [
            {
                "empName": "Sumi Saji",
                "empId": 2,
                "streamName": "Sales",
                "designation": "Manager",
                "accountName": "SmartOps",
                "managerName": "Self (Manager)"
            },
            {
                "empName": "Shanu Mohan",
                "empId": 4,
                "streamName": "Sales",
                "designation": "Associate",
                "accountName": "Walmart",
                "managerName": "Manu Mathew"
            }
        ]
    }
    
    ```

2. GET /api/employees/allstreams
    - query-param-required : false
    - response-status : 200
    - response : streams details as JSON
    ```json
   {
        "message": "Successfully fetched",
        "streams": [
            "Sales",
            "Developer",
            "Delivery",
            "Computing",
            "Q&A"
        ]
    }
    ```

3. PUT /api/employees/update-to-manager?employeeId=1&streamId=2
    - query-param : employeeId
    - query-param : streamId
    - query-param-required : true
    - response-status : 200
    - response
    ```json
    {
        "message": "Varun Nair's details have been successfully updated."
    }
    ```

4. PUT /api/employees/update-to-employee?employeeId=4&managerId=2
    - query-param : employeeId
    - query-param : managerId
    - query-param-required : true
    - response-status : 200
    - response
    ```json
    {
        "message": "Shanu Mohan's details have been successfully updated."
    }
    
    ```