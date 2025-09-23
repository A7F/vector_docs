# StmQuery_Valid

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long StmQuery_Valid (Check aStimulusId)
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
stimulus.QueryValid()
```

## Description

Examines whether a stimulus with particular Id is valid.

## Parameters

- **dword aStimulusId** —

## Return Values

- **= 0**: Refer the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **\> 0**: Valid Id

## Applicable for

All stimuli

## Example

```plaintext
double result;
dword stmId;
stmId = StmCreate_Toggle(Velocity, 60, 80, 100);
// ... execute test sequence
result = StmQuery_Valid(stmId);
```
