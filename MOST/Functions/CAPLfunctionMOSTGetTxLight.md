[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetTxLight.md)

**CAPL Functions** » **MOST** » **mostGetTxLight**

# mostGetTxLight

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long mostGetTxLight(long channel);
```

## Description

Queries the Light Status at the Fiber Optical Transmitter (FOR).

## Parameters

- **channel**: Channel of the interface to be queried.

## Return Values

- **0**: Light out
- **1**: Modulated light
  - Bypass/Slave: Tx has light modulation of the Rx
  - Master: Master light
- **2**: Constant light
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostSetTxLight](CAPLfunctionMOSTSetTxLight.md) • [mostGetRxLight](CAPLfunctionMOSTGetRxLight.md) • [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [OnMostTxLight](../EventProcedures/CAPLfunctionOnMOSTTXLight.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
