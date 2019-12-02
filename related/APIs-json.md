# APIs.json

The following information is taken from the [0.15 version of the APIs.json format](http://apisjson.org/format/apisjson_0.15.txt).

APIs.json supports describing "sets of APIs", with some metadata being specified at the APIs.json document level, and additional metadata being specified for each listed API in that document individually.

## APIs.json General Fields

* Name [Mandatory]: text string of human readable name for the collection of APIs
* Description [Mandatory]: text human readable description of the collection of APIs
* Image [Optional]: Web URL leading to an image to be used to represent the collection of APIs defined in this file
* Url [Mandatory]: Web URL indicating the location of the latest version of this file
* Tags (collection) Optional]: this is a list of descriptive strings which identify the contents of the APIs.json file; represented as an array. 
* Created [Mandatory]: date of creation of the file
* Modified [Mandatory]: date of last modification of the file
* specificationVersion [Mandatory]: version of the APIs.json specification in use

## APIs.json API-level Fields

* Name [Mandatory]: name of the API
* Description [Mandatory]: human readable text description of the API.
* Image [Optional]: URL of an image which can be used as an "icon" for the API if displayed by a search engine.
* humanUrl: Web URL corresponding to human readable information about the API. 
* baseUrl: Web URL corresponding to the root URL of the API or primary endpoint.
* Version [Optional]: String representing the version number of the API this description refers to. 
* Tags: (collection) [Optional]: this is a list of descriptive strings which identify the API; as an array. 
* properties (collection): type: please see reserved keywords below; url or value.
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
* contact (collection): Any vCard Element
