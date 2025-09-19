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
