# pystrct's API

*class* pystrct.**StructFile**(*filepath, fmt*)

Return a StructFile object.

- **filepath**: *string*

A path to a binary file.

- **fmt**: *string*

Struct's format. To know how to create a format, see the
[Python 3 Struct's documentation](https://docs.python.org/3/library/struct.html#format-characters).

### Methods
**next**(*n*)

Return a *list* of the next *n* elements on file according to *tell*. If n is 1, return the element itself.
- **n**: *int (default 1)*

    Number of elements.
---
**prev**(*n*)\
Return a *list* of the previous *n* elements on file according to *tell*. If n is 1, return the element itself.
- **n**: *int (default 1)*\
    Number of elements.
---
**get**(*i, n*)\
Return a *list* of the *n* elements starting from the *ith* element. If n is 1, return the element itself.
- **i**: *int*\
    Start position.
- **n**: *int (default 1)*\
    Number of elements from start.
---
**last**()\
Return the last element on the end of file.
---
**append**(*value*):
Append a *value* in file.
- **value**: *tuple*\
    Value to be apendded. The tuple must follow the struct *format* defined.
---
**write**(i, value):
Write/overwrite a *value* in the *ith* position in file.
- **i**: *int*\
    Index in file.
- **value**: *tuple*\
    Value to be written. The tuple must follow the struct *format* defined.
---
**truncate**(n)\
Erase the last *n* elements.

### Properties
**size**: *int*\
Return the file size in bytes.
---
**tell**: *int*\
Return the file pointer's position as an index.
---
**length**: *int*\
Return the total elements in file.
