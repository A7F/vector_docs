[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoChkCrcSupport.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSDOChkCrcSupport**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)