# on busIntegration

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `on busIntegration( ); // form 1`
- `on CAN*.busIntegration( ); // form 2`

## Description

This event handler is called when a bus integration event occurs on a CAN channel. The event occurs when the CAN channel is activated after the measurement has started or when the channel is reset.

## Selectors

- **Selector1**: channel
  - **Description**: CAN channel the bus integration event occurs.
  - **Type**: dword
  - **Access Limitation**: read

- **Selector1**: time_ns
  - **Description**: The timestamp of the event.
  - **Type**: Int64
  - **Access Limitation**: —

## Example

**Example form 1**

Form 1 (Wildcard all CAN channels the bus integration event occurs)

```plaintext
on busIntegration
{
  write("Channel %d Time %llu", this.channel, this.time_ns);
}
```

**Example form 2**

Form 2 (Defined CAN channel the bus integration event occurs)

```plaintext
on CAN1.busIntegration
{
  write("Channel %d Time %llu", this.channel, this.time_ns);
}
```
