# lookupSysvarData

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
sysvarData * lookupSysvarData(char sysvarPath[]); // form 1
sysvarData * lookupSysvarData(char namespace[], char sysvarName[]); // form 2
```

## Description

Searches for a system variable definition. If the system variable is not found or has a wrong type, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `sysvar`.

**Notes**: It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.

## Parameters

- **sysvarPath**: Fully qualified name of the variable (including namespaces)
- **namespace**: Namespace(s) of the variable, separated with **::**
- **sysvarName**: Name of the variable

## Return Values

The found system variable or an invalid object.

## Example

—
