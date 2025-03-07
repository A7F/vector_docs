[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetRespError.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetRespError

# linGetRespError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linGetRespError(); // form 1
long linGetRespError(long NAD); // form 2
```

## Description

With this function it’s possible to query the response error flag of the calling Slave node or of the Slave node specified by its node address (NAD) as last seen on the LIN bus.

## Parameters

- **NAD**: Configured node address of the Slave node to be queried.

## Return Values

Returns one if the queried response_error flag is set, zero if it is not set and -1 if it has not been sent yet.

## Example

—

[linCheckRespError](CAPLfunctionLINCheckRespError.md) • [linSetRespError](CAPLfunctionLINSetRespError.md) • [linActivateGlobalNetworkManagement](CAPLfunctionLINActivateGlobalNetworkManagement.md) • [linActivateSlaveNetworkManagement](CAPLfunctionLINActivateSlaveNetworkManagement.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)