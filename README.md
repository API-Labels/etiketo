# API Label Format

This is the *API Label Format specification* for representing sets of API labels in a JSON-based representation. An API label document contains labels for one API. Labels are either *values* or *links*. Value labels are either strings or sets of strings. Link labels are either URIs or sets of URIs. Both value and link labels can use either registered or extension types.

Here is a simple example of an API label document, which identifies the API it describes, and uses a `title` label with a string value:

```javascript
{
  "labels": {
    "title": "Example API",
  },
  "links": {
    "describes": "http://example.com/API"
  }
}
```

API label documents are JSON objects containing a `labels` and/or a `links` member.


## API Labels: Value Labels

### Types of Value Labels

The registered label types that can be used for value labels can be found in the [API label type registry](https://github.com/API-Labels/label-registry).


### Value Range of Value Labels

## API Labels: Link Labels

the model established by [RFC 8288 (Web Linking)](https://tools.ietf.org/html/rfc8288)

### Types of Link Labels

The registered link relation types that can be used for link labels can be found in the [link relation type registry maintained by IANA](https://www.iana.org/assignments/link-relations/link-relations.xhtml).


### Value Range of Value Labels

