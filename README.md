# the Pantsu.cat developer team TODO list

## pantsu/pomf

### Release `2.0.3`

- Replace potentially non-free `UploadException.class.php`
- Fix abbreviation of `<3` in `check_fileapi.swig`

### Release `2.1.0`

**Note:** No more new or changed features into this release, please. I don't
want the size of this release to grow too uncomfortable with the workload we're
facing in here.

- Clean up CSS
  - Use CSSLint for example, but don't blindly follow it
  - Related: Replace `#upload-btn` with `.js-upload-btn` or HTML data attributes
    (`[data-js="upload-btn"]` or similar) to be explicit it has no styles
    - Downside of using data attributes: it's fucking slow. But it will get
      better as JavaScript engines get optimized.
    - Using data attributes would seperate JS and CSS.
    - `.js-*` classes are never guaranteed to not to be touched by browsers, and
      not exactly what WHATWG wants to suggest for scripting (WHATWG HTML
      Standard, 1.7.3 Extensibility).
  - Use flexbox
  - <http://philipwalton.com/articles/css-architecture/>
  - Rearchitecture styles into base stylesheets (`layout.css`), components
    (`alerts.css`, `buttons.css`, `nav.css`) and modules (`header.css`,
    `footer.css`), then integrate into build system for concatenation
  - Deprecate or remove unused selectors like `.jumbotron .btn.drop`
- Clean up and refactor Luminarys' new JavaScript
  - Finish writing up JSDoc comments (`luminarys/refactor-js-pu`)
  - Reimplement `no-file-api`
  - Stop hardcoding original button text, grab it from the HTML element
  - Set `XMLHttpRequest.open()` URL to `form.action` (`HTMLFormElement.action`)
    instead of hardcoding `'/upload.php'`
  - Stop abusing HTML anchor elements for `<a>$errorMessage</a>`
- Lint PHP again (`phpmd`, `php-codesniffer` etc)
- Add a `<label>` element or `title=` attribute to uploader in `index.swig` and
  `nojs.swig`
- Fix/add handling for temporary files for which uploads have failed (remove or
  move them)

### Release `2.2.0`

- Add exception handling (`try{}`) to initial database connection
- More tests
  - CSS
  - JavaScript
  - HTML?
  - PHP
  - Checking if copyright headers exist
- Add Flash-free clipboard for copying uploaded file links
- Incorporate alchimist's SHA256 hashing to replace SHA1
- Add SQLite support
- Increase visibility of contact and copyright takedown pages
- Create a better `CONTRIBUTING.md` file
- Finish rewriting the FAQ into a `<dl>` description list
- Change or remove suggested web browsers to install in `check_fileapi.swig`
  - Chrome is a non-free web browser. Chromium is free/libre software.
  - Firefox suggests installing non-free addons. GNU IceCat does not.

### Release `3.0.0`

- Remove Gyazo response
- Merge Wub's `application/vnd.api+json` patch
- Implement protection against Cross-Site Request Forgeries
- Refactor PHP code by adding namespaces
- Remove Grunt and its dependencies
  - Replace with Make or something more sane
  - <http://blog.keithcirkel.co.uk/why-we-should-stop-using-grunt/>
  - **I urge to hurry with this.** `grunt-swig` requires an older `0.4.x`
    version of Grunt which I assume is no longer supported. Expected package
    breakage with NPM version `6.0.x` and later.
- Rewrite JavaScript to ES6 using eslint-config-airbnb
  - Our build system may not support ES6. Does it?
- Replace `nojs.html` with `<noscript>`-like fallback
- Merge alchimist's `expire` removal from MySQL schema and `upload.php`
- Remove `ob_start`
- Split `upload.php` into a common file class for file functions and the
  last ~15 lines of code for handling the upload and response
- Seperate default settings and local settings
  - This will also avoid an issue where files are uploaded to webroot with
    filename `POMF_FILES_ROOTabcdef.ext` if `POMF_FILES_ROOT` is undefined.
- Reduce default `{{max_upload_size}}` back to original `50 MiB` or a more
  common `100 MiB` used with CloudFlare setups
- Rename `pages/` into `templates/` or `views/` to better describe what the
  folder really is
- Consider using `xhr.responseType = 'json';` with caution for browser
  compatibility

### Release `4.0.0`

- Rewrite upload API
  - Decide if `status` / `errorcodes` are bad or not
    - Use HTTP responses like any sane API, don't reinvent the wheel
  - Move to an api-subdomain (e.g. <https://api.pantsu.cat/files/>)
  - Don't forget the more obscure HTTP methods such as `OPTIONS`
  - Consider adding JSON-P response type
- Add internationalization support
  - May require swapping Swig templates for Mustache or Handlebars

## pantsu/docs

- Document the API
  - <http://bradfults.com/the-best-api-documentation/>
- JSDoc
- Getting help
- Quick start
- …

## pantsu/status

- Research status software, find beautiful examples
- Create a status page

## pantsu/api

- Research if this is an ethical issue (SaaSS)
- Start creating an API for searching and other stuff

## pantsu/pomfload

- Rename project to accommodate WTFPL version 2 license
- Relicense to ISC (OpenBSD license)
- Rewrite the code to support UNIX standard input
- Finish writing docs
- Create an OpenBSD `Makefile`
- Add to OpenBSD ports

## pantsu/uguu

- …

## wubthecaptain/fuuka

- Publish Git repository
- Apply patches to replicate what's at Rebecca Black Tech
- Inform eksopl of the new Git repository
- Read `BUGS.txt` and cry ;\_;
  - Fix arbitrary redirection vulnerability
- Essentially rewrite the dumper for 4chan API
  - Perl?
  - Go?
- …

## Pantsu.cat sysadmin tasks

- Setup a mailing list
  - GNU Mailman
  - OpenSMTPd
- Add IPv6 support
- Distribute services across multiple IPv4-addresses
