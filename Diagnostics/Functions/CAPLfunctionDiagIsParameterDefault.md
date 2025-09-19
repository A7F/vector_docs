[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagIsParameterDefault.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagIsParameterDefault

# diagIsParameterDefault

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagIsParameterDefault (diagResponse obj, char parameterName[])
long diagIsParameterDefault (diagRequest obj, char parameterName[])
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
diagResponse::IsParameterDefault (char* parameterName)
diagRequest::IsParameterDefault (char parameterName[])
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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)