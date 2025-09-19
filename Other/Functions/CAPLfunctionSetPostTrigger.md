[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetPostTrigger.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setPostTrigger

# setPostTrigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
setPostTrigger(long PostTriggerTime);
```

## Description

Sets the posttrigger of the logging. The posttrigger set with this function is valid until the end of the measurement or until the next call of this function.

**Note**: The function [stopLogging()](CAPLfunctionStopLogging.md) does not consider the setting with function ‘`setPostTrigger`’, use the CAPL function [trigger()](CAPLfunctionTrigger.md) instead.

## Parameters

- New posttrigger value in milliseconds.
- If a value of -1 is supplied, the prosttrigger will be set to infinity.

## Return Values

- **1**: if the posttrigger is set to the given value
- **0**: else

## Example

```plaintext
on start
{
  SetPreTrigger(5000);
  SetPostTrigger(5000);
}

on key 'x'
{
  //start and stop of all CAPL trigger/Logging blocks with pre and post trigger settings
  trigger();
}
```

[setPreTrigger](CAPLfunctionSetPreTrigger.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
