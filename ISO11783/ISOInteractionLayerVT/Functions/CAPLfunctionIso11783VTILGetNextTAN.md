[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetNextTAN.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_GetNextTAN**

# VTIL_GetNextTAN

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_GetNextTAN(byte workingSetMasterAddress, dword& tan); // form 1
long VTIL_GetNextTAN(dbNode vt, byte workingSetMasterAddress, dword& tan); // form 2
```

## Description

Gets the TAN that will be used in the next activation message.

## Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMasterAddress**: Address of the Working Set Master
- **tan**: Returns the next TAN.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
