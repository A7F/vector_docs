[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetSender.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetSender

# GetSender (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `COParticipant txSignalRef::GetSender();`
- `COParticipant rxSignalRef::GetSender();`
- `COParticipant txPDURef::GetSender();`
- `COParticipant rxPDURef::GetSender();`

## Description

Returns the sender participant selected for the CO reference.

## Parameters

—

## Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns a reference to that participant. Else returns an invalid reference.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)