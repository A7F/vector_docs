[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsActivateSyncPdoMonitor.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsActivateSyncPdoMonitor**

# coTfsActivateSyncPdoMonitor

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsActivateSyncPdoMonitor( dword syncCanId, dword pdoCanId, dword transmissionType );
```

## Description

This function checks if the DUT (Device Under Test) sends a synchronous PDO with the given CAN-ID. The check is only available if the sync check was activated with [coTfsActivateSyncMonitor](CAPLfunctionCoTfsActivateSyncMonitor.md).

For each correct occurrence, the callback `void coTfsOnSyncPdoMsg(dword canId)` is called. The synchronous PDO must occur in the defined time slot. If the time is not adhered to, then the callback `void coTfsOnSyncPdoFail(dword canId)` is called once. After an error has occurred, the callback system is automatically disabled.

This check can be switched off again with [coTfsDeactivateSyncPdoMonitor](CAPLfunctionCoTfsDeactivateSyncPdoMonitor.md).

## Parameters

- **syncCanId**: Sync CAN-ID to be used.
- **pdoCanId**: CAN-ID of the PDO to be monitored.
- **transmissionType**: PDO transmission type, range 1..240.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsActivateSyncMonitor(0x80, 1000000, 500000, 50000); // 1s, 500 ms, 50 ms
coTfsActivateSyncPdoMonitor(0x181);
coTfsActivateSyncPdoMonitor(0x182);
coTfsActivateSyncPdoMonitor(0x183);

// ... callbacks are active ...
coTfsDeactivateSyncPDOMonitor(0x181); // disables one sync pdo callback

// ... others are still active ...
coTfsDeactivateSyncPDOMonitor(); // remove all checks
coTfsDeactivateSyncMonitor(); // disable sync check
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)