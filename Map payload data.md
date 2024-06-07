

![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/00ccc9ea-4035-4112-83b4-12ade477d663)


![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/245a2608-a428-4630-b0bc-330a6b7e3369)


![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/3234a303-2308-4c79-b226-d62eaaae07ef)



## map the arry inside objects inside array.
## we can use $ only for one loop.

![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/0e34c615-d81c-49ca-9bf0-5ab1d25da854)


# if we need to iterate over the multiple array in a object the we use:

```
payload map ((item, index) -> {	
	"Name":item.Name,
	"LastName":item.Lastname
})
```


![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/8bc5d5ef-96d8-4e4e-b92a-d55cd8337c12)




![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/01220214-d9bb-4cc8-a372-612667cf5ec7)






In Anypoint Studio, you can perform a variety of operations on the payload using DataWeave. DataWeave is a powerful transformation language that allows you to manipulate data in various formats (such as JSON, XML, CSV, etc.). Here are some common methods and operations you can perform on the payload in Anypoint Studio using DataWeave:

### 1. **Mapping and Transformations:**
- **map:** Iterate over a list and transform each item.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload map ((item, index) -> {
      "Name": item.Name,
      "LastName": item.LastName
  })
  ```

- **mapObject:** Iterate over an object and transform its key-value pairs.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload mapObject ((value, key) -> {
      (upper(key)): value
  })
  ```

### 2. **Filtering:**
- **filter:** Filter items in a list based on a condition.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload filter ((item) -> item.age > 18)
  ```

- **filterObject:** Filter key-value pairs in an object based on a condition.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload filterObject ((value, key) -> value != null)
  ```

### 3. **Reduction:**
- **reduce:** Reduce a list to a single value.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload reduce ((acc, item) -> acc + item.amount, 0)
  ```

### 4. **Plucking:**
- **pluck:** Extract key-value pairs from an object into an array.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload pluck ((value, key, index) -> {
      "key": key,
      "value": value
  })
  ```

### 5. **Grouping:**
- **groupBy:** Group items in a list based on a common attribute.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload groupBy ((item) -> item.category)
  ```

### 6. **Ordering:**
- **orderBy:** Sort items in a list based on an attribute.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload orderBy ((item) -> item.age)
  ```

### 7. **Merging:**
- **++ operator:** Merge two lists.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload ++ [{ "Name": "New Item", "LastName": "New LastName" }]
  ```

- **mergeWith:** Merge two objects.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload mergeWith { "additionalInfo": "some info" }
  ```

### 8. **Accessing Nested Elements:**
- **Using the dot operator to access nested fields.**
  ```dw
  %dw 2.0
  output application/json
  ---
  {
      "firstName": payload.user.details.firstName,
      "lastName": payload.user.details.lastName
  }
  ```

### 9. **Conditional Logic:**
- **if-else:** Conditional expressions within transformations.
  ```dw
  %dw 2.0
  output application/json
  ---
  payload map ((item, index) -> 
      if (item.age > 18) 
      {
          "Name": item.Name,
          "Status": "Adult"
      } 
      else 
      {
          "Name": item.Name,
          "Status": "Minor"
      }
  )
  ```

### 10. **String Operations:**
- **String manipulation functions:** such as `upper`, `lower`, `trim`, etc.
  ```dw
  %dw 2.0
  output application/json
  ---
  {
      "fullName": upper(payload.firstName) ++ " " ++ upper(payload.lastName)
  }
  ```

### Example Combining Multiple Operations:

Here's a comprehensive example that combines several operations:

```dw
%dw 2.0
output application/json
---
{
    "adults": payload filter ((item) -> item.age > 18) map ((item) -> {
        "fullName": upper(item.firstName) ++ " " ++ upper(item.lastName),
        "age": item.age
    }),
    "minors": payload filter ((item) -> item.age <= 18) map ((item) -> {
        "fullName": upper(item.firstName) ++ " " ++ upper(item.lastName),
        "age": item.age
    })
}
```

In this example, the payload is filtered into adults and minors, and for each, the full name is constructed and converted to uppercase.

These are just a few examples of the wide range of operations you can perform on the payload using DataWeave in Anypoint Studio. DataWeave offers many more functions and operators to manipulate and transform data as needed.
