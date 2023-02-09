# Glossary

This is an opinionated glossary for the terms used by the powerd6 team.

## Table of Contents
<!-- toc -->
---

## Module

A module is a document that contains information detailing and explaining rules and/or content, meant to be used for [rendering](#render).

Modules can be combined into (larger) modules.

Schema documentation is available [here](schemas/_index.md#module).

## Render

A render is the output of any process that receives a module and returns a human-readable format, based on the templates defined by the [types](#type) inside the module.

> Books, PDF documents and web-pages are possible rendering targets.

## Type

The aggregation of properties, their value-types and their [rendering](#render) rules is called a Type.

[Modules](#module) define custom types for the content contained inside of them.

> **Example**:
> 
> A "Spell" could be defined as a type with:
> - mandatory fields "name", "cost", "effect"
> - non-mandatory field "icon"
> 
> Optionally, a rendering rule could be defined to display the information next to the icon in `html`, but not in `txt` renders.

Schema documentation is available [here](schemas/_index.md#type).
