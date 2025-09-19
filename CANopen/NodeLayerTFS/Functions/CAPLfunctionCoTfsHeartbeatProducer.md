# coTfsHeartbeatProducer (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsHeartbeatProducer( dword duration, dword producerTime, dword tolerance );
```

## Description

This function activates the heartbeat producer of the DUT. For this the object 0x1017 with `producerTime` is described via a SDO write access. After this, the regularity of the heartbeat message is checked and then the heartbeat producer is switched off again (0x1017 = 0). The test duration must be greater than the permitted time deviation.

At least two heartbeat messages of the DUT are awaited, even if the test duration is set shorter.

## Parameters

- **duration**: Test duration in ms, how long the regularity of the heartbeat producer should be tested.
- **producerTime**: Heartbeat producer time in ms.
- **tolerance**: Permitted time deviation of the DUT in ms. It is recommended that you use an even value. The tolerated time-frame within which a message is still accepted is: `x - (tolerance/2) <= x <= x + (tolerance/2)`

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if (coTfsHeartbeatProducer( 3000, 500, 10) != 1) { // duration, producerTime, tolerance
  write("heartbeat producer test failed");
}
```
