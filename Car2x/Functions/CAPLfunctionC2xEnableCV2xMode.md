# C2xEnableCV2xMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xEnableCV2xMode ( long appChannel );
```

## Description

This function enables the CV2x protocol for a channel. The function has to be called in the event handler **on preStart**.

## Parameters

- **appChannel**
  - 0 = current Channel
  - 1 = Ath1
  - 2 = Ath2

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
on preStart()
{
  // enable CV2x for the first channel (Ath1)
  C2xEnableCV2xMode (1);
}
```
