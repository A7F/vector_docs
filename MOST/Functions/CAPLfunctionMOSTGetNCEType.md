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
