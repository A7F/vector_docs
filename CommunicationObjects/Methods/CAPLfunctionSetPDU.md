[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionSetPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SetPDU

# SetPDU (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `long consumedPDURef::SetPDU(PDU pdu); // form 1`
- `long providedPDURef::SetPDU(PDU pdu);`
- `long pduConsumerRef::SetPDU(PDU pdu);`
- `long pduProviderRef::SetPDU(PDU pdu);`
- `long txPDURef::SetPDU(PDU pdu); // form2`
- `long rxPDURef::SetPDU(PDU pdu);`

## Description

Sets the referred-to PDU for the CO reference.

## Parameters

- **pdu**: The new PDU. Note that this must be a communication object from a [data source](../../../CANoeCANalyzer/Windows/CommunicationSetup/ComSetupDataSources.md) of the new [communication concept](../../../CANoeCANalyzer/CommunicationConcept/CC.md).

## Return Values

- **0**: Success
- **3**: Given PDU doesn’t have the correct type
- **-1**: Given reference is invalid

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)