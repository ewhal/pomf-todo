# the Pantsu.cat developer team TODO list

## pantsu/pomf

### Release `2.0.2`

- Replace potentially non-free `UploadException.class.php`

### Release `2.1.0`

- More tests 
  - CSS
  - JavaScript
  - HTML?
  - PHP
  - Checking if copyright headers exist
- Add UTF-8 file name support
- Add exception handling (`try{}`) to initial database connection
- Clean up CSS
  - Use CSSLint for example, but don't blindly follow it
- Make `bg.png` smaller
  - Perhaps replace completely with pure CSS
- Add Flash-free clipboard for copying uploaded file links
- Add internationalization support
  - May require swapping Swig templates for Mustache or Handlebars
- Clean up and refactor Luminarys' new JavaScript
  - Finish writing up JSDoc comments (`luminarys/refactor-js-pu`)
  - Reimplement `no-file-api`
- Create a better `CONTRIBUTING.md` file

### Release `3.0.0`

- Rewrite upload API
  - Remove Gyazo response
  - Decide if `status` / `errorcodes` are bad or not
    - Use HTTP responses like any sane API, don't reinvent the wheel
  - Move to an api-subdomain (e.g. <https://api.pantsu.cat/v2/files/>)
  - Merge Wub's `application/vnd.api+json` patch
- Implement protection against Cross-Site Request Forgeries
- Refactor PHP code by adding namespaces
- Remove Grunt and its dependencies
  - Replace with Make or something more sane
  - <http://blog.keithcirkel.co.uk/why-we-should-stop-using-grunt/>
- Rewrite JavaScript to ES6 using eslint-config-airbnb
  - Our build system may not support ES6. Does it?

## pantsu/docs

- Document the API
  - <http://bradfults.com/the-best-api-documentation/>
- JSDoc
- PHPDoc
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
- Setup cgit to replace gogs
