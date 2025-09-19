[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForAnswer.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForAnswer

# TestWaitForAnswer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestWaitForAnswer(callContext cco, dword timeoutMs);
```

## Description

Waits for the answer to a method call. The call must have been created through [consumedMethodRef::CallAsync](../../CommunicationObjects/Methods/CAPLfunctionConsumedMethodRefCallAsync.md) on a consumed method.

If the wait is successful, the call context properties for the return value and the out parameters can be read.

## Parameters

- **cco**: Call context for a call.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (method was called)

## Example

```plaintext
long ret;
callContext MirrorAdjustment.Adjust cco;

cco = MirrorAdjustment[0,0].Adjust.CallAsync(50, 0);
ret = TestWaitForAnswer(cco, 300);
if (ret == 1)
{
  write("Call result: %d", cco.Result);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForImplValue](CAPLfunctionTestWaitForImplValue.md) • [TestWaitForNextCall](CAPLfunctionTestWaitForNextCall.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
