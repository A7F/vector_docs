[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/E2EProtection/CAPLfunctionARE2ECalculateCRC.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » ARE2ECalculateCRC

# ARE2ECalculateCRC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ARE2ECalculateCRC (PDU * aPDU, char sigGroupName[], qword & crc, long & crcSizeInBit);
```

## Description

Calculates the corresponding checksum and the CRC size (in bits) from a PDU. It is necessary that the PDU has a valid E2E.

## Parameters

- **aPDU**: A referenced PDU object.
- **sigGroupName**: The name of the signal group or empty. If empty, then the E2E should be directly defined at the PDU instead of the signal group.
- **crc**: The calculated CRC value.
- **crcSizeInBit**: The size of the CRC in bit (8, 16, 32, 64 bit).

## Return Values

- **0**: Successful
- **-1**: Not successful: PDU not found in database
- **-2**: Not successful: There is no signal group with the defined Name in the PDU or there is no E2E protection information defined for the signal group/PDU
- **-3**: Not successful: The CRC value could not be calculated

## Example

```plaintext
on PDU <PDU_NAME>
{
  qword crc;
  long crcSizeInBit;
  ARE2ECalculateCRC (this, "", crc, crcSizeInBit);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
