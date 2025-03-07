[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTNwmFiSetGetParameter.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostNwmFiSetParameter, mostNwmFiGetParameter

# mostNwmFiSetParameter, mostNwmFiGetParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostNwmFiSetParameter(long paramID, long value);
long mostNwmFiGetParameter(long paramID);
```

## Description

In order to modify timing parameters, the functions `mostNwmFiSetParameter` and `mostNwmFiGetParameter` provide access to the timing parameters of CANoe’s NetworkMaster implementation.

Use the function with care since the state machine of the NetworkMaster is not guaranteed to work properly afterwards.

Refer to the MOST specification for a detailed description of the timing parameters and the NetworkMaster state machine.

The function is available for CAPL programs assigned to the NetworkMaster block in the Simulation Setup.

## Parameters

- **paramID**
  - `-1`: set default for all parameter values
  - `1`: timer value tWaitBeforeScan (value range: 1…20000 ms)
  - `2`: timer value tWaitAfterNCE (value range: 1…20000 ms)
  - `3`: timer value tWaitForAnswer (value range: 1…20000 ms)
  - `4`: timer value tDelayCfgRequest1 (value range: 1…200000 ms)
  - `5`: timer value tDelayCfgRequest2 (value range: 1…200000 ms)

- **value**
  - New value to be set.

## Return Values

- **mostNwmFiSetParameter**
  - See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

- **mostNwmFiGetParameter**
  - `>=0`: value of the parameter identified by paramID

## Example

```plaintext
// set the timer value for tDelayCfgRequest2 to 15 s
mostNwmFiSetParameter(5, 15000);
```

[OnMostFiAmsPreSend](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreSend.md) • [OnMostFiAmsPreReceive](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreReceive.md) • [mostNwmFiEnableRingScan](CAPLfunctionMOSTNwmFiEnableRingScan.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)