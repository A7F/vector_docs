[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetReceiverIndex.md)

**CAPL Functions** » **Communication Objects** » **GetReceiverIndex**

# GetReceiverIndex (obsolete)

**Valid for**: CANoe DE

## Method Syntax

- `long txSignalRef::GetReceiverIndex();`
- `long rxSignalRef::GetReceiverIndex();`
- `long txPDURef::GetReceiverIndex();`
- `long rxPDURef::GetReceiverIndex();`

## Description

Returns the receiver index selected for the CO reference.

## Parameters

—

## Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns the index of that endpoint. Else returns -1.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)