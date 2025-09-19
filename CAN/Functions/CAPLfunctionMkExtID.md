# mkExtId

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword mkExtId(dword id);
```

## Description

Returns an extended id.

## Parameters

- **id**: Id part of a message.

## Return Values

[Extended identifier](../../../CANoeCANalyzer/General/CANExtendedIdentifier.md)

## Example

```plaintext
...
msg.id = mkExtId(this.id);
...
```

•  Technical References are only available in English
