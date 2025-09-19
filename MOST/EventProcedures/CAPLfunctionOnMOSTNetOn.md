[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTNetOn.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostNetOn / OnMostInitReady

# OnMostNetOn / OnMostInitReady

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `OnMostNetOn();`
- `OnMostInitReady();`

## Description

The NetOn event (first "Stable Lock" after the loop has been woken up) has occurred on one of the configured MOST channels. The relevant channel or time stamp of this event can be called up with the [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md), and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) functions.

**Note**

In the **MOST Specification 3V0** the **NetOn** event was renamed to **InitReady**. However, the meaning is still the same. The Trace Window displays this information in the disassembly column and the detail view. In CAPL there is an additional event procedure OnMostInitReady (**since version 7.2**). To assure the correct operation of existing CAPL programs, the event handler OnMostNetOn is still called.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

## Parameters

—

## Return Values

—

## Example

—

[OnMostStableLock](CAPLfunctionOnMOSTStableLock.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
