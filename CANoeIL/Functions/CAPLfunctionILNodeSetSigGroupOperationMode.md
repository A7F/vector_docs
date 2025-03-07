[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILNodeSetSigGroupOperationMode.md)

**CAPL Functions** » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILNodeSetSigGroupOperationMode

# ILNodeSetSigGroupOperationMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeSetSigGroupOperationMode(char signalGroupName[], long mode, long param);
```

## Description

Sets specific operation mode in the interaction layer for the specified signal group.

## Parameters

- **signalGroupName**: Name of the signal group.
- **mode**: 
  - 0: influences update bits; other values have currently no effect and are reserved.
- **param**: The effect of **param** depends on the parameter **mode**:
  - **Syntax form 1, Mode Value 0**:
    - 0: all update bits will be set or reset depending on the signal updates
    - 1: all update bits will always be sent with value = 1
  - **Syntax form 2, Mode Value 0**:
    - 0: the update bit of the signal group will be set or reset depending on the signal updates
    - 1: the update bit of the signal group will always be sent with value = 1
  - **Syntax form 3, Mode Value 0**:
    - 0: the update bit will be set or reset depending on the signal updates
    - 1: the update bit will always be sent with value = 1

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

[ILNodeSetOperationMode](CAPLfunctionILNodeSetOperationMode.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)