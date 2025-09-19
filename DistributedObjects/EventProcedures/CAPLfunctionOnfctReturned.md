# on fct_returned

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`on fct_returned <function>;`

## Description

The event procedure is called at the consumer when a service function answer is returned to the consumer.

## Parameters

- **`<function>`**: Designates the function on which the event procedure shall react. This must be a combination of endpoints on consumer side.

## Selectors

- **State**: State of the call:
  - `eCALLSTATE_INITIAL`: the call has not yet reached the provider
  - `eCALLSTATE_CALLED`: the call has reached the provider, but the return has not yet reached the consumer
  - `eCALLSTATE_RETURNED`: the return has reached the consumer
  - `eCALLSTATE_DISCARDED`: the call context is invalid
  - **Type**: enumeration
  - **Access Limitation**: Read only

- **Side**: Shows where the call is currently being handled:
  - `eCOSIDE_CONSUMER`: consumer side
  - `eCOSIDE_PROVIDER`: provider side
  - **Type**: enumeration
  - **Access Limitation**: Read only

- **Consumer**: Name of the consumer which started the call.
  - **Type**: char[]
  - **Access Limitation**: Read only

- **Provider**: Name of the provider which is called.
  - **Type**: char[]
  - **Access Limitation**: Read only

- **CallTime**: Point of time (in simulation time, in nanoseconds) when the call was started (on consumer side) or the call reached the provider (on provider side).
  - **Type**: int64
  - **Access Limitation**: Read only

- **ReturnTime**: Point of time (in simulation time, in nanoseconds) when the call was returned to the consumer (on provider side) or the return reached the consumer (on consumer side).
  - **Type**: int64
  - **Access Limitation**: Read only

- **ReqID**: A request ID which identifies the call. Can be used to match replies to calls if several calls are waiting for a reply. The request ID is internal and not necessarily transmitted on the network.
  - **Type**: int64
  - **Access Limitation**: Read only

- **`<Parameter Name>`**: Value of the named parameter. Note that parameters are not accessible or read-only depending on the side and state of the call, e.g. you cannot access out-parameters in state Initial and cannot change in-parameters in state **Returned**.
  - **Type**: `<data type of the parameter>`
  - **Access Limitation**: `<depends on side and state>`

- **Result**: Return value of the function (if the function return type is not void).
  - **Type**: `<data type of the return value>`
  - **Access Limitation**: `<depends on side and state>`

## Example

```plaintext
on fct_returned MirrorAdjustment[CANoe,LeftMirror].Adjust
{
  write("Function result is %d", this.Result);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on fct_Calling](CAPLfunctionOnfctCalling.md) • [on fct_Called](CAPLfunctionOnfctCalled.md)
