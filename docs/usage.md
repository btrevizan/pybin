## Importing
```python
from pystrct import StructFile
```

## Creating a new object
```python
# Create/open a new file structed as (int, int)
strct_file = StructFile('pairs.bin', '2i')
```

## Inserting data
```python
# Values must match the defined struct format
strct_file.append((1, 2))
strct_file.append((3, 4))
strct_file.append((5, 6))
strct_file.append((7, 8))
strct_file.append((9, 10))

# Overwrite (3, 4) pair
strct_file.write(1, (30, 40))
```

## Forcing file close and save
```python
# A representation of the object
stcrt_repr = repr(strct_file)

# Close file and save all
del strct_file
```

## Retrieving data
```python
# Get object from representation
strct_file = eval(strct_repr)

# Get next 4 pairs
first_four = strct_file.next(4)  # [(1, 2), (30, 40), (5, 6), (7, 8)]

# Get previous 3 pairs
prev_four = strct_file.prev(3)   # [(30, 40), (5, 6), (7, 8)]

# Get pair on index 3
pair = strct_file.get(3)         # (7, 8)

# Get the next 2 starting from 1
pairs = strct_file.get(1, 2)     # [(30, 40), (5, 6)]
```

## Deleting data
```python
# Delete (5, 6) pair
last_pair = strct_file.last()

# Overwrite (5, 6) with (9, 10)
strct_file.write(2, last_pair)

# Delete (9, 10) in last
strct_file.truncate(1)
```
