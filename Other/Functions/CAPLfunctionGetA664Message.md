[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetA664Message.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetA664Message

# GetA664Message

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GetA664Message (PDUobject aPDU, a664Message aMessage);
```

## Description

This function can be used within an "ON PDU"-handler to retrieve the A664Message object, to which the PDU corresponds.

The a664Message object then allows to retrieve the various runtime parameters like BAG or error flags via message selectors.

**Note**: the message ID is available, but not the message name.

## Parameters

- **`<aPDU>`**: The `<this>` object of the PDU-handler
- **<aMessage>**: The a664Message object which getting the current message information

## Return Values

- **<success> - 0**: Information about corresponding message was successfully retrieved
- **-1**: Wrong bus system (callback not from an AFDX channel)
- **-3**: PDU-object (this) not of correct type or not initialized properly
- **-6**: Frame or PDU not available

## Example

```plaintext
on PDU *
{
  A664Message *msg;
  getA664Message(this, msg);
  writeEx(-3,1, "received PDU %s with distance: %d", this.name, msg.Distance);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)