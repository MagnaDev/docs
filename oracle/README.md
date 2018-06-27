# Oracle

## Naming Conventions

This document describes the naming conventions which should be adhered to when
developing applications using Oracle PL/SQL.

Some general rules: 
 
* Do not use names with a leading numeric character.
* Oracle is not case sensitive with names, for that reason, only use lowercase
    for naming.
* Always choose meaningful and specific names.
* Abbreviations should only be used if the full name is excessively long. They
    should be shorter than 5 characters and must be widely known and accepted.
* Do not use Oracle reserved words as names. A list can be found in the 
    dictionary view `v$reserved_words`.

| Identifier | Convention | Example |
| --- | --- | --- |
| Local Variable | `l_<name>` | `l_first_name` |
| Global Variable | `g_<name>` | `g_version` |