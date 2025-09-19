[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionStmQueryValid.md)

**CAPL Functions** » **Test Service Library** » **Stimulus Functions** » **StmQuery_Valid**

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
- **> 0**: Valid Id

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

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
