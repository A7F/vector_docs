[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetPreTrigger.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setPreTrigger

# setPreTrigger

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
setPreTrigger(long preTriggerTime);
```

## Description

Sets the pretrigger of the logging. The pretrigger set with this function is valid until the end of the measurement or until the next call of this function.

**Note**: The function [startLogging()](CAPLfunctionStartLogging.md) does not consider the setting with function `setPreTrigger`, use the CAPL function [trigger()](CAPLfunctionTrigger.md) instead.

## Parameters

- New pretrigger value in milliseconds.

## Return Values

- **1**: if the pretrigger is set to the given value
- **0**: else

## Example

```c
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

[Next Topic](CAPLfunctionSetPostTrigger.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
