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
