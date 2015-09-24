# the Pantsu.cat developer team TODO list

## pantsu/pomf

### Release `1.1.0`

- Go through history to see if version 2.0.0 is really a better choice
- Write release notes to docs
- Write one test?

### Release `1.1.1`

- Remove Grunt imagemin task
- Make `bg.png` smaller
  - Perhaps replace completely with pure CSS
- Make HTML response class better / more valid
  - Aim for a low amount of PHP code
- Remove more moe code from `upload_file()`

### Release `1.2.0`

- More tests 
  - CSS
  - JSCS
  - HTML?
  - PHP
  - Checking if copyright headers exist
- Deprecate Gyazo response
- Zepto / jQuery rewrite
- Add UTF-8 file name support
- Add exception handling (`try{}`) to initial database connection
- Clean up CSS
  - Use CSSLint for example, but don't blindly follow it

### Release `2.0.0`

- Rewrite upload API
  - Remove Gyazo response
  - Decide if `status` / `errorcodes` are bad or not
    - Use HTTP responses like any sane API, don't reinvent the wheel
  - Move to an api-subdomain (e.g. <https://api.pantsu.cat/v2/upload/>)
- Implement protection against Cross-Site Request Forgeries
- Refactor PHP code by adding namespaces
- Remove Grunt and its dependencies
  - Replace with Make or something more sane
  - <http://blog.keithcirkel.co.uk/why-we-should-stop-using-grunt/>

## pantsu/docs

- Document the API
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
- Read BUGS.txt and cry ;_;
  - Fix arbitrary redirection vulnerability
- Essentially rewrite the dumper for 4chan API
  - Perl?
  - Go?
- …
