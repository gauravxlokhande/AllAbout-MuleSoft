

![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/00ccc9ea-4035-4112-83b4-12ade477d663)


![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/245a2608-a428-4630-b0bc-330a6b7e3369)


![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/3234a303-2308-4c79-b226-d62eaaae07ef)



Mup the arry inside objects inside array.
we can use $ only for one loop.

![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/0e34c615-d81c-49ca-9bf0-5ab1d25da854)


if we need to iterate over the multiple array in a object the we use:

``
payload map ((item, index) -> {	
	"Name":item.Name,
	"LastName":item.Lastname
})
``
![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/8bc5d5ef-96d8-4e4e-b92a-d55cd8337c12)


![image](https://github.com/gauravxlokhande/AllAbout-MuleSoft/assets/119065314/01220214-d9bb-4cc8-a372-612667cf5ec7)
