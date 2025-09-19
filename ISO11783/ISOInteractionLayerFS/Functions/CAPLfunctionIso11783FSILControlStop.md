[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILControlStop.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_ControlStop

# FSIL_ControlStop

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_ControlStop(); // form 1`
- `long FSIL_ControlStop(dword option); // form 2`
- `long FSIL_ControlStop(dbNode fs); // form 3`
- `long FSIL_ControlStop(dbNode fs, dword option); // form 4`

## Description

Deactivates the File Server and stops sending cyclic messages.

A [Cannot Claim Address](../../../../CANoeCANalyzer/J1939/j1939basics/j1939NMT.md) message is sent if the NMT is activated and the message is not suppressed with the parameter `option` set to 1.

Removes all device descriptor object pools (DDOPs) too.

## Parameters

- **fs**: FS simulation node to apply the function
- **option**: Options  
  1: Suppress sending **Cannot Claim Address** message

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 4

```c
void SetDataMaskSize(dword newSize)
{
  // data mask size can only be changed if FS is stopped
  FSIL_ControlStop(FS, 1);
  // wait until Working Sets have detected that FS is offline
  TestWaitForTimeout(3500);
  // change size and restart FS
  FSIL_SetNodeProperty(FS,"dataMaskSize", newSize);
  FSIL_ControlStart(FS);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
