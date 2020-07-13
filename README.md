## Take-Home Assignment Expanded

-  Add `Umbrella` insurance line. If the user got an economic score in any of the four main lines of insurance (life, disability, home & auto), he is eligible to get umbrella insurance. Base rules are applied to it.
    
    _Input_
    
    ```jsx
    {
      "age": 35,
      "dependents": 2,
      "house": {"ownership_status": "owned"},
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
        "home": "economic",
        "life": "regular",
    		"umbrella": "economic"
    }
    
    ```


- Add divorced and domestic partnership to marital status options. If domestic partnership, add 1 risk point to the life score and remove 1 risk point from disability.

    _Input_
    
    ```jsx
    {
      "age": 35,
      "dependents": 2,
      "house": {"ownership_status": "owned"},
      "income": 0,
      "marital_status": "domestic partnership",
      "risk_questions": [0, 1, 0],
      "vehicle": {"year": 2018}
    }
    
    ```
    
    _Output_
    
    ```jsx
    {
        "auto": "regular",
        "disability": "ineligible",
        "home": "economic",
        "life": "regular"
    }
    


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
