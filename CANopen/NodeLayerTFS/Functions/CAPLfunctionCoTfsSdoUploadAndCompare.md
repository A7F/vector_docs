# coTfsSDOUploadAndCompare (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

- `long coTfsSDOUploadAndCompare( dword index, dword subIndex, dword size, byte inValueBuf[], dword valueBufSize, byte inMaskBuf[], dword maskBufSize, dword useBitMask ); // form 1`
- `long coTfsSDOUploadAndCompare( dword index, dword subIndex, dword size, byte inValueBuf[], dword valueBufSize, byte inMaskBuf[], dword maskBufSize ); // form 2`
- `long coTfsSDOUploadAndCompare( dword index, dword subIndex, dword size, byte inValueBuf[][], dword valueBufSize ); // form 3`
- `long coTfsSDOUploadAndCompare( dword index, dword subIndex, dword size, qword inValue ); // form 4`
- `long coTfsSDOUploadAndCompare( dword index, dword subIndex, dword size, qword inValue, qword mask ); // (5)`

## Description

This function executes a complete SDO upload. Depending on the number of data, this is either an [expedited upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoUpload.md) (up to 4 bytes) or a [segmented transfer](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSdoUpload.md). Afterwards the received data is compared against the data supplied.

It is not possible to fetch the received data using [coTfsGetSdoUploadData](CAPLfunctionCoTfsSdoGetUploadData.md) after this function was called.

(4) and (5) can be used for maximum 4 byte objects only.

## Parameters

- **index**: Object index
- **subindex**: Object subindex
- **size**: Expected data length.
- **inValueBuf[]**: Data pointer for expected data.
- **valueBufSize**: Buffer size in byte of **inValueBuf**.
- **inMaskBuf[]**: Data pointer for compare data.
- **maskBufSize**: Buffer size in byte of **inMaskBuf**.
- **useBitMask**:
  - 0: don't use bitmask for comparison
  - !=0: use bitmask for comparison
- **inValue**: Data to be compared.
- **mask**: Mask that is used for comparison.

## Return Values

- [error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md) or
  - 0: data mismatch
  - 1: supplied data matches received data
  - 2: data length mismatch

## Example

```c
dword dataLength = 2;
byte compareMask[2];
byte receiveData[2];
receiveData[0] = 0x01;
receiveData[1] = 0x02;
compareMask[0] = 0x0F; /* compare only lower nibble of byte 0 */
compareMask[1] = 0xFF; /* compare complete byte 1 */

if (coTfsSDOUploadAndCompare( 0x1017, 0x2, dataLength, receiveData, 2, compareMask, 2, 1 ) != 1)
{
  write(" SDO upload failed or data mismatch");
}
```
