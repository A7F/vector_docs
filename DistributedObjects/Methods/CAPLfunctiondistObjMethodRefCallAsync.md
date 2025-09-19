# distObjMethodRef::CallAsync

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `callContext <Method> distObjMethodRef::CallAsync(params ...);` // form 1
- `void distObjMethodRef::CallAsync(params ..., Callback);` // form 2

## Description

Asynchronous call to a method member, i.e. the call does not wait for the function to be called and the return to be received. In test procedures, you can wait for the answer with [TestWaitForAnswer](../../Test/Functions/CAPLfunctionTestWaitForAnswer.md); in simulation programs, you can use the handler [on fct_Returned](../../CommunicationObjects/EventProcedures/CAPLfunctionOnfctReturned.md). In form 2, the callback function is called when the return is received.

## Parameters

- The **in** and **inout** parameters of the method. The function expects the arguments in **impl** encoding.
- Form 2 takes as last parameter a callback function which in turn must have a single parameter of type **callContext <Method>** and return type **void**. You can also use a [delegate](../../../Shared/CAPL/General/Delegates.md) for the callback.

## Return Values

- **Form 1**: A call context object for the call. You can e.g. use it to wait for the return or to retrieve a unique request ID which you can match in a [on fct_Returned](../../CommunicationObjects/EventProcedures/CAPLfunctionOnfctReturned.md) handler.

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.SomeMethod.CallAsync(1, 2, delegate (callContext ExampleObject.SomeMethod cco) {
    write("Result = %d", cco.Result);
  });
}
```
