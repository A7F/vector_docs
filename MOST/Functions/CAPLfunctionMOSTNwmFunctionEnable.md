[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTNwmFunctionEnable.md)

**CAPL Functions** » **MOST** » **mostNwmFunctionEnable**

# mostNwmFunctionEnable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostNwmFunctionEnable(long functionId, long opTypes);
```

## Description

Registers and unregisters a function and its operations with the NetworkMaster.

**Note:** The NetworkMaster will not respond to the new registered function and thus an [on mostMessage](../EventProcedures/CAPLfunctionOnMOSTMessage.md)/[on mostAMSMessge](../EventProcedures/CAPLfunctionOnMOSTAMSMessage.md) handler has to be implemented in the CAPL module of the NetworkMaster.

## Parameters

- **functionId**: Function ID.
- **opTypes (Property/Method)**:
  - `0`: unregisters the function.
  - `1-0xFFFF`: according to the table below.

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

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—
