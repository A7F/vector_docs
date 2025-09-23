[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/E2EProtection/CAPLfunctionCrcCalculateCRC8H2F.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » Crc_CalculateCRC8H2F

# Crc_CalculateCRC8H2F

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long Crc_CalculateCRC8H2F (byte data[], dword dataSize, dword dataOffset, dword crcLength, dword crcStartValue, dword firstCall, dword& crcCalculated);
```

## Description

Calculates the corresponding checksum for CRC8H2F based on the data. The calculation of the CRC value corresponds to AUTOSAR Profile 2.

## Parameters

- **data**: Payload data for which the checksum is to be calculated.
- **dataSize**: Length of data block to be calculated in bytes.
- **dataOffset**: Start index for the calculation of the CRC in the payload data.
- **crcLength**: The length of the data for the CRC is calculated.
- **crcStartValue**: CRC initial value depending on whether it is the first call or a subsequent call. Value is ignored if **firstCall** is **1**.
- **firstCall**: Flag for first call or a subsequent call. Possible values are **0** (subsequent call) or **1** (first call).
- **crcCalculated**: Calculated CRC8H2F value.

## Return Values

- **0**: Successful
- **-1**: Not successful: CRC length must not be 0
- **-2**: Not successful: Offset must not be greater or equal length
- **-3**: Not successful: Length outside array range
- **-4**: Not successful: Summary of Length and offset are outside array range

## Example

```plaintext
on key '2'
{
  // Example from AUTOSAR_PRS_E2EProtocol.pdf
  //
  // E2E Protocol Specification
  // AUTOSAR FO R20-11
  // Table 6.28: E2E Profile 2 example protect result

  long  result;
  dword calculatedCRC;
  byte  seq;
  dword dataLength;
  long res;
  byte  data[8] = {
  // CRC| Payload
  0x1B  ,0x01,0x00,0x00,0x00,0x00,0x00,0x00
  };
  byte dataIDs[16] = { 0x01, 0x02, 0x03, 0x04,0x05, 0x06, 0x07, 0x08,0x09, 0x0a, 0x0b, 0x0c,0x0d, 0x0e, 0x0f, 0x10 };  dataLength = elcount(data);

  seq = data[1] & 0x0F;
  res = Crc_CalculateCRC8H2F( data   , dataLength, 1  , dataLength-1,  0xFF, 1, calculatedCRC );
  res = Crc_CalculateCRC8H2F( dataIDs, 16        , seq,          1,  calculatedCRC, 0, calculatedCRC );

  write( "calculatedCRC=0x%X (expect0x1B)", calculatedCRC );
}
```
