# diagIsParameterDefault

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagIsParameterDefault(diagResponse obj, char parameterName[]);
long diagIsParameterDefault(diagRequest obj, char parameterName[]);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```c
diagResponse::IsParameterDefault(char* parameterName);
diagRequest::IsParameterDefault(char parameterName[]);
```

## Description

Returns `<> 0` if the parameter in the object has its default value.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier

## Return Values

1 for true or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—
