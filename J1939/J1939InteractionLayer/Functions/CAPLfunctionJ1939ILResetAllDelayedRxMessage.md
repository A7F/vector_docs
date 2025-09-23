# J1939ILResetAllDelayedRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILResetAllDelayedRxMessage(dword behavior); // form 1
long J1939ILResetAllDelayedRxMessage(dbNode node, dword behavior); // form 2
```

## Description

Resets the change of all [J1939ILDelayRxMessage](CAPLfunctionJ1939ILDelayRxMessage.md) calls.

## Parameters

- **behavior**
  - 0: Do not process currently delayed messages
  - 1: Process currently delayed messages after the defined delay

- **node**
  - Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **-102**: An invalid parameter is used

## Example

—
