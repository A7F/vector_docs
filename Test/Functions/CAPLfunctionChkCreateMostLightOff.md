[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMostLightOff.md)

**CAPL Functions** » **Test Service Library** » **Checks** » **ChkCreate_MostLightOff, ChkStart_MostLightOff**

# ChkCreate_MostLightOff, ChkStart_MostLightOff

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `dword ChkCreate_MostLightOff();`
- `dword ChkStart_MostLightOff();`
- `dword ChkCreate_MostLightOff(Callback aCallback);`
- `dword ChkStart_MostLightOff(Callback aCallback);`

## Constructor

- `TestCheck::CreateMostLightOff();`
- `TestCheck::StartMostLightOff(Callback aCallback);`
- `TestCheck::StartMostLightOff();`
- `TestCheck::CreateMostLightOff(Callback aCallback);`

## Check Name

[MOST Light & Lock Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTLightLockObservation.md)

## Description

The check function monitors the occurrence of "LightOff" events. A "LightOff" event occurs if the hardware connected to the channel no longer receives light at the input.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aCallback**: Name of the callback function, which should be called as soon as a "LightOff" event occurs. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- CAPL callback does not exist.

## Example

—

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)