[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionSetMethod.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SetMethod

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)