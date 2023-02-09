# 2. Merge json modules

Date: 2023-01-29

## Status

Accepted

## Context

There are multiple possible options to handle module combination.

While a custom implementation specifically for powerd6 would be possible, it would require significant effort to implement and document, therefore, custom merge mechanism will not be used.

By relying on the transport mechanism for the modules, JSON, we can leverage well-known patterns, like:

- [Json Patch](https://jsonpatch.com/)
- [JSON Merge Patch](https://www.rfc-editor.org/rfc/rfc7396)

The main difference between them is how JSON is used to signifiy changes to an original document. The Patch mechanism can be seen as a list of changes, while the Merge-Patch can be seen as a complete valid object that needs to interact with the existing object.

In reality, both allow for the same end-goals, but the nature of the json-patch means that module would need to be compiled into jsonPatches before being merged. [This article](https://erosb.github.io/post/json-patch-vs-merge-patch/) goes into more depth on the subject matter.

## Decision

The chosen mechanism for combining modules is JSON Merge Patch.

## Consequences

The existing schemas must replace all usage of arrays with maps, since Merge Patch is unable to operate on arrays in the intuitive way.