[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTLightLockError.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » on mostLightLockError

# on mostLightLockError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`on mostLightLockError;`

## Description

On controller events `on mostLightLockError` is called. Light, Lock and Error events will be forwarded automatically.

If the event procedure should only react to events on channel 1 this is defined as follows:

`on MsgChannel1.mostLightLockError`

## Parameters

—

## Return Values

—

## Example

—

[mostGetRxLight](../Functions/CAPLfunctionMOSTGetRxLight.md) • [mostGetLock](../Functions/CAPLfunctionMOSTGetLock.md) • [OnMostTxLight](CAPLfunctionOnMOSTTXLight.md) • [mostLightLockError - Selectors](../Selectors/CAPLfunctionMOSTSelectors.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
