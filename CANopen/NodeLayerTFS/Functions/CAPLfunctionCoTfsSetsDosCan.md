[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSetsDosCan.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSetSDOScan**

# coTfsSetSDOScan (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSetSDOScan( byte outBufDetected[], dword outBufSize );
```

## Description

This functions performs a SDO upload of the mandatory object 0x1000 to detect if a CANopen® device is available. The available devices will be added to the test report. For each found node the value of **outBufDetected[node-ID-1]** is set to 1, else to 0. Thus the size of the buffer should match the number of available node-IDs of the device profile at a minimum.

## Parameters

- **outBufDetected**: Buffer for registering the found nodes.
- **outBufSize**: Size of buffer.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword outBufSize = 127;
byte outBufDetected[outBufSize];

if (coTfsSetSDOScan( outBufDetected, outBufSize ) == 1) {
  write ("SDO scan successfully performed");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)