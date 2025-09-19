# CarMaker_SetNamedValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_SetNamedValue(char name[], char value[]);
```

## Description

Defines or changes a named value in CarMaker.

## Parameters

- **name**: Name of the named value.
- **value**: The new value to be set.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
gErrorState = CarMaker_SetNamedValue("Variant", "V1");
```

• Technical References are only available in English
