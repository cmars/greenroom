# greenroom

> What is this all about now?

Rendering godocs for Backstage TechDocs documentation.

greenroom renders [Godoc](https://go.dev/blog/godoc) comments into
documentation that can be consumed and rendered into Backstage using its
[TechDocs plugin](https://backstage.io/docs/features/techdocs/creating-and-publishing).
TechDocs expects a [Mkdocs](https://www.mkdocs.org/) project documentation
configuration and layout.

> Why would I want to do that?

This makes it easy to upload your Go libraries' code documentation up into
Backstage.

It's not really that useful for public Go packages; just link to
[pkg.go.dev](https://pkg.go.dev) for that. It'll be primarily useful for
distributing internal Go packages within an organization that is using
Backstage as an internal catalog of all the technical things.

> How do I install it?

    go install github.com/cmars/greenroom@latest

> How do I run it?

In your Go module,

    greenroom ./...

will create Markdown documentation for each package matching the query `./...`
in a `docs` subdirectory, and a `mkdocs.yml` that references all of it.

`greenroom -help` for more options.

> How does it work?

[github.com/princjef/gomarkdoc](https://github.com/princjef/gomarkdoc) is doing
almost all of the real work, by rendering all the godocs into Markdown. Other
than that its just a bit of Go package introspection, YAML wrangling and
shuffling files around.
