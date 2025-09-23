# MessageTimeNS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `float MessageTimeNS(message msg); // from 1`
- `float MessageTimeNS(linFrame msg); // from 2`
- `float MessageTimeNS(mostMessage msg); // from 3`
- `float MessageTimeNS(mostAmsMessage msg); // from 4`
- `float MessageTimeNS(mostRawMessage msg); // from 5`

## Description

Returns the time stamp in nanoseconds.

The time stamp that can be polled with this function has a greater precision than the **msg**.TIME time stamp, whereby the precision depends on the CAN or LIN hardware that is being used.

## Parameters

- **message**: CAN message
- **linFrame**: LIN frame
- **mostMessage, mostAmsMessage, mostRawMessage**: MOST message

## Return Values

Time stamp of the message in ns.

## Example

—

[MessageTimeNS (FlexRay)](../../FlexRay/Functions/CAPLfunctionMessageTimeNS.md) • [EnvVarTimeNS](CAPLfunctionEnvVarTimeNS.md) • [timeNowNS](CAPLfunctionTimeNowNS.md) • [Message Selector TIME](../../CAN/CAPLfunctionMessageSelectors.md)
