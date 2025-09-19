[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsFsFunctionEnable.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsFsFunctionEnable

# mostAsFsFunctionEnable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostAsFsFunctionEnable(long functionId, long opTypes); // form 1`
- `long mostAsFsFunctionEnable(long functionId, long opTypes, char cbSendStatus[]); // form 2`

## Description

`mostAsFsFunctionEnable()` registers a function and its operations with the function service. The service must have been previously enabled for the function block with [mostAsFsEnable](CAPLfunctionMOSTAsFsEnableMOSTAsFsDisable.md).

The second option registers a function with the notification service simultaneously. For this to be achieved, the function must be of the "Property" type and the notification service of the function block must have been previously enabled with [mostAsNtfEnable](CAPLfunctionMOSTAsNTFEnable.md).

**Database support:**

The special value functionID=-1 triggers the execution of the CAPL function for all MOST functions and operations of the function block from the function catalog.

## Parameters

- **functionIdText**: Function ID or -1 for all functions of the function block from the database.
- **cbSendStatus[]**: Name of the CAPL function that generates and sends the status message. If functionID=-1, cbSendStatus designates the prefix of the CAPL send functions to be defined. If an empty character string is specified, the default prefix "SendStatus_" is used.
- **opTypes (Property/Method)**:
  - **Bit 0**: OpType = 0x0 (Set/Start)
  - **Bit 1**: OpType = 0x1 (Get/Abort)
  - **Bit 2**: OpType = 0x2 (SetGet/StartResult)
  - **Bit 3**: OpType = 0x3 (Increment/-)
  - **Bit 4**: OpType = 0x4 (Decrement/-)
  - **Bit 5**: OpType = 0x5 (GetInterface/GetInterface)
  - **Bit 6**: OpType = 0x6 (-/StartResultAck)
  - **Bit 7**: OpType = 0x7 (-/AbortAck)
  - **Bit 8**: OpType = 0x8 (-/StartAck)
  - **Bit 9**: OpType = 0x9 (-/ErrorAck)
  - **Bit 10**: OpType = 0xA (-/ProcessingAck)
  - **Bit 11**: OpType = 0xB (-/Processing)
  - **Bit 12**: OpType = 0xC (Status/Result)
  - **Bit 13**: OpType = 0xD (-/ResultAck)
  - **Bit 14**: OpType = 0xE (Interface/Interface)
  - **Bit 15**: OpType = 0xF (Error)
  - **Bit 16**: All OpTypes corresponding to 0-15, if they are defined in the XML function catalog.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

- `mostAsFsFunctionEnable(0x123, 0x8002)` enables the 0x123 function with the "Get" and "Error" operations. The Command Interpreter will then send the error 'OpType not available' for the remaining command OpTypes of the function only.
- `mostAsFsFunctionEnable(0x123, 0xFFFF)` enables the 0x123 function and all its operations. The command interpreter will never send 'OpType not available' for this function.
- `mostAsFsFunctionEnable(0x123, 0x01FFFF)` enables the 0x123 function and all operations defined in the XML function catalog.
- `mostAsFsFunctionEnable(0x123, 0)` disables the 0x123 function
- `mostAsFsFunctionEnable(-1, 0x01FFFF)` enables all functions and all operations defined in the XML function catalog.
- `mostAsFsFunctionEnable(-1, 0)` disables all operations of all functions defined in the XML function catalog.
- `mostAsFsFunctionEnable(-1, 0x01FFFF, "SendStatus_")` enables all functions and all operations defined in the XML function catalog. Additionally, functions of type 'property' will be registered at the Notification Service if a corresponding CAPL function for sending the status message is defined.

[mostAsFsEnable, mostAsFsDisable](CAPLfunctionMOSTAsFsEnableMOSTAsFsDisable.md) • [mostAsFsFunctionEnableEx](CAPLfunctionMOSTAsFsFunctionEnableEx.md) • [mostAsNtfFunctionEnable](CAPLfunctionMOSTAsNTFFunctionEnable.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
