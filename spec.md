# Etiketo API Label Format Specification

This is the *Etiketo API Label Format specification* for representing sets of API labels in a JSON-based representation. An Etiketo document contains labels for one API. Labels are either *values* or *links*. Value labels are either strings or sets of strings. Link labels are either URIs or sets of URIs. Both value and link labels can use either registered or extension types.

Here is a simple example of an Etiketo document, which assigns a `title` to the API (using a value label), and identifies the API it describes (using a link label):

```json
{
  "labels": {
    "title": "Example API",
  },
  "links": {
    "describes": "http://example.com/API"
  }
}
```

Etiketo documents are JSON objects containing a `labels` and/or a `links` member. The API labels represented in an Etiketo document is the combination of the value labels (listed in the `labels` member) and the link labels (listed in the `links` member).


## Etiketo Value Labels

In an Etiketo document, the `labels` member is an object that contains all value labels as members. Each member in the `labels` object constitutes an API value label. Value labels are either strings or sets of strings.

Any member of the `labels` object where the member value is neither a string nor an array of strings MUST be ignored and does not constitute an API value label.

Each member representing a value label consists of a name and a value. The name represents the name of the API value label. The value (which is a string or an array of strings) represents the value of the API value label. 


### Types of Value Labels

Value label names can either be simple strings, in which case they represent registered label value types, or URIs, in which case they represent extension label value types. This naming model is derived from the naming model of link relation types established by [RFC 8288 (Web Linking)](https://tools.ietf.org/html/rfc8288).

The ABNF for value label names is as follows (using the definition from [RFC 8288](https://tools.ietf.org/html/rfc8288)):

```ABNF
label-name      = reg-label-name / ext-label-name
reg-label-name  = LOALPHA *( LOALPHA / DIGIT / "." / "-" )
ext-label-name  = URI ; Section 3 of [RFC3986]
```

The registered label types that can be used for value labels can be found in the [API label type registry](https://github.com/API-Labels/registry) as described in the registry section below.


### Value Range of Value Labels

Each value label is identified by a type (as described above) and has a value. Value labels can have two types of values, either single strings, or sets of strings. If a value label has a value of a single string, this is represented as a JSON string.  If a value label has a value of a set of strings, this is represented as a JSON array of strings.

Label types SHOULD indicate whether their value is supposed to be a single string, or a set of strings. If the representation of a value label does not match the way the label type is specified, applications MAY ignore the label.


## Etiketo Link Labels

In an Etiketo document, the `links` member is an object that contains all link labels as members. Each member in the `links` object constitutes an API link label. Link labels are either URIs or sets of URIs.

Etiketo link labels generally follow the model established by [RFC 8288 (Web Linking)](https://tools.ietf.org/html/rfc8288).


### Types of Link Labels

The registered link relation types that can be used for link labels can be found in the [link relation type registry maintained by IANA](https://www.iana.org/assignments/link-relations/link-relations.xhtml).


### Value Range of Link Labels

Link labels are typed Web links. Their type is established through their name, which identifies link relation types in accordance with [RFC 8288 (Web Linking)](https://tools.ietf.org/html/rfc8288). In the same way as RFC 8288 allows links to have multiple targets, this is also allowed for Etiketo link labels.


## API Label Type Registry

Value labels can have one of two types of names: They can be simple strings, in which case they are interpreted as registered value labels. Alternatively, they can be URIs, in which case they are interpreted as extension labels.

Registered label types are supposed to use names that are registered in the [API label type registry](https://github.com/API-Labels/registry). This specification registers the following label types:

- `tags` (set of strings): A set of tags that are used to describe the API. Each string in the set of strings represents one individual tag.
- `title` (string): A human-readable title of the described API.
- `version` (string): The version identifier of the described API.


## Examples

...


## API Label Discovery

[[ see issue #1 for now. ]]
