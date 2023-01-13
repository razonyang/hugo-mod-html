# Hugo HTML Module

This module ships with several partials and shortcodes for you to write HTML in Markdown.

## Installation

```toml
[[module.imports]]
path = "github.com/razonyang/hugo-mod-html"
```

## Shortcodes

Similar to HTML, there are two types of shortcodes:

- Void shortcode: cannot have any child nodes.
- Tag (non-void) shortcode.

### `html/_void`

> Void shortcode.

```go
{{< html/_void _name={tag} name=value >}}
```

- `_name` is a reserved parameter for specifying the tag name.

```go
{{< html/_void _name=hr >}}

{{< html/_void _name=hr style="border: 2px solid blue;" >}}

{{< html/_void _name=input type=password placeholder="Password" >}}

{{< html/_void _name=input disabled="" >}}
```

### `html/_tag`

> Tag (non-void) shortcode.

```go
{{< html/_tag _name={tag} name=value >}}
...
{{< /html/_tag >}}
```

- `_name` is a reserved parameter for specifying the tag name.

```go
{{< html/_tag _name=a href="https://github.com/razonyang/hugo-mod-html" target="_blank" >}}Repository{{< /html/_tag >}}

{{< html/_tag _name=span >}}Text{{< /html/_tag >}}

{{< html/_tag _name=button >}}
{{< html/_tag _name=span >}}Text inside button{{< /html/_tag >}}
{{< /html/_tag >}}
```
