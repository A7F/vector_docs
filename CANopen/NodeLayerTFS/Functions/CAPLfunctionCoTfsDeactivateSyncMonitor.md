[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsDeactivateSyncMonitor.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsDeactivateSyncMonitor

# coTfsDeactivateSyncMonitor

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsDeactivateSyncMonitor( dword canId );
```

## Description

This function switches off the calling of the sync callbacks if these are switched on. Furthermore all active sync PDO checks are also disabled.

The callbacks can be switched on with [coTfsActivateSyncMonitor](CAPLfunctionCoTfsActivateSyncMonitor.md).

## Parameters

- **canId**: CAN identifier

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsActivateSyncMonitor(0x080080,100.20);
TestWaitForTimeout(2000);
coTfsDeactivateSyncMonitor(0x008080);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)