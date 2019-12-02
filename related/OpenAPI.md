# [OpenAPI](https://github.com/OAI/OpenAPI-Specification)

## [OpenAPI Object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#oasObject)

The [OpenAPI object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#oasObject)  is the root document object of an OpenAPI document. Some of its members are relevant for providing metadata for an API.

- info (Info Object; see below) REQUIRED: Provides metadata about the API. The metadata MAY be used by tooling as required.
- tags (Tag Object): A list of tags used by the specification with additional metadata. The order of the tags can be used to reflect on their order by the parsing tools. Not all tags that are used by the Operation Object must be declared. The tags that are not declared MAY be organized randomly or based on the tools' logic. Each tag name in the list MUST be unique.
- externalDocs (External Documentation Object): Additional external documentation.

## [OpenAPI Info Object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#info-object)

The [OpenAPI Info object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#info-object) is a required member of the [OpenAPI object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md#oasObject).

- title (string) REQUIRED: The title of the application.
- description (string): A short description of the application. CommonMark syntax MAY be used for rich text representation.
- termsOfService (string): A URL to the Terms of Service for the API. MUST be in the format of a URL.
- contact (Contact Object): The contact information for the exposed API.
- license (License Object): The license information for the exposed API.
- version (string) REQUIRED: The version of the OpenAPI document (which is distinct from the OpenAPI Specification version or the API implementation version).
