[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForNextCall.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForNextCall**

# TestWaitForNextCall

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForNextCall(providedMethodRef * method, dword timeoutMs); // form 1`
- `long TestWaitForNextCall(distObjMethodRef * method, dword timeoutMs); // form 2`

## Description

Waits for the next call of the method at the simulated provider. You may use a specific endpoint combination to wait for the call of a specific consumer or the combination [all,`<provider>`] to wait for a call of any consumer.

You can get information about the call with the **CurrentCCO** property or through the **LatestCall** value (both at the method endpoint).

**Note**: Form 2 requires a method member from a distributed object (`distObjRef <T>`). It is not allowed to pass method members from distributed object references (`distObjReferenceRef <T>`).

## Parameters

- **method**: Method provider where the call is awaited.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (method was called)

## Example

```plaintext
long ret;
providedMethodRef MirrorAdjustment.Adjust method;

method = MirrorAdjustment.providerSide[all,LeftMirror].Adjust;
ret = TestWaitForNextCall(method, 200);
if (ret == 1)
{
  int x;
  x = method.CurrentCCO.deltaX;
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForImplValue](CAPLfunctionTestWaitForImplValue.md) • [TestWaitForAnswer](CAPLfunctionTestWaitForAnswer.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
