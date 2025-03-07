[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILSetCANFDParam.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILSetCANFDParam

# ILSetCANFDParam

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILSetCANFDParam(dword ID, int FDF, int BRS, int DLC)
long ILSetCANFDParam(dbMsg msg, int FDF, int BRS, int DLC)
```

## Description

The function allows setting of CAN FD parameters for a specific message.

## Parameters

- **ID**: CAN-ID of message that should be modified.
- **msg**: message that should be modified.
- **FDF**:
  - -2: reset FDF setting of message according to database
  - -1: do not change FDF setting of message
  - 0: FDF off
  - 1: FDF on
  - This parameter has highest priority and will overrule settings for BRS and DLC, i.e. BRS = 0 and max DLC = 8 in case that FDF off.
- **BRS**:
  - -2: reset BRS settings of message according to database
  - -1: do not change BRS setting of message
  - 0: BRS off
  - 1: BRS on
- **DLC**:
  - -2: reset DLC settings of message according to database
  - -1: do not change DLC setting of message
  - ≥0: set DLC of message to specified value

## Return Values

- **0**: No error
- **-53**: CAN FD not supported by CANoe version
- **-100**: message/message ID not found, because not handled by IL

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)