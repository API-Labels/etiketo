# Label Format

This is the *Label Format specification* for representing sets of labels in a JSON-based representation. Labels can used for different purposes, and the format provides a way to separate and group labels. Groups carry names, which can be registered or extension names.

Each *registered group of labels* is represented by a *top-level folder in this repository*, with the folder name representing the group name. Names are strings containing ASCII characters, numbers, and hyphens. They must be treated as being case-insensitive.

*Extension names* are URIs to avoid name clashes between privately used groups of labels.

A label document is a single JSON object containing a single `labels` member. The `label` member is a set of one or more members, with each member being identified by the group name.

```
{ "labels": {
    "API": {
      "version": "1.3.42",
      "SPDX-license": "ADSL",
      "http://example.com/privatelabeltype": "some label value"
}}}
```

Each group contains a set of labels. Each label is a member with the label type as the member name, and the label value as the member value. It is up to the label group to define the allowed label types.
