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

> How does it work?

[github.com/princjef/gomarkdoc](https://github.com/princjef/gomarkdoc) is doing
almost all of the real work, by rendering all the godocs into Markdown. Other
than that its just a bit of Go package introspection, YAML wrangling and
shuffling files around.
