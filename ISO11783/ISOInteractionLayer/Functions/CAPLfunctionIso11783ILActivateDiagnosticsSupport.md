[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILActivateDiagnosticsSupport.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_ActivateDiagnosticsSupport**

# Iso11783IL_ActivateDiagnosticsSupport

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_ActivateDiagnosticsSupport(byte enable); // form 1
long Iso11783IL_ActivateDiagnosticsSupport(dbNode node, byte enable); // form 2
```

## Description

This function activates or deactivates the support of ISO11783 diagnostics by the IL.

If diagnostics support is activated the node:

- sends message DM1 cyclically if any error is active
- sends message DM2 if DM2 is requested
- clears all previously active DTCs if DM3 is requested

If diagnostics support is activated then diagnostics message which are in the Tx list of the node are disabled and therefore not used by the IL.

## Parameters

- **enable**: Enables or disables support of ISO11783 diagnostics:
  - 0: Disable support of ISO11783 diagnostics
  - 1: Enable support of ISO11783 diagnostics

- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
