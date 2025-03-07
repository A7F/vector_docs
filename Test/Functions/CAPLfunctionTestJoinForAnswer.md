[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinForAnswer.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinForAnswer

# TestJoinForAnswer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestJoinForAnswer(callContext cco);
```

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

## Parameters

- **value**: Value handle of a communication object or distributed object.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
long ret;
callContext MirrorAdjustment.Adjust cco;
cco = MirrorAdjustment[0,0].Adjust.CallAsync(50, 0);
ret = testJoinForAnswer(cco);

index = TestWaitForAllJoinedEvents(2000);
```

[TestJoinImplValue](CAPLfunctionTestJoinImplValue.md) • [TestJoinForNextCall](CAPLfunctionTestJoinForNextCall.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)