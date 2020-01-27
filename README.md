# sys-weather
This system API provides list of Cities in a country and weather details for a city or country.

# Application Design

- Created RAML reusable assets, published in Exchange and imported them in this project as Exchange modules.
- Followed naming conventions.
- Encrypted properties using secure properties dependency module.
- Maintained different property files for each environment for easy deployments in higher environments.
- Used API Autodiscovery to download policies from Anypoint Platform.
- Followed Best Practices while developing the APIs like keeping all global configurations in a file, global error handling, standard JSON format logging, logging correlationId for errors and logs.

# API Details


/{version}/about
GET
	To do the health check on the API
/{version}/cities/{country}
GET
Get city names for a country by passing country name as URI parameter.
/{version}/weather
GET
Get weather details for a city/country by passing city/country name as query parameter.


# MUnit Tests

MUnit tests are written to cover the possible success and error scenarios.

# Logging

Standard logging in JSON format and also logged correlationId to track a transaction..


# Error Handling 

If any error occurs in the application, global error handler handles the error and gives a standard error response with error details and correlationId.


# Challenges faced
There was a small challenge,as the API was down. So, installed Docker to run the SOAP Service in a container. 
Another challenge was dealing with CDATA from SOAP Service response. Apart from this, everything went well. 


# Design decision
We followed API LED Connectivity model and designed a System API as we are connecting to an external SOAP service.The response format is JSON as it is easy to parse and play with JSON.
