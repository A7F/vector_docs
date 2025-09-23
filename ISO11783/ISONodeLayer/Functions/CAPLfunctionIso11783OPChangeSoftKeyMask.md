# Iso11783OPChangeSoftKeyMask

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeSoftKeyMask( dword ecuHandle, 
 dword maskID, dword softKeyMaskID );
```

## Description

The function changes the soft key mask of a data mask. A **Change Soft Key Mask** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **maskID**: Object ID of the data mask
- **softkeyMaskID**: Object ID of the data mask

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeSoftKeyMask( handle, 1000, 1050 );
```
