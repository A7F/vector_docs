# consumedMethodRef::CallAsyncPhys (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

- `callcontext <MethodType> consumedMethodRef::CallAsync_Phys(params ...); // form 1`
- `void consumedMethodRef::CallAsync_Phys(params …, Callback); // form 2`

### Description

Calls the method from the specified consumer at the specified provider. The function call is made asynchronously, i.e. the call does not wait for the function to be called and the return to be received. In test procedures, you can wait for the answer with [TestWaitForAnswer](../../Test/Functions/CAPLfunctionTestWaitForAnswer.md); in simulation programs, you can use the handler [on fct_Returned](../EventProcedures/CAPLfunctionOnfctReturned.md). In form 2, the callback function is called when the return is received.

### Parameters

- The **in** and **inout** parameters of the method. The function expects the values in **phys** encoding.
- Form 2 takes as last parameter a callback function which in turn must have a single parameter of type `callContext <MethodType>` and return type void. You can also use a [delegate](../../../Shared/CAPL/General/Delegates.md) for the callback.

### Return Values

A call context object for the call. You can e.g. use it to wait for the return or to retrieve a unique request ID which you can match in a [on fct_Returned](../EventProcedures/CAPLfunctionOnfctReturned.md) handler.

### Example

```plaintext
callContext MirrorAdjustment.Adjust cco;
int waitResult;
cco = MirrorAdjustment.consumerSide[CANoe,LeftMirror].Adjust.CallAsync_Phys(50, 0);
waitResult = testWaitForAnswer(cco, 500);
if (waitResult == 1 && cco.Result == Mirrors::AdjustResult::OK)
{
  testStepPass("AdjustCall", "Call returned with OK");
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedMethodRef::CallAsync](CAPLfunctionConsumedMethodRefCallAsync.md) • [TestWaitForAnswer](../../Test/Functions/CAPLfunctionTestWaitForAnswer.md)
