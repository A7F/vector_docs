[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1587/EventHandler/CAPLfunctionOnJ1587Param.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1587](../CAPLfunctionsJ1587Overview.md) » on J1587Param

# on J1587Param

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Description

Defines the event handler for a valid J1587 parameter, the `this` pointer is of type [J1587Param](../../../Shared/CAPL/General/J1587Param.md).

## Parameters

dbMsg | PID | *

## Example

**on J1587Param** TextMessageAcknowledged

```
{
  if (this.MID == gECU_MID)
  {
    if (this.MessageDisplayed == 1)
    {
      gDisplayState = kDisplayed;
    }
    else
    {
      gDisplayState = kTimeout;
    }
  }
}
```

• Technical References are only available in English

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
