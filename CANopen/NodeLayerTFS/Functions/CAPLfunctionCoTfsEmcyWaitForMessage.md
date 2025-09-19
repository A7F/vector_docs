# coTfsEmcyWaitForMessage (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsEmcyWaitForMessage( dword timeout );
```

## Description

This function waits until either a time-out occurs or an emergency message for the selected DUT (Device Under Test) is received.

## Parameters

- **timeout**: Time-out in ms.

## Return Values

- **0**: A time-out has occurred
- **1**: An emergency message was received

## Example

```plaintext
if ( coTfsEmcyWaitForMessage( 5000 )== 1) {
  write("emergency message received");
} else {
  write("time-out occurred");
}
```
