[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILControlStart.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_ControlStart**

# FSIL_ControlStart

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long FSIL_ControlStart(); // form 1`
- `long FSIL_ControlStart(byte address); // form 2`
- `long FSIL_ControlStart(dbNode fs); // form 3`
- `long FSIL_ControlStart(dbNode fs, byte address); // form 4`

## Description

Activates node to start Address Claiming.

The File Server starts Address Claiming (if NMT is activated). If the Address Claiming was successful, cyclic messages are sent.

## Parameters

- **fs**: FS simulation node to apply the function
- **address**: Source address of the node (optional)

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

See [FSIL_ControlStop](CAPLfunctionIso11783FSILControlStop.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
