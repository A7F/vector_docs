[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFShdFunctionEnableCAPLfunctionMOSTAsNTFShdFunctionDisable.md)

**CAPL Functions** » **MOST** » **mostAsNtfShdFunctionEnable, mostAsNtfShdFunctionDisable**

# mostAsNtfShdFunctionEnable, mostAsNtfShdFunctionDisable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAsNtfShdFunctionEnable(long fblockId, long instId, long functionId);
long mostAsNtfShdFunctionDisable(long fblockId, long instId, long functionId);
```

## Description

`mostAsNtfShdFunctionEnable()` registers a MOST function with the notification shadow service. As soon as the specified function block (fblockId, instId) appears in the bus registry of the simulated device, the [notification shadow service](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketNotificationShadowService.md) enters the simulated device in the notification matrix of the function block, i.e., it sends the FBlockId.InstId.Notification.Set(SetFunction, functionId) message.

`mostAsNtfShdFunctionDisable()` removes a MOST function from the notification shadow service.

## Parameters

- **fblockId**: Function block ID
- **instId**: Instance ID
- **functionId**: Function ID of a "Property" type function.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostAsShdEnable, mostAsShdDisable](CAPLfunctionMOSTAsShdEnableCAPLfunctionMOSTAsShdDisable.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)