# Iso11783DestroyECU

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783DestroyECU( dword ecuHandle );
```

## Description

This function deletes a logical node that was generated with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) from the network.

**Important Note**  
You should avoid allowing this function to be called within a CAPL callback function, since otherwise data consistency of the node layer could be violated.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

- **0**: ECU was correctly deleted
- **1**: ECU couldn't be deleted, because the function was called from a callback
- **2**: invalid ECU handle

## Example

```plaintext
Iso11783DestroyECU(ecuHandle);
```
