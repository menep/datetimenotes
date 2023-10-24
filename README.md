# Notes on DateTime

- Server: store DateTime in ISO 8601 format, UTC timezone (e.g. `2023-01-01T00:00:00Z`)
- Server, client: use libraries (e.g. `date-fns`)

- `Date.toLocaleDateString`: always explicitely pass formatting options to avoid unexpected results in some locales

- Formats: never take the order for granted (e.g. `11/10/1990` could mean `1990-10-11` or `1990-11-10`)

- Node.js: always check that `full-icu` is enabled when running test suites or formatting might default to `en-US`
