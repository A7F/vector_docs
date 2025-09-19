[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLFunctionMOSTSetGetRetryParameter.md)

CAPL Function Overview » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetRetryParameter, mostGetRetryParameter

# mostSetRetryParameter, mostGetRetryParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostSetRetryParameter(long channel, long id, long value);`
- `long mostGetRetryParameter(long channel, long id);`

## Description

The functions provide access to the transceiver chip parameters for message transmission. The number of low-level transmission attempts and delay between attempts can be set and retrieved.

## Parameters

- **channel**: Channel of the connected interface.
- **id**: Parameter identification (see table below).

  - **ID 0**: Transmission attempts on the control channel.
    - VN26x0 (MOST25): 1..255
    - VN2640 (MOST150): 1..16
    - OptoLyzer G2 3150o (MOST150): 1..16

  - **ID 1**: Time between send retries on the control channel.
    - VN26x0 (MOST25): 3..255
    - VN2640 (MOST150): 3..31
    - OptoLyzer G2 3150o (MOST150): 3..15

  - **ID 2**: Transmission attempts on the asynchronous channel.
    - VN2640 (MOST150): 1..16
    - OptoLyzer G2 3150o (MOST150): 1..16

  - **ID 3**: Time between send retries on the asynchronous channel.
    - VN2640 (MOST150): 0..255
    - OptoLyzer G2 3150o (MOST150): 0..255

- **value**: Value to be set.

## Return Values

- **mostSetRetryParameter**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md).
- **mostGetRetryParameter**:
  - `>=0`: Retry parameter value.
  - `<0`: See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

```c
// configure MOST transceiver for 5 low-level transmission attempts on Control channel
mostSetRetryParameter(1, 0, 5);
```

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [output](CAPLfunctionMOSToutput.md) • [mostReadReg](CAPLfunctionMOSTReadReg.md) • [OnMostReg](../EventProcedures/CAPLfunctionOnMOSTReg.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
