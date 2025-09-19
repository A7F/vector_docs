# callcontext::DeferAnswer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
long callContext::DeferAnswer();
```

## Description

Defers the answer for a function call indefinitely. The call will only be answered once you call [callcontext::ReturnCall](CAPLfunctionCallcontextReturnCall.md) on the call context explicitly.

## Parameters

—

## Return Values

- **0**: Call was successful
- **1**: Wrong state of the call, e.g. call was already answered

## Example

```plaintext
on fct_Called MirrorAdjustment.providerSide[all,LeftMirror].Adjust
{
  // return the call always only after 2 other calls have been received
  const dword nrOfCalls = 3;
  long ccHandles[nrOfCalls];
  dword nextCallSlot = 0;
  dword nrOfCallsReceived = 0;

  this.Result = Mirrors::AdjustResult::OK;
  this.DeferAnswer();
  ccHandles[nextCallSlot] = this.CreatePermanentHandle();
  nextCallSlot = (nextCallSlot + 1) % nrOfCalls;

  if (++nrOfCallsReceived >= nrOfCalls)
  {
    callContext * cco;
    dword returnSlot;
    returnSlot = nrOfCallsReceived % nrOfCalls;
    cco = cco::FromHandle(ccHandles[returnSlot]);
    cco.ReturnCall();
    cco::ReleaseHandle(ccHandles[returnSlot]);
  }
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [callcontext::ReturnCall](CAPLfunctionCallcontextReturnCall.md) • [callcontext::SetTimeToAnswer](CAPLfunctionCallcontextSetTimeToAnswer.md)
