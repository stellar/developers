# Stellar Developers
Stellar developer portal site generator.

This uses gulp and metalsmith (plus a heap of plugins) to generate the site.

## Installation
```bash
git clone https://github.com/stellar/developers # or git@github.com:stellar/developers.git
npm install:w

```

## Development
To generate the static site, run the following inside your repo containing this folder:
```bash
node_modules/.bin/gulp develop # or just `gulp` if you have it installed globally or have path set up
```

That will compile the code and start a up test webserver to view the generated site. It will also watch for edits (to content) and automatically build when needed.

By default, the site is served under the developers/ subfolder. This is to reduce the amount of bugs when this site is deployed to https://www.stellar.org/developers/. This can be changed by passing a custom baseUrl to the gulp build task like so: `gulp develop --baseUrl="/"` or `gulp build --baseUrl="/"`.

## Development conventions
- Use yaml especially for front matter since Github can nicely display markdown files with this
- 2 spaces everywhere

### Writing Examples

The developer portal for stellar includes a system for displaying code-samples alongside the documentation for horizon endpoints. To recognize and process these examples, you must write them in a particular way:

1.  Any markdown (.md) file in a project that has a path prefix of `/docs/horizon-examples` will be considered to be an example file.
2.  The example file must include a `language` attribute in it's front matter.  Valid values for this attribute are `curl`, `ruby`, `javascript`, and `go`
3.  The file's basename must match the basename of the horizon endpoint to which it is associated.  For example `docs/horizon-examples/accounts-all.md` will be associated with the "accounts-all" horizon endpoint. 

By following the rules above, your example file should get recognized by the build pipeline and slotted into the appropriate output file.

## Contributing
Please read the [contributing guide](CONTRIBUTING.md) to learn more about how to contribute to the developer portal. For contributions to docs, please put contributions in their respective repositories.

## License
This project is licensed under Apache License Version 2.0. For more information, refer to the [LICENSE.txt](LICENSE.txt) file.
