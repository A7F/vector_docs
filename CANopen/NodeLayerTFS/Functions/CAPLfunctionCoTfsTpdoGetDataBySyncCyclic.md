[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsTpdoGetDataBySyncCyclic.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsTPDOGetDataBySyncCyclic

# coTfsTPDOGetDataBySyncCyclic (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsTPDOGetDataBySyncCyclic( dword index, dword outLength[], byte outValueBuf[], dword valueBufSize );
```

## Description

This function tries to extract TPDO data using synchronous cyclic method of the test node.

**Test sequence**

- The transmission type of the TPDO is checked, the values 1..240 (synchronous) are accepted. If another value is read, 1 is set.
- It is checked if the TPDO is active.
- The test module must be in state operational, this is checked with heartbeat and guarding functions. If a heartbeat producer is active, it is overwritten and deactivated.
- The test module works as a sync producer.
- The test module waits for the TPDO data.
- After receiving the data, the event timer is set back to 0.
- If necessary, the original transmission type is set.

**Test result**

The test was successful if all parts of the tests are executed successfully. If that's the case, the TPDO data are written in `outLength[]` and `outValueBuf[]`. Otherwise the data are set invalid.

**Syntax special**

The parameters `outLength[]` and `outValueBuf[]` can be omitted both.

## Parameters

- **index**: Index of TPDO.
- **outLength[]**: Size of the TPDO in bytes.
- **outValueBuf[]**: Data of the TPDO, the array size should be 8 bytes.
- **valueBufSize**: Size of data buffer.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword outLength[1];
byte outValueBuf[8];

if (coTfsTPDOGetDataBySyncCyclic( 0x1800, outLength, outValueBuf, 8 )!= 1) {
  write("could not retrieve data ");
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)