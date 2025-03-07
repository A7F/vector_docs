[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILGetState.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_GetState**

# FSIL_GetState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_GetState();` // form 1
- `long FSIL_GetState(dbNode fs);` // form 2

## Description

Returns the current state of the FS IL.

## Parameters

- **fs**: FS simulation node to apply the function

## Return Values

- **0**: Initialized
- **1**: Claiming
- **2**: Active
- **3**: Stopped
- **4**: Suspended
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 1**

```plaintext
on key 's'
{
  long state;
  state = FSIL_GetState();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)