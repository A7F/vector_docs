# SetMethod (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
long consumedMethodRef::SetMethod(Method method);
long providedMethodRef::SetMethod(Method method);
```

## Description

Sets the referred-to method for the CO reference.

## Parameters

- **method**: The new method.

## Return Values

- **0**: Success
- **3**: Given method doesn’t have the correct type
- **-1**: Given reference is invalid

## Example

```plaintext
consumedMethodRef Services::IMirrors.SetPosition cmr;
cmr.SetMethod(Services::Mirrors.SetPosition);
```
