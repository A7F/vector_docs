# coTfsHeartbeatConsumer (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsHeartbeatConsumer( dword virtProducerId, dword consumerTime, dword tolerance );
```

## Description

A heartbeat consumer is configured on the DUT (object 0x1016, subindex 1). The tester sends a single heartbeat message as heartbeat producer, triggering a heartbeat event for the consumer. The tester waits for an emergency message with error code 0x8130. The DUT is reset with a NMT reset command, and the test waits for the boot-up message. After this test, the device is in the pre-operational state.

## Parameters

- **virtProducerId**: This "virtual" node emulates the necessary heartbeat producer, this node number may not be assigned in the system to be tested.
- **consumerTime**: Heartbeat consumer time in ms.
- **tolerance**: Permissible tolerance (`x - (tolerance/2) <= x <= x + (tolerance/2)`) for the receipt of the emergency message.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if (coTfsHeartbeatConsumer( 122, 500, 100) != 1) { // virtProducerId, consumerTime, tolerance
  write( "hb consumer failed");
}
//after a successful test, the test node is in pre-operational state
```
