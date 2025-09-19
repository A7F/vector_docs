[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILControlStop.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ControlStop

# TCIL_ControlStop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ControlStop(); // form 1`
- `long TCIL_ControlStop(dword option); // form 2`
- `long TCIL_ControlStop(dbNode tc); // form 3`
- `long TCIL_ControlStop(dbNode tc, dword option); // form 4`

## Description

Deactivates the Task Controller and stops sending cyclic messages. A [Cannot Claim Address](../../../../CANoeCANalyzer/J1939/j1939basics/j1939NMT.md) message is sent, if the NMT is activated and the message is not suppressed with the parameter `option` set to 1.

Removes all device descriptor object pools (DDOPs) too.

## Parameters

- **tc**: TC simulation node to apply the function
- **option**: Options  
  1: Suppress sending **Cannot Claim Address** message

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 4

```c
void SetDataMaskSize(dword newSize) {
  // data mask size can only be changed if TC is stopped
  TCIL_ControlStop(TC, 1);
  // wait until Working Sets have detected that TC is offline
  TestWaitForTimeout(3500);
  // change size and restart TC
  TCIL_SetNodeProperty(TC,"dataMaskSize", newSize);
  TCIL_ControlStart(TC);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
