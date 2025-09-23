# Iso11783OPDeactivate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPDeactivate( dword ecuHandle );
```

```plaintext
long Iso11783OPDeactivate( dword ecuHandle, dword options );
```

## Description

The function terminates the connection to the Virtual Terminal.

The **Delete Object Pool** command is executed to log off from the Virtual Terminal. The **Maintenance** message is not longer sent. The Object Pool API changes to state **Not Active**.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **options**: Options
  - Bit 0 = 1: suppress **Delete Object Pool** command
  - Bit 1 = 1: delete local object pool

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPDeactivate( handle );
```
