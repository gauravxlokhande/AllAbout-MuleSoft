# MuleSoft 


### Who & what is MuleSoft?
MuleSoft provides the most widely used integration platform for connecting SaaS & enterprise applications in the cloud and on-premise.
Back in 2018, MuleSoft was acquired by Salesforce primarily to accelerate customers digital transformations. MuleSoft's integration platform enables not only to unlock data across legacy systems, cloud apps and devices but also to make smarter and faster decisions, and offer highly connected experiences for end-users.
MuleSoft's Anypoint Platform is now a part of the Salesforce Integration Cloud. Conversely, MuleSoft has a pre-built connector into Salesforce for seamless integration.


### we can access mulesoft from below website.
```
https://anypoint.mulesoft.com/
```

### What Is RAML?
RAML stands for RESTful API Modeling Language, which is a YAML-based language for describing APIs. It was developed by MuleSoft in 2013 and is now owned by Salesforce. RAML is used to model APIs, not just document them, and can help developers create efficient API management strategies. It's concise and reusable, and can be used to manage the API lifecycle from design to deployment to sharing. 
RAML is designed to describe APIs in a way that's readable by both humans and computers. It focuses on describing resources, methods, parameters, responses, media types, and other HTTP constructs that form the basis for modern APIs. RAML isn't strict, and can be used to describe APIs that obey many, but not all, RESTful constraints


```yaml
#%RAML 1.0
title: Hello world # required title

/greeting: # optional resource
  get: # HTTP method declaration
    responses: # declare a response
      200: # HTTP status code
        body: # declare content of response
          application/json: # media type
            # structural definition of a response (schema or type)
            type: object
            properties:
              message: string
            example: # example how a response looks like
              message: "Hello world"
```

```yaml
#%RAML 1.0
title: Hello World API # Title of the API

/greeting: # Define a resource at the path /greeting
  get: # HTTP GET method for the /greeting resource
    description: Returns a greeting message # Description of the GET method
    queryParameters: # Section to define query parameters
      name: # Define a query parameter named 'name'
        description: The name to include in the greeting message # Description of the 'name' query parameter
        type: string # Data type of the 'name' parameter, which is a string
        required: false # Indicates that the 'name' parameter is optional
    responses: # Section to define the responses for the GET method
      200: # HTTP status code for a successful response
        body: # Define the body of the response
          application/json: # Media type of the response body
            type: object # Define the structure of the response body as an object
            properties: # Properties of the response object
              message: string # 'message' property of type string
            example: # Example of a response
              message: "Hello, world" # Example response message
```
