# Notes on Date and Time

## Backend (server, database)
- always store date and time in ISO 8601 format, UTC timezone (e.g. `2023-01-01T00:00:00Z`)
- when necessary to store the timezone, store it separately from the date and time
- always use libraries for date and time manipulation (e.g. `date-fns`) ¹
- API endpoints should accept either ISO datestrings or timestamps ²
- JS uses milliseconds for timestamps, other languages (e.g. PHP) use seconds ³

## Frontends
- see ¹
- see ²
- see ³

## Date object
- `toLocaleDateString` et al.: always explicitely pass formatting options to avoid unexpected results in some locales
- only create dates from string when ISO
- it's useful to store user-provided date and time values in separate variables as numbers (e.g. `new Date(year, zeroIndexedMonth, day, hours, minutes, seconds)`)

## Formats
- never take the order for granted (e.g. `11/10/1990` could mean `1990-10-11` or `1990-11-10`)

## Node.js
- make sure `full-icu` is enabled when running test suites or formatting might default to `en-US`
