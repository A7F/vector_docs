# coTfsNmt (Level 3)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsNmt( void );
```

## Description

This function attempts to set the following device states in the DUT (Device Under Test) sequentially: Stop, Reset, Operational, Pre-Operational, Reset Communication, Start, Pre-Operational and Reset.

After this test, the DUT is in the pre-operational state.

**Note**: If the heartbeat producer is already active, it will be restored at the end.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsNmt() != 1) { 
  write ("coTfsNMT failed");
}
```
