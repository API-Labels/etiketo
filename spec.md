# Etiketo API Label Format Specification

This is the *etiketo API Label Format specification* for representing sets of API labels in a JSON-based representation. An etiketo document contains labels for one API. Labels are either *values* or *links*. Value labels are either strings or sets of strings. Link labels are either URIs or sets of URIs. Both value and link labels can use either registered or extension types.

Here is a simple example of an etiketo document, which assigns a `title` to the API (using a value label), and identifies the API it describes (using a link label):

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

Etiketo documents are JSON objects containing a `labels` and/or a `links` member. The API labels represented in an etiketo document is the combination of the value labels (listed in the `labels` member) and the link labels (listed in the `links` member).


## Etiketo Value Labels

In an etiketo document, the `labels` member is an object that contains all value labels as members. Each member in the `labels` object constitutes an API value label. Value labels are either strings or sets of strings.

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

In an etiketo document, the `links` member is an object that contains all link labels as members. Each member in the `links` object constitutes an API link label. Link label values are either URIs or sets of URIs, where URIs are represented by a JSON string and sets of URIs are represented by a JSON array of strings.

Etiketo link labels generally follow the model established by [RFC 8288 (Web Linking)](https://tools.ietf.org/html/rfc8288). This model assumes that links are using link relations, and that each link therefore is a typed reference to the URI it is linking to.


### Types of Link Labels

As defined by RFC 8288, link relation types can be either registered, or they can be extension link relation types. Registered link relation types are identified by simple strings, and the registered link relation types can be found in the [link relation type registry maintained by IANA](https://www.iana.org/assignments/link-relations/link-relations.xhtml).

Extension link relation types, on the other hand, are identified by URI. This makes it easier to avoid name clashes in decentralized scenarios where services are inventing and using their own link relation types. It also makes it possible (though this is not required) to use URIs that can be dereferenced and then provide documentation about their meaning.

Etiketo uses the model established by RFC 8288 for its link labels, and uses the same model (i.e., a registry for simple types and URIs for naming extension types) for its value labels. This means that both value and link label types work in the same way.


### Value Range of Link Labels

Link labels are typed Web links. Their type is established through their name, which identifies link relation types in accordance with [RFC 8288 (Web Linking)](https://tools.ietf.org/html/rfc8288). In the same way as RFC 8288 allows links to have multiple targets, this is also allowed for etiketo link labels.


## API Value Label Type Registry

Value labels can have one of two types of names: They can be simple strings, in which case they are interpreted as registered value labels. Alternatively, they can be URIs, in which case they are interpreted as extension labels.

Registered label types are supposed to use names that are registered in the [API label type registry](https://github.com/API-Labels/registry). This specification registers the following label types:

- `tags` (set of strings): A set of tags that are used to describe the API. Each string in the set of strings represents one individual tag.
- `title` (string): A human-readable title of the described API.
- `version` (string): The version identifier of the described API.


## Examples

...


## API Label Discovery

[[ see issue #1 for now. ]]
