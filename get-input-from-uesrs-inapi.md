```
https://developer.mulesoft.com/tutorials-and-howtos/dataweave/how-to-retrieve-custom-headers-query-uri-parameters-dataweave/
```


# Get Input in Queryparams, header, body, uriparams.

## for Queryparams

in api:
![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/fc47cd97-6cae-4201-9bcd-bcee25bba7e4)
```
http://localhost:8081/gaurav?name=Kaushal
```
for show in var
```
 attributes.queryParams.name
```

## For Headers

in api:
![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/be9f7bf0-0afe-4ae9-9d49-85a4471debce)

for show in var

```
attributes.headers.clientid
```
