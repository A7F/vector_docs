# coTfsLssAddMasterResponseSwitchStateGlobal (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseSwitchStateGlobal( dword mode, dword modeMask );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions.

## Parameters

- **mode**  
  0 - Waiting mode  
  1 - Configuration mode

- **modeMask**  
  Mask for mode; set bits are compared, not set bits are not compared.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)
