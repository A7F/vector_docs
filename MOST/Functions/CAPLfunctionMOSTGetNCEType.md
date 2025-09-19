[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetNCEType.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetNceType

# mostGetNceType

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long mostGetNceType();
```

## Description

Returns the type of network change event (NCE) (when changing the MPR register).

**Note**: This function can only be called within the [OnMostMPR()](../EventProcedures/CAPLfunctionOnMOSTMPR.md) event procedure.

## Parameters

—

## Return Values

- **< 0**: NCE-. The absolute value corresponds to the number of devices which closed their bypass.
- **0**: No information available (e.g. first MPR register event, the function was not called in the [OnMostMPR()](../EventProcedures/CAPLfunctionOnMOSTMPR.md) event procedure).
- **> 0**: NCE+. The value corresponds to the number of devices which opened their bypass.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
