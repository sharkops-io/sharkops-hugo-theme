# sharkops-hugo-theme

A small [Hugo](https://gohugo.io) theme for a blog with posts and author pages,
built on the [VMware Clarity](https://clarity.design) CSS. It powered the
original sharkops.io site.

## Use it

As a Hugo module:

```toml
# hugo.toml
[module]
  [[module.imports]]
    path = "github.com/sharkops-io/sharkops-hugo-theme"
```

Or as a git submodule:

```sh
git submodule add https://github.com/sharkops-io/sharkops-hugo-theme themes/sharkops
echo 'theme = "sharkops"' >> hugo.toml
```

Needs Hugo 0.63.0 or newer.

## Content it expects

| Where | Field | Used for |
|---|---|---|
| site params | `dateFormat` | Go date layout for post dates (default `Jan 2, 2006`) |
| post front matter | `type: post` | The home page lists the three newest pages of this type |
| post front matter | `author: {key, name}` | Byline, linked to `/authors/<key>` |
| `content/authors/<key>.md` | `me: <key>` | Lists that author's ten newest posts |
| `content/authors/<key>.md` | `links: [...]` | Links shown on the author page |

The `extlink` shortcode opens a link in a new tab:

```
{{< extlink href="https://example.com" title="Example" >}}
```

## Layout

- `layouts/_default/` base, list, single and page templates
- `layouts/authors/` author index and author pages
- `layouts/partials/` head, header, footer, article list, metadata, pagination
- `static/css/main.css` the theme's own styles; `clr-ui` and `clr-icons` are
  Clarity 4.0.6, vendored unchanged

## License

Apache License 2.0. See [LICENSE](LICENSE).

The vendored Clarity stylesheets in `static/css/clr-*.min.css` are
Copyright VMware, Inc. and remain under the MIT license stated in their
headers.
