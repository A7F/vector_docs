# QueueSerialMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- **PSI5 Protocol**  
  This method can only be called on system variable namespaces of time slots belonging to the namespace SENSOR::PSI5.
- **SENT Protocol**  
  This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Method Syntax

SensorErrorCode SysVarNamespace.QueueSerialMessage(dword messageId, dword useLongMessageId);

## Description

Inserts the given serial message into the send queue of the given time slot (PSI5)/channel (SENT).

Please note that the actual data of the message is not specified in this function call. Instead, it will be taken from any signal system variables defined in the Sensor configuration dialog for this serial message ID.

## Parameters

- **messageId**  
  Specifies the ID of the serial message. If **useLongMessageId** is set to TRUE, the message ID is 8 bits long. Otherwise, the message ID is 4 bits long.

- **useLongMessageId**  
  If set to TRUE, the message will have an 8-bit ID and 12 bits of payload data. If set to FALSE, the message will have a 4-bit ID and 16 bits of payload data.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

**Example PSI5**

```plaintext
// Send serial message with ID 15 (4 bit ID, 16 bit data)
sysvar::SENSOR::PSI5::ExampleChannel::ExampleSensor::ExampleTimeslot.QueueSerialMessage(0x15, 0);
```

**Example SENT**

```plaintext
// Send serial message with ID 15 (4 bit ID, 16 bit data)
sysvar::SENSOR::SENT::ExampleChannel.QueueSerialMessage(0x15, 0);
```
