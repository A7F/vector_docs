# coTfsTPDOGetDataByRTR (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsTPDOGetDataByRTR( dword index, dword outLength[], byte outValueBuf[], dword valueBufSize );
```

## Description

The function sends a remote frame with the given CAN-ID. The tested node answers with the corresponding TPDO data.

**Test sequence**

- The transmission type of the TPDO is checked, the values 0xFF (asynchronous, device profile specific) and 0xFE (asynchronous, manufacturer specific) are accepted. If another value is read, 0xFF is set.
- The test module must be in state operational, this is checked with heartbeat and guarding functions. If a heartbeat producer is active, it is overwritten and deactivated.
- It is checked if the TPDO is active and supports RTRs.
- The CAN-ID is read and a remote frame is sent.
- If the process is successful (return value 1), the read data are written in **outLength** and **outValueBuf[]**.
- If necessary, the original transmission type is set.

**Test result**

The test was successful if all parts of the tests are executed successfully. If that's the case, the TPDO data are written in **outLength** and **outValueBuf[]**. Otherwise, the data are set invalid.

**Syntax special**

The parameters **outLength** and **outValueBuf[]** can be omitted both.

## Parameters

- **index**: Index of TPDO.
- **outLength[]**: Size of the TPDO in bytes.
- **outValueBuf[]**: Data of the TPDO, the array size should be 8 bytes.
- **valueBufSize**: Size of buffer.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword outLength[1];
byte outValueBuf[8];

if (coTfsTPDOGetDataByRTR(0x1800, outLength, outValueBuf, 8) != 1) {
  write("could not retrieve data");
}
```
