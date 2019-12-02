# [OpenAPI](https://github.com/OAI/OpenAPI-Specification)

## [OpenAPI `info` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#info-object)

The [OpenAPI `info` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#info-object) is a required member of the [OpenAPI root document object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#oasObject)

- title (string) REQUIRED: The title of the application.
- description (string): A short description of the application. CommonMark syntax MAY be used for rich text representation.
- termsOfService (string): A URL to the Terms of Service for the API. MUST be in the format of a URL.
- contact (Contact Object): The contact information for the exposed API.
- license (License Object): The license information for the exposed API.
- version (string) REQUIRED: The version of the OpenAPI document (which is distinct from the OpenAPI Specification version or the API implementation version).
