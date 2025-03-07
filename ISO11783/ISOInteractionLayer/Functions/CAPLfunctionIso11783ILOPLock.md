[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPLock.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPLock

# Iso11783IL_OPLock

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPLock( dword lock, dword maskID, dword timeout ); // form 1`
- `long Iso11783IL_OPLock( dbNode implement, dword lock, dword maskID, dword timeout ); // form 2`

## Description

The function locks the screen updates on the Virtual Terminal. A **Lock** command is sent to the Virtual Terminal.

## Parameters

- **lock**
  - 0: unlock
  - 1: lock
- **maskID**
  - object ID of the data mask object
- **timeout**
  - timeout in [ms]
- **implement**
  - Simulation node to apply the function.

## Return Values

- **0**
  - function has been executed successfully
- **< 0**
  - an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPLock( 1200, 1, 500 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)