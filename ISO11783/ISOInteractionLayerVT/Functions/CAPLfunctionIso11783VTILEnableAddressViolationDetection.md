[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILEnableAddressViolationDetection.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_EnableAddressViolationDetection

# VTIL_EnableAddressViolationDetection

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_EnableAddressViolationDetection(dword numberOfDM1Transmissions); // form 1
long VTIL_EnableAddressViolationDetection(dbNode node, dword numberOfDM1Transmissions); // form 2
```

## Description

Activates detection of address violations by other nodes.

Address violation means that a message is registered on the bus with the source address of the simulated node that was not sent by the simulated node itself.

If an address violation is detected, the simulated node sends an Address Claimed message. If diagnostics support is activated (via [VTIL_ActivateDiagnosticsSupport](CAPLfunctionIso11783VTILActivateDiagnosticsSupport.md)) then the node also sends message DM1 with SPN=2000+nodeAddress, FMI=31 and OC=1.

This behavior can be influenced by implementing the function [VTIL_OnAddressViolation](CAPLfunctionIso11783VTILOnAddressViolation.md).

## Parameters

- **numberOfDM1Transmissions**
  - 1..0xFFFFFFFF: activates the detection of address violations
  - 0: deactivates detection of address violations

  If value is >0 and an address violation is detected and diagnostics support is activated then message DM1 is sent **numberOfDM1Transmissions** times. If **numberOfDM1Transmissions** is 0xFFFFFFFF then sending of DM1 is not stopped.

- **node**
  - Simulation node to apply the function.

## Return Values

- **0**
  - Function has been executed successfully

- **< 0**
  - An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
