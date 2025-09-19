# remove

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax (Dynamic)

- `long map[char[]]::remove(char key[]);`
- `long map[float]::remove(float key);`
- `long map[int64]::remove(int64 key);`
- `long map[long]::remove(long key);`

## Description

Removes one element from the field.

## Complexity

O(log(N))

## Parameters

- **key**: Key of the element.

## Return Values

- **1**: Key was available
- **0**: Key was not available

## Example

```plaintext
m.remove(3);
```
