[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILConfigureNMNotifications.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILConfigureNMNotifications

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)