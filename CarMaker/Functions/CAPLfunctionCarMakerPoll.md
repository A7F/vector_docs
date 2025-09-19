# CarMaker_Poll

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_Poll(char host[], char user[]);
```

## Description

Manages the internal state and updates the CANoe system variables. If the polling cycle is set to zero in the configuration dialog, automatic polling is disabled, and this function must be called regularly.

If the polling cycle is set in the configuration dialog, the automatic polling is enabled and calling this function is not required.

The function can also be used to get the current APO return code.

## Parameters

—

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// get the current error status
gErrorState = CarMaker_Poll();
```
