[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTNwmFiSetConfigState.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostNwmFiSetConfigState

# mostNwmFiSetConfigState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostNwmFiSetConfigState(long state, long sendConfigStatusMsg);
```

## Description

Forces the network configuration status to be set in CANoe’s NetworkMaster.

Use the function with care since the state machine of the NetworkMaster is not guaranteed to work properly afterwards. (A shutdown of the network will reset the NetworkMaster’s state machine.)

The function is available for CAPL programs assigned to the NetworkMaster block in the Simulation Setup.

## Parameters

- **state**  
  - 0: ConfigNotOk
  - 1: ConfigOK

- **sendConfigStatusMsg**  
  - 0: set the configuration status without sending a message
  - 1: set configuration status and broadcast NetworkMaster.Configuration.Status

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[OnMostFiAmsPreSend](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreSend.md) • [OnMostFiAmsPreReceive](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreReceive.md) • [mostNwmFiEnableRingScan](CAPLfunctionMOSTNwmFiEnableRingScan.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
