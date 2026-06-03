# Redocly configuration file

You can configure all of your Redocly tools using a single `redocly.yaml` configuration file in the root of your project. Your `redocly.yaml` configurations can be used locally, in CI, or on our hosted platforms to specify the following behaviors:

- The rules to apply to your APIs and how strictly to `lint`.
- The styles and features to use when rendering your API documentation.
- Project-aware configuration for the VSCode extension.


Redocly CLI searches for the file in the local directory, or you can specify a configuration file with your command.

Our starter projects like `openapi-starter` include the file for you to edit.

## Example Redocly configuration file

An example is worth a thousand words, or so they say. Here's a simple configuration file showing some of the options available and how to use them.


```yaml
extends:
  - recommended

apis:
  core@v2:
    root: ./openapi/openapi.yaml
    rules:
      no-ambiguous-paths: error
  external@v1:
    root: ./openapi/external.yaml
    openapi:
      hideLoading: true

openapi:
  schemasExpansionLevel: 2
  showExtensions: true
```

Read on to learn more about the various configuration sections and what you can do with each one.

## Using configuration with Redocly CLI

Some of the Redocly CLI commands, such as the [lint command](/docs/cli/commands/lint), use the API names from the `apis` object as shortcuts for referencing API descriptions.
You can tell the `lint` command to validate specific API descriptions by using their names from the `apis` object, like in the following example:


```shell
redocly lint core@v2
```

On the other hand, if you run the command without specifying any aliases, it applies to all API descriptions listed in the `apis` object of the configuration file.


```shell
redocly lint
```

This runs the `lint` command for every API defined in the configuration file.

## Configuration file overview

Learn about the various sections of the config file, and follow the links for detailed documentation for each.



### Expand existing configuration with `extends`

Use `extends` to adopt an existing [ruleset](/docs/cli/rules#rulesets) such as the `recommended` or `minimal` standards.
You can also define your own rulesets and refer to them here by file path or URL.

While the order of the sections in the configuration file doesn't matter, usually `extends` is first, and any later rules, preprocessors or decorators defined in this file then override the base settings.

Read the [detailed `extends` documentation](/docs/cli/configuration/extends) to see more information and examples.

### Configure linting `rules`

In the `rules` section, configure which rules apply, their severity levels, and any options that they support.
Configurable rules, and rules from custom plugins are also configured here.

Use this section to adjust the linting rules from the rulesets or other base configuration set in `extends`, and fine-tune it to meet the needs of your API. Here's an example `redocly.yaml`, changing some rule severity, and using some additional configuration for a rule.


```yaml
rules:
  no-unused-components: error
  operation-singular-tag: warn
  boolean-parameter-prefixes:
    severity: error
    prefixes: ['can', 'is', 'has']
```

You can also define your [configurable rules](/docs/cli/rules/configurable-rules) here.

For more information and examples, visit the [configuring rules documentation](/docs/cli/configuration/rules).



### Configure OpenAPI features and documentation styles

#### mockServer object

You can apply `mockServer` to individual APIs as well as at the root (default) level.
In case of conflict, API takes priority.

The API registry supports [the mock server feature](https://redocly.com/docs/api-registry/guides/mock-server-quickstart/) and allows project owners to enable it for all branches per API version.
When the mock server is enabled for an API, you can send test requests to it from any API client.

The `mockServer` object allows additional configuration of the mock server behavior.
This object is optional.

#### Fixed properties


```json
{
  "$ref": "#/components/schemas/mockserver",
  "components": {
    "schemas": {
      "mockserver": {
        "type": "object",
        "title": "Mock server object",
        "description": "Lets you toggle features that control how mock servers behave.",
        "properties": {
          "errorIfForcedExampleNotFound": {
            "description": "You can force specific examples to appear in the response by adding the optional `x-redocly-response-body-example` header to your requests. If you pass an example ID that can't be found in the API description, the mock server returns any other example unless `errorIfForcedExampleNotFound` is `true`. Then the mock server returns an error instead.",
            "type": "boolean",
            "default": false
          },
          "strictExamples": {
            "description": "By default, the mock server automatically enhances responses with heuristics, such as substituting response fields with request parameter values. If set as `true`, examples are returned in the response unmodified, and exactly how they are described in the OpenAPI description.",
            "type": "boolean",
            "default": false
          }
        }
      }
    }
  }
}
```

#### openapi object

The `openapi` object configures features and theming for API documentation generated from OpenAPI descriptions.

If you need to apply different theming and functionality to individual APIs, add the `openapi` property to the appropriate API in the `apis` object, and use the same options as the global `openapi` object.

Find the full list of supported options on the [Reference docs configuration page](https://redocly.com/docs/api-reference-docs/configuration/functionality/).



### Configure each of the `apis` independently

For organizations with multiple APIs, versions or environments, having specific configuration for each is a powerful tool.
All configuration options can be nested within a specific API entry.

#### Example of `apis` configuration


```yaml
extends:
  - recommended

apis:
  public@v2:
    root: ./openapi/openapi.yaml
    rules:
      operation-4xx-response: off
  internal@v1:
    root: ./internal-openapi/openapi.yaml
    rules:
      security-defined: off
      operation-4xx-response: off
    decorators:
      remove-x-internal: on
```

Visit the [per-API configuration page](/docs/cli/configuration/apis) for detailed documentation and more examples.



### Use custom `plugins`

Use this list to import any custom plugins (omit this section if you have no plugins). Custom plugins are used to add any custom decorators or rules that you want to use, that aren't provided by the Redocly [built-in rules](/docs/cli/rules/built-in-rules), [configurable rules](/docs/cli/rules/configurable-rules), or existing [decorators](/docs/cli/decorators).

Add each plugin by path, relative to the configuration file, to have the plugin contents available to configure.
Importing by URL isn't supported, to reduce the risk of malicious code execution.

Find more information on the [configuration in plugins](/docs/cli/custom-plugins/custom-config) page.

#### Plugin import example

Use the `plugins` section to import as many plugins as you need to refer to in your config file.


```yaml
plugins:
  - './local-plugin.js'
  - './another-local-plugin.js'
```

The rules, decorators, pre-processors and configuration contained in the plugins become available to your configuration file.



### Resolve non-public or non-remote URLs

Redocly automatically resolves any API registry link or public URL in your API descriptions.
If you want to resolve links that are neither API registry links nor publicly accessible, set the `resolve` object in your configuration file.

Redocly CLI supports one `http` header per URL.

#### Fixed properties


```json
{
  "$ref": "#/components/schemas/resolve",
  "components": {
    "schemas": {
      "resolve": {
        "type": "object",
        "title": "Resolve object",
        "description": "All API registry links and public URLs in your API descriptions automatically resolve. If you want to resolve links that are neither API registry links nor publicly accessible, include this object to add an HTTP request header.\nIf the URL matches multiple patterns, the first match takes priority. The header from the first match is used in the request.\nUse environment variables where possible.",
        "properties": {
          "doNotResolveExamples": {
            "type": "boolean",
            "description": "Set this option to `true` to prevent resolving `$ref` fields in singular `example` properties. This affects both `lint` and `bundle` commands. This does not affect `$ref` resolution in other parts of the API description.",
            "default": false
          },
          "http": {
            "type": "object",
            "description": "Description of URL pattern matches and the corresponding headers to use when resolving references.",
            "properties": {
              "headers": {
                "type": "array",
                "minItems": 1,
                "items": {
                  "type": "object",
                  "required": [
                    "matches",
                    "name"
                  ],
                  "properties": {
                    "matches": {
                      "type": "string",
                      "description": "The URL pattern to match. For example, `https://api.example.com/v2/**` or `https://example.com/*/test.yaml`"
                    },
                    "name": {
                      "type": "string",
                      "description": "The header name. For example, `X-API-KEY`."
                    },
                    "value": {
                      "type": "string",
                      "description": "The value of the header. Mutually exclusive with `envVariable`. We recommend to use `envVariable` instead for any secrets."
                    },
                    "envVariable": {
                      "type": "string",
                      "description": "The environment variable name resolved which should contain the value. Mutually exclusive with `value`."
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

#### Example

Here is an example for adding header definitions:


```yml
resolve:
  http:
    headers:
      - matches: https://api.Aexample.com/v2/**
        name: X-API-KEY
        envVariable: SECRET_KEY
      - matches: https://example.com/*/test.yaml
        name: Authorization
        envVariable: SECRET_AUTH
```

The first match takes priority when a URL matches multiple patterns.
Therefore, only the header from the first match is used in the request.

### Split up the configuration file

As your config file grows, you may want to split it into multiple parts.
Splitting a config file is possible by using references in a config similar to how they are used in OpenAPI descriptions:


```yaml
extends:
  - recommended
openapi:
  $ref: ./openapi-theme.yaml
mockServer:
  $ref: ./mockserver.yaml
```

When using the `push` command with a config file that includes `$ref`s, all referenced files are explicitly uploaded using the `--files` option.
