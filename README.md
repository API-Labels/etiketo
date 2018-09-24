# Label Format

This is the *Label Format specification* for representing sets of labels in a JSON-based representation. Labels can used for different purposes, and the format provides a way to separate and group labels. Groups carry names, which can be registered or extension names.

Each *registered group of labels* is represented by a *top-level folder in this repository*, with the folder name representing the group name. Names are strings containing ASCII characters, numbers, and hyphens. They must be treated as being case-insensitive.

*Extension names* are URIs to avoid name clashes between privately used groups of labels.
