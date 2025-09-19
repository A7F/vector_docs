# coTfsSDOChkCrcSupport (Level 1)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```
dword coTfsSDOChkCrcSupport( void );
```

## Description

The call of this function after receipt of a SDO initiate upload/download response ([coTfsSDOBlockInit](CAPLfunctionCoTfsSdoBlockInit.md)) returns the information whether the SDO server supports block transfers with CRC checksums.

## Parameters

—

## Return Values

- **0**: CRC not supported
- **!=0**: CRC supported

## Example

See example of [coTfsSDOGetBlockSize](CAPLfunctionCoTfsSdoGetBlockSize.md)
