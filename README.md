# SpringBoot-Lambda-Demo-Boilerplate
Boilerplate code for Java SpringBoot lambda creation example.

## Steps to create Spring Boot app
1. Create new project.
2. Choose Java 17 and Maven for builds.
3. In the archetype selection of Maven Central, choose ```com.amazonaws.serverless.archetypes:aws-serverless-springboot3-archetype```.
4. Then click create.

## Steps to deploy code to lambda
1. From AWS Console, Go to your function.
2. Click "Test".
3. Choose template as ```API Gateway AWS Proxy``` .
4. Update payload: 
	a. path to endpoint of your app.
	b. httpMethod to GET/POST based on your endpoint mapping.
5. Click "Invoke".

## Steps to create REST API through API Gateway to test your endpoint
1. From AWS Console, create new API, choose Rest API.
2. Add a name to your API and leave the rest to default.
3. Click create Resource, add ```{{proxy+}}``` in the resource name to handle all the incoming requests to API Gateway.
4. Click create Method, with ANY as the Method Type, choose lambda proxy and select your lambda function.
5. Click "Create Method".

## Steps to deploy API
1. From the Resources page, click on deploy API.
2. Select new stage from the dialog box, give a stage name and click "Deploy".

## Testing the endpoint through API Gateway
1. Once you deploy the API, you get an Invoke URL in the format -> ```https://{app-id}.execute-api.{region}.amazonaws.com/{stage}```.
2. Use this url through Postman or your browser and add the endpoint at the end of the url -> ```https://{app-id}.execute-api.{region}.amazonaws.com/{stage}/{endpoint}```.
Note: If you get a missing token error, just add your endpoint at the end of your url
