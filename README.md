# the Pantsu.cat developer team TODO list

## pantsu/pomf

### Release `1.1.0`

- Merge `update-depends` to `master`
- Go through history to see if version 2.0.0 is really a better choice
- Update `package.json` with new Git URLs
- Fix LibreJS `@source`
- Liberate `img/`
- Write release notes to docs
- Write one test?
- Rewrite `README.md` to standard markdown (no three backticks for code)

### Release `1.1.1`

- Replace Grunt imagemin task with pngquant variant
- Make `bg.png` smaller
  - Perhaps replace completely with pure CSS
- Make HTML response class better / more valid
  - Aim for a low amount of PHP code

### Release `1.2.0`

- More tests 
  - CSS
  - JSCS
  - HTML?
  - PHP
- Deprecate Gyazo response
- Zepto / jQuery rewrite

### Release `2.0.0`

- Rewrite upload API
  - Remove Gyazo response
  - Decide if `status` / `errorcodes` are bad or not
    - Use HTTP responses like any sane API, don't reinvent the wheel

## pantsu/docs

- Publish LICENSE
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
