[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664TriggerMessage.md)

# A664TriggerMessage

[CAPL Functions](../../CAPLfunctions.md) » [AFDX »](../CAPLfunctionsAFDXOverview.md) A664TriggerMessage

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
long A664TriggerMessage (a664Message aMessage, dword mode)
```

## Description

This function triggers the scheduling of the [a664Message](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXmessage.md) "aMessage". The message is either scheduled once or periodically. To forward an AFDX message in the analysis branch, use the function [output()](CAPLfunctionAfdxOutput.md).

## Parameters

- **aMessage**: The message object to be scheduled.
- **Mode**: Triggering mode.
  - 0: Immediate (transmit once without considering BAG)
  - 1: SingleShot (transmit once according to BAG)
  - 2: StartCyclic (start cyclic transmission according to the selector value [TxCycle](../CAPLfunctionsAFDXSelectors.md#TxCycle))
  - 3: StopCyclic (stop cyclic transmission)

## Return Values

- **0**: Successfully triggered.
- **Other values**: See [error codes.](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```c
// define messages from database
a664Message DEMOMSG_INT1 msgInt1 = {msgChannel = 1};
a664Message DEMOMSG_ALLTYPES myMsg = {msgChannel = 1};

a664TriggerMessage(msgInt1, 0);  // send DEMOMSG_INT1 immediately
a664TriggerMessage(msgInt1, 1);  // send DEMOMSG_INT1 once respecting the BAG
a664TriggerMessage(msgInt1, 2);  // send DEMOMSG_INT1 periodically

myMsg.TxCycle = 100;  // change period from DBC to 100msec
a664InitPayload (myMsg); // set payload to last known signal values
myMsg.VFG_OIL_TEMP_AB_32 = 33;  // overwrite signal value within the message
myMsg.FS_FDS_1_HSMU_DEMO_ALLTYPES = 3;  // set FS within the message
a664TriggerMessage(myMsg, 2);  // send cyclic with 100msec period
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)