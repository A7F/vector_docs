# SetField (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `long consumedFieldRef::SetField(Field field);`
- `long providedFieldRef::SetField(Field field);`
- `long fieldConsumerRef::SetField(Field field);`
- `long fieldProviderRef::SetField(Field field);`

## Description

Sets the referred-to field for the CO reference.

## Parameters

- **field**: The new field.

## Return Values

- **0**: Success
- **3**: Given field doesn’t have the correct type
- **-1**: Given reference is invalid

## Example

```plaintext
consumedFieldRef double cfr;
cfr.SetField(Services::Mirrors.Position);
```
