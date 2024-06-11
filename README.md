# Most imp note: We can connect Mulesoft with any database Like Salesforce, MySql just by CONFIGURE IT IN LISTNER.

## Note1:  All Salesforce Components in Anypoint studio Takes input as array of objects. Like [{},{}] you can gave it like this or if ur passing object  it invalid if you want to make it valid then take in transform msg an gave paload [payload] like this.

## Note2: in salesforce upsert operation alway enable external field ans gave external field its mandatory else make enable already exist field external field by editing it.

## Note3: Whatever we are passing in body raw it we can get in payload also we can access it like paload.id.

## Note4: massage transform is itself a payload.

## Note5: Remember we can create a file for store variables values and all test.properties in src/main/resources but to access it we need to add it in global elements/create/ global configuration/ configuration properties and add this test.properties file

