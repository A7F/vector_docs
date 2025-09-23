[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetRxBufferCtrl.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetRxBufferCtrl

# mostSetRxBufferCtrl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

This functionality is only available for:

- VN2640
- VN2600/VN2610
- OptoLyzerOL3150o (firmware version >= V1.5.3)
- OptoLyzerOl3050e (firmware version >= V1.5)

## Function Syntax

```plaintext
long mostSetRxBufferCtrl(long channel, long mode);
```

## Description

Disables or enables the Rx buffer for messages of the control channel.

In case the parameter mode is set to '0' or '1' the result is reported by means of the callback function [OnMostStress()](../EventProcedures/CAPLfunctionOnMOSTStress.md).

Disabling the Rx buffer means that exactly one more message is accepted. Afterwards the buffer is no longer enabled, i.e. further messages are rejected with "RxBuffer full" (see status flags of Tx acknowledgment).

After the measurement start the receive buffer is always enabled.

**VN2640:**

Disabling the Rx buffer means that up to four control messages will be accepted, before the buffer is disabled and low level retries on the bus are provoked.

**OptoLyzerOL3150o:**

The stress network interface controller (NIC) must have its bypass opened (see [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)). Only messages addressed to the StressNIC will be blocked.

## Parameters

- **channel**: Channel of the connected interface
- **mode**:
  - **0**: Disable receive buffer
  - **1**: Enable receive buffer
  - **2**: Enable receive buffer exactly once for one message

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetRxBufferAsync](CAPLfunctionMOSTSetRxBufferAsync.md)
