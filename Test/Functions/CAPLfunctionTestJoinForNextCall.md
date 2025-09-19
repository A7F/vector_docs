[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinForNextCall.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinForNextCall

# TestJoinForNextCall

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestJoinForNextCall(providedMethodRef * method); // form 1
long TestJoinForNextCall(distObjMethodRef * method); // form 2
```

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

## Parameters

- **method**: Method provider where the call is awaited.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
long ret;
providedMethodRef MirrorAdjustment.Adjust method;

method = MirrorAdjustment.providerSide[all,LeftMirror].Adjust;
ret = testJoinForNextCall(method);

index = TestWaitForAllJoinedEvents(2000);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForImplValueUInt](CAPLfunctionTestWaitForImplValueUInt.md) • [TestWaitForImplValueSInt](CAPLfunctionTestWaitForImplValueSInt.md) • [TestWaitForImplValueFloat](CAPLfunctionTestWaitForImplValueFloat.md) • [TestWaitForImplValueString](CAPLfunctionTestWaitForImplValueString.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
