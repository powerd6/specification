# Schemas

## Table of Contents
<!-- toc -->
---

## Module

**Download:** [json-schema file](./module.json)

**Example:**

```json
{
  "title": "generic-spells",
  "description": "A collection of simple spells for the powerd6 system.",
  "source": "https://github.com/sample-user/generic-spells",
  "types": [
    {
      "id": "spell",
      "description": "Arcane or mystical arts that can be used inside or outside combat.",
      "schema": {
        "properties": {
          "name": {
            "description": "The name of the spell.",
            "type": "string"
          },
          "recovery": {
            "description": "How many turns must be passed before using the spell again.",
            "type": "number"
          },
          "effect": {
            "description": "The effect that is executed when the spell is used.",
            "type": "string"
          }
        },
        "required": [
          "name",
          "recovery",
          "effect"
        ]
      },
      "rendering": {
        "txt": "${name}:\n(Recovery ${recovery})\n${effect}",
        "md": "# ${name}\n> Recovery ${recovery}\n\n${effect}"
      }
    }
  ],
  "content": [
    {
      "id": "fireball",
      "type": "spell",
      "name": "Fireball",
      "recovery": 2,
      "effect": "Create an orb of flames that can be thrown with magical energy."
    }
  ]
}
```

## Type

**Download:** [json-schema file](./type.json)

**Example:**

```json
{
  "id": "spell",
  "description": "Arcane or mystical arts that can be used inside or outside combat.",
  "schema": {
    "properties": {
      "name": {
        "description": "The name of the spell.",
        "type": "string"
      },
      "recovery": {
        "description": "How many turns must be passed before using the spell again.",
        "type": "number"
      },
      "effect": {
        "description": "The effect that is executed when the spell is used.",
        "type": "string"
      },
      "icon": {
        "description": "The icon that represents the spell.",
        "oneOf": [
          {
            "type": "string",
            "format": "uri"
          },
          {
            "type": "string",
            "contentEncoding": "base64",
            "contentMediaType": "image/png"
          }
        ]
      }
    },
    "required": [
      "name",
      "recovery",
      "effect"
    ]
  },
  "rendering": {
    "txt": "${name}:\n(Recovery ${recovery})\n${effect}",
    "md": "# ${name}\n![](${icon})\n> Recovery ${recovery}\n\n${effect}"
  }
}
```