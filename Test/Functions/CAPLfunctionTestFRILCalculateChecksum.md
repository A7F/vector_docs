[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestFRILCalculateChecksum.md)

**CAPL Functions** » **CANoe IL** » **TestFRILCalculateChecksum**

# TestFRILCalculateChecksum

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestFRILCalculateChecksum (char pduNamme[], long  type, BYTE payload[], long payloadLength, BYTE crc []);
```

## Description

Calculates the corresponding CRC checksum based on the payload. The correct offset is calculated from the database using the PDU name.

**Note**  
Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **pduName**: Name of the PDU.
- **type**:
  - type = 0 : CRC
  - type = 1 : CHK
- **payload**: Payload for which the checksum is to be calculated.
- **payloadLength**: Number of data bytes in payload.
- **crc**: The calculated checksum.

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

—

[ILCalculateChecksum](../../CANoeIL/Functions/CAPLfunctionILCalculateChecksum.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
