# coolpass

Schema based password generator

## schema

The schema defines how the password is derived from domain and user name fields

schema is defined as:

`[@|#][-]{0-9}*[+]`

- '@' - means domain name
- '#' - means user name
- '@'/ '#' is followed by number that represents the index into the field. if the number is negative (starts with '-'), it represents index starting from end of string
- '+' - means captialize
- '$' immediately after '@'/'#' means the length of domain/user name respectively
- any other character is copied as is
