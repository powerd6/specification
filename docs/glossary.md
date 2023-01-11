# Glossary

This is an opinionated glossary for the terms used by the powerd6 team.

## Table of Contents
<!-- toc -->
---

## Module

A module is a document that contains information detailing and explaining rules and/or content, meant to be used for [rendering](#render).

Modules can be combined and merged into (larger) modules.

## Render

A render is the output of any process that receives a module and returns a human-readable format.

> Books, PDF documents and web-pages are examples of Renderers.

## Type

The aggregation of properties, their value-types and their [rendering](#render) rules is called a Type.

[Modules](#module) can define custom types for the content contained inside of them.

> A "Spell" could be defined as a type with:
> - mandatory fields "name", "cost", "effect"
> - non-mandatory field "icon"
> 
> Optionally, a rendering rule could be defined to display the information next to the icon in `html`, but not in `txt` renders.