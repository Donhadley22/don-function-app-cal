# AZURE FUNCTION APP CALCULATOR

## Table of Contents
### 1. General Information
### 2. Prerequisites
### 3. Installation and Setup
### 4. Testing the Application

## General Information
   
*This is a Function App Calculator built using Visual Studio and deployed in Azure for operation. 
*It uses HTTP trigger to call on the Azure Function App to run this run this functon over a web browser.
*This app sums up the provided values of variables x and y that are integers and returns a nemerical value.



## Prerequisites

Before setting up and using this function app, ensure you have the following:

- An Azure subscription
- Azure Functions Core Tools installed locally
- .NET Core SDK
- Visual Studio

## Installation and Setup

### Create Azure Fuction App
*Sign into the Azure portal in this URL https://portal.azure.com with your account details
*Go to the search bar, search and select Functon app, then click on create to enter specific configurations as demanded.
*On the Basics page, provide your Resource group, Function App name and Region. Leave other configurations as default.
*The Operating system should be Windows and Hosting options and plans is Consumption (Serverless).
*Select "Review + create" to review the app configuration selections.
*On the "Review + create" page, review your settings, and then select "Create" to provision and deploy the function app.
*Go to resource to view your new function app.

### Building the function
*This function was built using the Azure Function project template on  Visual Studio.
*The Function worker is .NET6.0
*The public static class in the template was changed to Sum.
*The Fuction name was also changed to Sum.
*The HTTP trigger and logger were left untouched.
*These lines of code were added to define the function:
```shell
int x =int.Parse(req.Query["x"]);

int y =int.Parse(req.Query["y"]);

int result = x + y;

return new OkobjectResult(result);
 ```
*The ParseInt method that was used in the function parses a value as a string and returns integers.

### Deploying the function to Azure from Visual Studio
*On the code editing page, click on Build button at the top of the page and select Publish section button on the displayed list.
*Under Publish Target select Azure and click Next.
*On Specific target, select Azure Function App (Windows) and click Next.
*On Select existing or create a new Azure Function, select the Resource Group of the Function App you created earlier by clicking on it.
*Then select the Azure Function app that you created earlier and click on Finish button bellow.
*On the Publish profile creation progress page, click Close when it is done.
*When it displays Ready to Publish, click on Publish and wait till is displays a notification that it is done publishing your function.

## Testing the Application
*Go to Azure portal and click on the Function App
*click on the function name Sum under Functions displayed on your Function app Overview page. 
*Then click on Get Function Url and copy the displayed Url.
*Paste the copied Url into your browser and provide values for the Function Variables x and y. 
*To provide the values, at the end of the Url in the browser, where you have this symbol == enter the values in this format &x=500&y=300 hit enter. This will trigger the Function to run and return a result which is the sum of the two values provided, in this instance, 800.

### Thank you for reading!