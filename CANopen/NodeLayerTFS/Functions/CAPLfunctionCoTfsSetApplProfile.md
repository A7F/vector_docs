# coTfsSetApplProfile

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSetApplProfile( dword profile );
```

## Description

The function enables the support of an application profile. The function has to be called before any test functions are executed.

## Parameters

- **profile**: Number of profile which is to be set, the values 0 and 301 are saved as 301 and represent the default value.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetApplProfile(447);

//...

coTfsSetApplProfile(301); // set back to default
```
