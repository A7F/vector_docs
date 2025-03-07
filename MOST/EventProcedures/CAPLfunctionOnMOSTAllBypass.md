[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTAllBypass.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostAllBypass

# OnMostAllBypass

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostAllBypass(long mode);
```

## Description

The event procedure `OnMostAllBypass` is called if the bypass of the MOST chip was opened or closed. The variable **mode** contains the new state.

Supplemental information can be called up within this procedure by the [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) functions.

Controller events are passed through CAPL nodes. Please use the Multibus filter or MOST Filter to filter these events in node chains.

## Parameters

- **mode**  
  0: The bypass is opened.  
  1: The bypass is closed. The MOST hardware is transparent to other devices on the ring.

## Return Values

—

## Example

—

[mostSetAllBypass](../Functions/CAPLfunctionMOSTSetAllBypass.md) • [mostGetAllBypass](../Functions/CAPLfunctionMOSTGetAllBypass.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)