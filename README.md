# Password Helper

Schema based password generator

- No backend
- Nothing to remember

Generate a secure password using your user name / ID which in most cases would be your email / phone & the service name

#### What about schema? Where is this saved??

Schema is prefilled using URL query param 'schema'. So you create the URL once and save it / bookmark it. That's it :-)

Refer to example below for more details

## Schema

The schema defines how the password is derived from domain and user name fields

schema is defined as:

`[@|#][-]{0-9}*[+]`

- '@' - means domain name
- '#' - means user name
- '@'/ '#' is followed by number that represents the index into the field. if the number is negative (starts with '-'), it represents index starting from end of string
- '+' - means captialize
- '$' immediately after '@'/'#' means the length of domain/user name respectively
- any other character is copied as is

### Example

say the schema is `@1+@-1@$1234!#1+#2`

- `@1+` means 1st letter from domain in capitals
- `@-1` means last letter from domain
- `@$` means numbers of letters in domain
- `1234!` means '1234!'
- `#1+` means 1st letter from user name in capitals
- `#2` means 2nd letter from user name

so if domain is `test` and user name is `test`
the password generated would be - `Tt41234!Te`

this scehma can be pre-filled by appending a query param `schema=QDErQC0xQCQxMjM0ISMxKyMy`

[Try it](https://vharish836.github.io/coolpass/?schema=QDErQC0xQCQxMjM0ISMxKyMy)
