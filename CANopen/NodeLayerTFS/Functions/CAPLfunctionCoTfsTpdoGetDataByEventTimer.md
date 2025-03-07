[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsTpdoGetDataByEventTimer.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsTPDOGetDataByEventTimer

# coTfsTPDOGetDataByEventTimer (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsTPDOGetDataByEventTimer( dword index, dword outLength[], byte outValueBuf[], dword valueBufSize );
```

## Description

This function reads the TPDO data via an event timer mechanism.

**Test sequence**

- The transmission type of the TPDO is checked, the values 0xFF (asynchronous, device profile specific) and 0xFE (asynchronous, manufacturer specific) are accepted. If another value is read, 0xFF is set.
- It is checked if the TPDO is active.
- The test module must be in state operational, this is checked with heartbeat and guarding functions. If a heartbeat producer is active, it is overwritten and deactivated.
- The event timer is set to 20 ms.
- The test module waits for the transmission of the first PDO for synchronization purposes. Afterwards the event timer evaluation starts with a tolerance of 20 ms.
- If the process is successful (return value 1), the read data are written in **outLength[]** and **outValueBuf[]**.
- If necessary, the original transmission type is set.

**Test result**

The test was successful if all parts of the tests are executed successfully. If that's the case, the TPDO data are written in **outLength[]** and **outValueBuf[]**. Otherwise the data are set invalid.

**Syntax special**

The parameters **outLength[]** and **outValueBuf[]** can be omitted both.

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

if (coTfsTPDOGetDataByEventTimer(0x1800, outLength, outValueBuf, 8) != 1) {
  write("could not retrieve data");
} // if
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)