[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILNodeControlWait.md)

**CAPL Functions** » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILNodeControlWait

# ILNodeControlWait

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeControlWait(char aNodeName[]); // form 1
long ILNodeControlWait(char aNodeName[],dword flags); // form 2
```

## Description

Stops the interaction layer of the specified simulation node. Cyclical sending of messages stops but setting of signals is still possible. The specified node must be in the current bus context. In all other cases the function has no effect and will return with an error.

## Parameters

- **aNodeName**: Name of the node of which the interaction layer should be stopped.
- **flags**:
  - 0: data update allowed
  - 1: data update ignored, corresponds to form 1

## Return Values

- **0**: No error
- **-10000**: Unspecific error
- **-10001**: Node or module not found
- **-10002**: No suitable module available
- **-10003**: Function is not supported by module
- **-10004**: Module returns illegal value
- **other**: Error in module

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)