# ILConfigureNMNotifications

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword ILConfigureNMNotifications (dword direction, dword mode);
```

## Description

The function allows manipulating the coupling between IL and NM module. The function can be called at any time.

## Parameters

- **direction**
  - 0: IL->NM
  - 1: NM -> IL
  - Other values are reserved.

- **mode**
  - 0: notifications are off
  - 1: notifications are done always (regardless of existing callback functions)
  - 2 and 3: notifications are done only in absence of certain callback functions (default)
  - Other values are reserved.

## Return Values

- **0**: No error
- **Others**: Error in module

## Example

—
