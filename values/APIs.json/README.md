# Etiketo Support for [APIs.json](http://apisjson.org/)

Etiketo supports value labels and link labels. In order to represent APIs.json metadata (as defined in the [0.15 version of the APIs.json format](http://apisjson.org/format/apisjson_0.15.txt)), the following etiketo value label types are defined for compatibility with APIs.json:

* `http://etiketo.org/values/APIs.json/#name`: Name of the API
* `http://etiketo.org/values/APIs.json/#description`: Human readable text description of the API.
* `http://etiketo.org/values/APIs.json/#image`: URL of an image which can be used as an "icon" for the API if displayed by a search engine.
* `http://etiketo.org/values/APIs.json/#humanUrl`: Web URL corresponding to human readable information about the API. 
* `http://etiketo.org/values/APIs.json/#baseUrl`: Web URL corresponding to the root URL of the API or primary endpoint.
* `http://etiketo.org/values/APIs.json/#version`: String representing the version number of the API this description refers to. 
* `http://etiketo.org/values/APIs.json/#tags`: A list of descriptive strings which identify the API; as an array. 
* `http://etiketo.org/values/APIs.json/#properties` (collection): type: please see reserved keywords below; url or value.
  * Swagger
  * RAML
  * Blueprint
  * WADL
  * WSDL
  * TermsOfService
  * InterfaceLicense
  * StatusPage
  * Pricing
  * Forums
  * AlertsTwitterHandle
* `http://etiketo.org/values/APIs.json/#contact` (collection): Any vCard Element
