[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerPoll.md)

[CAPL Functions](../../CAPLfunctions.md) » [CarMaker Interface](../CAPLfunctionsCarMakerOverview.md) » CarMaker_Poll

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)