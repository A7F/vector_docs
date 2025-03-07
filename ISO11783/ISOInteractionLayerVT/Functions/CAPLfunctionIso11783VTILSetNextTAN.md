[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetNextTAN.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_SetNextTAN**

# VTIL_SetNextTAN

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_SetNextTAN(byte workingSetMasterAddress, dword tan); // form 1
long VTIL_SetNextTAN(dbNode vt, byte workingSetMasterAddress, dword tan); // form 2
```

## Description

Sets the TAN to be used in the next activation message.  
**Note**: The TAN is incremented by the Virtual Terminal IL automatically after an activation message is sent (in the range between 0 and 15).

## Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMasterAddress**: Address of the Working Set Master.
- **tan**: Next TAN, 0..15.

## Return Values

- **0**: Blocking of all messages has been stopped successfully.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)