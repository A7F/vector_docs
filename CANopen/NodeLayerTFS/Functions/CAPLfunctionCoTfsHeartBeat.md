# coTfsHeartbeat (Level 3)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsHeartbeat( dword virtProducerId );
```

## Description

This function tests the heartbeat consumer and heartbeat producer of the DUT (Device Under Test) with two different time settings.

First, the heartbeat producer is tested for regularity. The test duration is 10 seconds in each case. The heartbeat time is set to 1sec and after that, 200 ms. The tolerance is 10 or 20%. After that, the heartbeat consumer is tested with a cycle time of 1sec and a tolerance of 10 % and 5%.

The test uses internally the functions [coTfsHeartbeatConsumer](CAPLfunctionCoTfsHeartbeatConsumer.md) and [coTfsHeartbeatProducer](CAPLfunctionCoTfsHeartbeatProducer.md).

After this test, the target device is in the pre-operational state.

## Parameters

- **virtProducerId**: Virtual heartbeat producer, this node may not exist in the test setup.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsHeartbeat( 2 ) != 1) {
  write ( "heartbeat test failed" );
}
```
