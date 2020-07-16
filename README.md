## Take-Home Assignment Expanded

-  The user can have from 0 to N `vehicles` and `houses`. The payload will change to a list of objects. If the user has only one vehicle, add 1 point to that vehicle’s score. This same rule applies to houses. 
    
    _Input_
    
    ```jsx
    {
      "age": 35,
      "dependents": 2,
      "houses": [
        {"id": 1, "ownership_status": "owned"}
      ],
      "income": 0,
      "marital_status": "married",
      "risk_questions": [0, 1, 0],
      "vehicles": [
        {"id": 1, "year": 2019},
        {"id": 2, "year": 2010},
        {"id": 3, "year": 2012},
      ]
    }
    ```
  
    _Output_

    ```jsx
    {
        "auto": [
            {"id": 1, "plan": "regular"},
            {"id": 2, "plan": "economic"},
            {"id": 3, "plan": "economic"},
        ],
        "disability": "ineligible",
        "home": [
            {"id": 1, "plan": "regular"}
        ],
        "life": "regular",
    }
    ```


- Houses have a status (`owned` and `rented`). If owned she is eligible for Home insurance. If rented she is eligible for Renters insurance.

    _Input_
    
    ```jsx
    {
      "age": 35,
      "dependents": 2,
      "house": {"ownership_status": "rented"},
      //"house": {"ownership_status": "owned"},
      "income": 0,
      "marital_status": "married",
      "risk_questions": [0, 1, 0],
      "vehicle": {"year": 2018}
    }
    ```
    
    _Output_
    
    ```jsx
    {
        "auto": "regular",
        "disability": "ineligible",
        "renters": "economic",
        //"home": "economic, 
        "life": "regular"
    }
    ```
    


-  If all the risk answers are false and the user has an income lower than 25k, then he is ineligible for all insurance lines.
    
    _Input_
    
    ```jsx
    {
      "age": 35,
      "dependents": 2,
      "house": {"ownership_status": "owned"},
      "income": 20000,
      "marital_status": "married",
      "risk_questions": [0, 0, 0],
      "vehicle": {"year": 2018}
    }
    
    ```
    
    _Output_
    
    ```jsx
    {
        "auto": "ineligible",
        "disability": "ineligible",
        "home": "ineligible",
        "life": "ineligible"
    }

    ```
