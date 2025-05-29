# Mollie's OpenAPI Specification
This repository contains the [OpenAPI specifications](https://www.openapis.org/) for Mollie's API.

Check out the [API Reference](https://docs.mollie.com/reference/overview) for the latest, up-to-date documentation of our API.

## Files
- `specs.yaml`: OpenAPI 3.1 spec matching Mollie's Public API.

## Extensions
The specification contains a few fields that help us present the information in ways that are difficult in OpenAPI by default.

#### `x-enumDescriptions`
It helps us display a table in the documention page where the descriptions will be added for each of the `enum` options.

```yaml
type: string
enum:
  - EUR
  - GBP
x-enumDescriptions:
  EUR: Euro
  GBP: British Pound
```

#### `x-readme`
It allows us to choose which code snippets are initially shown to the users in the documentation page.

```yaml
x-readme:
  code-samples:
    - language: shell
      code: ...
    - language: php
      code: ...
    - language: node
      code: ...
    - language: python
      code: ...
    - language: ruby
      code: ...
```

## Custom Extensions
#### `x-request`
This field allows us to specify a particular request and tie it to a response. It can be helpful when creating a new example for the Postman Collections.

```yaml
responses:
  ...
  examples:
    create-payment-example:
      summary: ...
      x-request: requests.yaml#/create-payment-example
      value:
        ...
```
