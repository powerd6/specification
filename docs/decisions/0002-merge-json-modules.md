# 2. Merge json modules

Date: 2023-01-29

## Status

Accepted

## Context

There are multiple possible options to handle module combination.

While a custom implementation specifically for powerd6 would be possible, it would require significant effort to implement and document, therefore, custom merge mechanism will not be used.

By relying on the transport mechanism for the modules, JSON, we can leverage well-known patterns, like:

- json patch
- json merge patch

<!--
TODO: review https://erosb.github.io/post/json-patch-vs-merge-patch/ for options,
consider changing json-schema to support merge-patch
(arrays are unsupported, dictionaries must be used instead.)
-->

## Decision

The change that we're proposing or have agreed to implement.

## Consequences

What becomes easier or more difficult to do and any risks introduced by the change that will need to be mitigated.
