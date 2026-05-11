# interfaces_hub

A repository of Peppy **conformance interfaces** (`peppy_schema: "interface_v1"`).

An interface declares the topics, services, and actions a node must expose to "conform" to it. Nodes set `manifest.conforms_to` in their `peppy.json5` to claim an interface; subscribers depend on the interface rather than on a specific node, so any conforming implementation can satisfy them.

## Adding an interface

Create a new `.json5` file under the relevant category:

```json5
{
  peppy_schema: "interface_v1",
  manifest: { name: "<interface_name>", tag: "<semver>" },
  interfaces: {
    topics:   [ /* ... */ ],
    services: [ /* ... */ ],
    actions:  [ /* ... */ ],
  }
}
```

## Use

This repo is consumed by `peppy repo update` alongside node and launcher repositories.
