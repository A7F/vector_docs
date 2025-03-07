[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionSetSignalStartValues.md)

**CAPL Functions** » **CAN** » **setSignalStartValues**

# setSignalStartValues

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `setSignalStartValues(message msg); // form 1`
- `setSignalStartValues(multiplexed_message msg); // form 2`
- `setSignalStartValues(frFrame frame); // form 3`
- `setSignalStartValues(frFrame frame, byte uninitializedData); // form 4`
- `setSignalStartValues(frPDU pdu); // form 5`
- `setSignalStartValues(frPDU pdu, byte uninitializedData); // form 6`
- `setSignalStartValues(pg paramGroup); // form 7`
- `setSignalStartValues(j1587Param param); // form 8`
- `setSignalStartValues(linFrame msg); // form 9`

## Description

Sets the values of the signals in the parameter to the start values defined in the database.

## Parameters

- **msg, frame, pdu, paramGroup, parameter**: Objects where the signals shall be set.
- **uninitializedData (Form 4, Form 6)**: Value to which the bytes in the frame / PDU shall be set which are not used by signals.

## Return Values

- **0**: function was successful
- **1**: message / frame / PDU / paramGroup wasn't found in the database
- **2**: at least one signal start value didn't fit into the signal in the message

## Example

```plaintext
message LightState msg;
setSignalStartValues(msg);
```

[StartLogging](../../Other/Functions/CAPLfunctionStartLogging.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)