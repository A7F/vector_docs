# A664TriggerFrame

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```
long A664TriggerFrame (a664Frame aFrame, dword mode)
```

## Description

This function triggers the transmission of a single [a664Frame](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXframe.md) "aFrame" either immediately or respecting the BAG. To forward an AFDX frame in the analysis branch, use the function [output()](CAPLfunctionAfdxOutput.md).

## Parameters

- **aFrame**: The frame object to be scheduled.
- **mode**: Triggering mode.
  - 0: Immediate (transmit once without considering BAG)
  - 1: SingleShot (transmit once according to BAG)

## Return Values

- **0**: Successfully triggered.
- **Other values**: See [error codes.](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
a664Message DEMOMSG_ALLTYPES myMsg = {msgChannel = 1};
a664Frame * myFrame;
myMsg.TxCycle = 100;
myMsg.VFG_OIL_TEMP_AB_32 = 33;
myMsg.FS_FDS_1_HSMU_DEMO_ALLTYPES = 3;

// use myMsg as source to define a frame for manipulations
myFrame = myMsg;
myFrame.UdpDstPort = 3333;  // change UDP destination port
a664TriggerFrame(myFrame, 1);  // transmit the frame respecting the BAG
```

