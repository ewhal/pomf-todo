# the Pantsu.cat developer team TODO list

## pantsu/pomf

### Release `3.0.0`
- Replace potentially non-free `UploadException.class.php`
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
  - Deprecate or remove unused selectors like `.jumbotron .btn.drop`
- Clean up and refactor Luminarys' new JavaScript
  - Finish writing up JSDoc comments (`luminarys/refactor-js-pu`)
  - Stop hardcoding original button text, grab it from the HTML element
  - Set `XMLHttpRequest.open()` URL to `form.action` (`HTMLFormElement.action`)
    instead of hardcoding `'/upload.php'`
  - Stop abusing HTML anchor elements for `<a>$errorMessage</a>`
- Lint PHP again (`phpmd`, `php-codesniffer` etc)
- Add a `<label>` element or `title=` attribute to uploader in `index.swig` and
  `nojs.swig`
- Fix/add handling for temporary files for which uploads have failed (remove or
  move them)
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
- Merge Wub's `application/vnd.api+json` patch
- Implement protection against Cross-Site Request Forgeries
- Refactor PHP code by adding namespaces
- Rewrite JavaScript to ES6 using eslint-config-airbnb
  - Our build system may not support ES6. Does it?
- Merge alchimist's `expire` removal from MySQL schema and `upload.php`
- Seperate default settings and local settings
  - This will also avoid an issue where files are uploaded to webroot with
    filename `POMF_FILES_ROOTabcdef.ext` if `POMF_FILES_ROOT` is undefined.
- Reduce default `{{max_upload_size}}` back to original `50 MiB` or a more
  common `100 MiB` used with CloudFlare setups
- Consider using `xhr.responseType = 'json';` with caution for browser
  compatibility
- Remove `ENGINE=InnoDB;` from SQL schema, let the default engine be decisive

### Release `4.0.0`
- Add internationalization support
  - May require swapping Swig templates for Mustache or Handlebars

## pantsu/pomfload

- Rename project to accommodate WTFPL version 2 license
- Relicense to ISC (OpenBSD license)
- Rewrite the code to support UNIX standard input
- Finish writing docs
- Create an OpenBSD `Makefile`
- Add to OpenBSD ports

