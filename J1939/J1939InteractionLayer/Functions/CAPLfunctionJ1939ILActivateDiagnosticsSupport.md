[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILActivateDiagnosticsSupport.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILActivateDiagnosticsSupport

# J1939ILActivateDiagnosticsSupport

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILActivateDiagnosticsSupport(byte enable); // form 1
long J1939ILActivateDiagnosticsSupport(dbNode node, byte enable); // form 2
```

## Description

This function activates or deactivates the support of J1939 diagnostics by the IL.

If diagnostics support is activated the node:

- sends message DM1 always cyclically
- sends message DM2 if DM2 is requested
- clears all previously active DTCs if DM3 is requested
- clears all active DTCs if DM11 is requested
- sends configured diagnostics messages if they are requested

If diagnostics support is activated then diagnostics message which are in the Tx list of the node are disabled and therefore not used by the IL.

## Parameters

- **enable**: Enables or disables support of J1939 diagnostics:
  - 0: Disable support of J1939 diagnostics
  - 1: Enable support of J1939 diagnostics

- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
