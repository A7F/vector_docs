[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/E2EProtection/CAPLfunctionCrcCalculateCRC64.md)

## Crc_CalculateCRC64

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » Crc_CalculateCRC64

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
long Crc_CalculateCRC64 (byte data[], dword dataSize, dword dataOffset, dword crcLength, qword crcStartValue, dword firstCall, qword& crcCalculated);
```

### Description

Calculates the corresponding checksum for CRC64 based on the data. The calculation of the CRC value corresponds to AUTOSAR Profile 7.

### Parameters

- **data**: Payload data for which the checksum is to be calculated.
- **dataSize**: Length of data block to be calculated in bytes.
- **dataOffset**: Start index for the calculation of the CRC in the payload data.
- **crcLength**: The length of the data for the CRC is calculated.
- **crcStartValue**: CRC initial value depending on whether it is the first call or a subsequent call. Value is ignored if **firstCall** is **1**.
- **firstCall**: Flag for first call or a subsequent call. Possible values are **0** (subsequent call) or **1** (first call).
- **crcCalculated**: Calculated CRC64 value.

### Return Values

- **0**: Successful
- **-1**: Not successful: CRC length must not be 0
- **-2**: Not successful: Offset must not be greater or equal length
- **-3**: Not successful: Length outside array range
- **-4**: Not successful: Summary of Length and offset are outside array range

### Example

```plaintext
// first CALL, Offset '0'
on key 'a'
{
  long  retval;
  qword crc;
  byte  data[9] = {0x31, 0x32, 0x33, 0x34, 0x35, 0x36, 0x37, 0x38, 0x39};

  retval = Crc_CalculateCRC64(data, elcount (data), 0, elcount (data), 0, 1, crc);
  write("CRC of data: 0x%I64X", crc);
}

// first CALL, Offset '2', Length - 2
on key 'b'
{
  long  retval;
  qword crc;
  byte  data[11] = {0xAA ,0xAA,0x31, 0x32, 0x33, 0x34, 0x35, 0x36, 0x37, 0x38, 0x39};

  retval = Crc_CalculateCRC64(data, elcount (data), 2, elcount (data) -2, 0, 1, crc);
  write("CRC of data: 0x%I64X", crc);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
