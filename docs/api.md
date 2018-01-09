# pystrct's API

*class*  pystrct.**StructFile**(*filepath, fmt*): return a StructFile object.

- *string* **filepath**: a path to a binary file.
- *string* **fmt**: Struct's format. To know how to create a format, see the
[Python 3 Struct's documentation](https://docs.python.org/3/library/struct.html#format-characters).

### Methods
*list/tuple/object* **next**(*n*): return a *list* of the next *n* elements on file according to *tell*.
If n is 1, return the element itself.

- *int* **n**: number of elements *(default 1)*.
---
*list/tuple/object* **prev**(*n*): return a *list* of the previous *n* elements on file according to *tell*.
If n is 1, return the element itself.

- *int* **n**: number of elements *(default 1)*.
---
*list/tuple/object* **get**(*i, n*): return a *list* of the *n* elements starting from the *ith* element.
If n is 1, return the element itself.

- *int* **i**: start position.
- *int* **n**: number of elements from start *(default 1)*.
---
*tuple/object* **last**(): return the last element on the end of file.
---
**append**(*value*): append a *value* in file.

- *tuple* **value**: value to be appended. The tuple must follow the struct *format* defined.
---
**write**(i, value): write/overwrite a *value* in the *ith* position in file.

- *int* **i**: index in file.
- *tuple* **value**: value to be written. The tuple must follow the struct *format* defined.
---
**truncate**(n): erase the last *n* elements.

### Properties
*int* **size**: file size in bytes.

---
*int* **tell**: file pointer's position as an index.

---
*int* **length**: total elements in file.
