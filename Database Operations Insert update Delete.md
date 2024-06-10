# All Operations on database using Mulesoft Anypoint Studio.

refer
```
https://docs.mulesoft.com/db-connector/latest/database-insert-update-delete
```

# INSERT

![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/9f66150f-afad-432a-a5e5-0a1c13ca14d2)
![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/e23ec7b2-02a1-4a00-9822-39753edad9e6)

## SQL Query text
```
INSERT INTO sakila.actor ( first_name, last_name, last_update) VALUES (:firstname, :lastname,:lastupdate);
```

## Input Parameters
```
output application/json
 ---
{
	firstname: vars.FirstName,
	lastname: vars.LastName,
	lastupdate: now()
}
```

# Update
