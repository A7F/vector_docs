# Iso11783OPActivate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPActivate( dword ecuHandle);
long Iso11783OPActivate( dword ecuHandle, dword options );
```

## Description

The function activates the Object Pool API. The initialization procedure with the Virtual Terminal is performed and the object pool is transmitted to the Virtual Terminal.

During the initialization procedure some information from the Virtual Terminal is requested. This can be suppressed with the `options` parameter. The requested information can be get with the function [Iso11783OPGetVTInfo](CAPLfunctionIso11783OPGetVTInfo.md).

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **options**: Options:
  - Bit 0 = 1: suppress **Get Memory** command
  - Bit 1 = 1: suppress **Get Number of Softkeys** command
  - Bit 2 = 1: suppress **Get Text Font Data** command
  - Bit 3 = 1: suppress **Get Hardware** command

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
dword handle = 0;
handle = Iso11783CreateECU( gECUName );

Iso11783OPLoad( handle, "ObjectPool.iop", "pool001" );
Iso11783OPActivate( handle );
Iso11783ECUGoOnline(handle, gECUAddress );
```
