[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionCallcontextReturnCall.md)

## CAPL Functions » Communication Objects » callcontext::ReturnCall

# callcontext::ReturnCall (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

### Method Syntax

- `void callContext::ReturnCall(); // form 1`
- `void callContext::ReturnCall(<Type> returnValue); // from 2`

### Description

Returns the call immediately, sending an answer to the caller. Note that many function calls require an answer per protocol even if the function has neither a return value nor an out parameter.

**Immediately** means in effect after the current handler has been processed or when the current test procedures reaches a wait instruction, but at the same point of (simulation) time.

You can optionally set the return value (if the function does not return **void**).

This call is equivalent to [callcontext::SetTimeToAnswer(0)](CAPLfunctionCallcontextSetTimeToAnswer.md).

### Parameters

- **returnValue**: Return value for the call.

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

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [callcontext::DeferAnswer](CAPLfunctionCallcontextDeferAnswer.md) • [callcontext::SetTimeToAnswer](CAPLfunctionCallcontextSetTimeToAnswer.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)