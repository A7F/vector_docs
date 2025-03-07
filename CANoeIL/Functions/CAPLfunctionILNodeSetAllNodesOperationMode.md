[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILNodeSetAllNodesOperationMode.md)

**CAPL Functions** » **CANoe IL** » **ILNodeSetAllNodesOperationMode**

# ILNodeSetAllNodesOperationMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note
- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax
```
long ILNodeSetAllNodesOperationMode(long mode, long param)
```

## Description
Sets specific operation mode in the interaction layer of all nodes in the current bus context.

## Parameters

- **mode**: 
  - `0`: influences update bits; other values have currently no effect and are reserved.

- **param**: The effect of **param** depends on the parameter **mode**:
  - **Mode Value**: `0`
    - **Param Value**:
      - `0`: all update bits will be set or reset depending on the signal updates
      - `1`: all update bits will always be sent with value = 1

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

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)