[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxReleasePacket.md)

**CAPL Functions** » **AFDX** » **AfdxReleasePacket**

# AfdxReleasePacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxReleasePacket( long packet );
```

## Description

This function deletes a packet created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md). The handle can not be used any longer.

## Parameters

- **packet**: Handle of the message to delete.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

See example of [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)