# callcontext::ReleaseHandle (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
void callContext::ReleaseHandle(long handle);
```

### Description

Releases a permanent handle for a call context. You need a permanent handle if you want to keep a call alive for a longer time, e.g., if you wish to store several call contexts in an (associative) array. You also need a permanent handle if you want to pass the call context, e.g., to a CAPL DLL.

### Parameters

- **handle**: A permanent handle for a call context.

### Return Values

—

### Example

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

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [callcontext::CreatePermanentHandle](CAPLfunctionCallcontextCreatePermanentHandle.md) • [callcontext::FromHandle](CAPLfunctionCallcontextFromHandle.md)
