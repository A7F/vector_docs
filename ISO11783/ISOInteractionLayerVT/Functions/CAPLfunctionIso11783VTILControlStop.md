[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILControlStop.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ControlStop**

# VTIL_ControlStop

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long VTIL_ControlStop();` // form 1
- `long VTIL_ControlStop(dword option);` // form 2
- `long VTIL_ControlStop(dbNode vt);` // form 3
- `long VTIL_ControlStop(dbNode vt, dword option);` // form 4

## Description

Deactivates the Virtual Terminal and stops sending cyclic messages. A [Cannot Claim Address](../../../../CANoeCANalyzer/J1939/j1939basics/j1939NMT.md) message is sent, if the NMT is activated and the message is not suppressed with the parameter `option` set to 1.

## Parameters

- **vt**: VT simulation node to apply the function
- **option**: Options
  - 1: Suppress sending **Cannot Claim Address** message

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example for test nodes

```plaintext
void SetDataMaskSize(dword newSize)
{
  // data mask size can only be changed if VT is stopped
  VTIL_ControlStop(VT, 1);
  // wait until Working Sets have detected that VT is offline
  TestWaitForTimeout(3500);
  // change size and restart VT
  VTIL_SetNodeProperty(VT,"dataMaskSize", newSize);
  VTIL_ControlStart(VT);
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
