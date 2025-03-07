[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMessageTimeNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » MessageTimeNS

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)