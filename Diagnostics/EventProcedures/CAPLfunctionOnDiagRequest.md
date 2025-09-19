# on diagRequest

**Valid for**: CANoe DE

**Note**: The following syntax forms require a defined target ECU by calling `diagSetTarget(char ecuQualifier[])` beforehand. When using these forms, no semantic check can be performed at compile-time, so no warnings will be emitted for nonexistent diagRequests.

- form 1
- form 2
- form 3
- form 4

## Function Syntax

`on diagRequest`

## Description

In case [Additional Diagnostic Descriptions](../../../CANoeCANalyzer/Diagnostics/DiagISOTPconfig/DiagDescr/DiagDescAdditional.md) are configured for the ECU, the first description with a matching definition for the PDU is searched in the interpretation order. Otherwise, the diagnostic description assigned to the simulation is used immediately. Then the first matching event procedure (top-down) is called.

- `on diagRequest <service>` // form 1
  - Is called when a request is received in the ECU simulation that belongs to the indicated diagnostic service.

- `on diagRequest <class>::*` // form 2
  - Is called when the service of the request received belongs to the specified class.
  - This procedure may therefore be called for several services!

- `on diagRequest <class>::<instance>::*` // form 3
  - Is called when the service of the request received belongs to the specified class and instance.
  - This procedure may therefore be called for several services!

- `on diagRequest *` // form 4
  - Is called when no other event procedure matches.
  - This procedure may therefore be called for several services!

- `on diagRequest ECU.<service>` // form 5
  - Is called when a request is received in the ECU simulation that belongs to the indicated diagnostic service.

- `on diagRequest ECU.<class>::*` // form 6
  - Is called when a request is received in the ECU simulation and belongs to the specified class.
  - This procedure may therefore be called for several services!

- `on diagRequest ECU.<class>::<instance>::*` // form 7
  - Is called when a request is received in the ECU simulation and belongs to the specified class and instance.
  - This procedure may therefore be called for several services!

- `on diagRequest ECU.*` // form 8
  - Is called when a request is received in the ECU simulation and no other event procedure matches.
  - This procedure may therefore be called for several services!

**Note**: Please note that, after every sending of a request, all responses are signaled only to the sender. Diagnostic requests that are sent from the Diagnostic Console are thus invisible for a CAPL program as are the received responses. Similarly, no responses to requests sent from a CAPL program are displayed in the Diagnostic Console.

When the procedure is called in the analysis branch of the Measurement Setup, only a fraction of the diagnostic functions is available. Please refer to [Diagnostics Event Handlers in Measurement Setup](../CAPLfunctionsDiagnosticsEventHandlerAnalysisBranch.md) for details. The event must be forwarded with `output(this)` if processing shall continue in blocks of the [Measurement Setup](../../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindow.md).

_______________________

(1) While the CANdela process knows the concept of a "diagnostic instance", ODX does not. Starting with CANoe 7.0 it is possible to use new unique service qualifiers, while CAPL programs for earlier CANoe versions might indicate the equivalent long qualifier path.

It is not recommended to mix these forms of declaration!

## Example

**Example 1 Simulation Setup**

```plaintext
on diagRequest FaultMemory_ReadAllIdentified
{
   diagResponse this resp;

   // Set the number of bytes needed to transfer the response with 2 DTCs (in this example: overall 11 bytes)
   diagResize( resp, 11); // 3 Bytes Header (SID, Subfunction, AvailabilityMask) + 2 * 4 Bytes for DTCs = 11 bytes
   // Set the value of the DTCs
   diagSetComplexParameter ( resp, "ListOfDTC", 0, "DTC", 0x000001 );
   diagSetComplexParameter ( resp, "ListOfDTC", 0, "DtcStatusbyte", 0xF1 );
   diagSetComplexParameter ( resp, "ListOfDTC", 1, "DTC", 0x000002 );
   diagSetComplexParameter ( resp, "ListOfDTC", 1, "DtcStatusbyte", 0xF3 );

   diagSendResponse ( resp );
}
```

**Example 2 Measurement Setup**

```plaintext
// Indicate all requests in the write window
diagRequest *
{
  char objectPath[200];
  char currentEcu[100];
  this.GetObjectPath(objectPath, elcount(objectPath));
  DiagGetCurrentEcu(currentEcu, elcount(currentEcu));

  write( "Request %s to ECU %s", objectPath, currentEcu);
  output(this); // forward down the measurment branch
}
```

**Example 3**

Starting with CANoe DE product 9.0 SP3 The CAPL compiler supports diagnostic objects that are declared with an ECU qualifier or target (like a functional group). This allows the compiler to check if the diagnostic service used to initialize the object is defined in the diagnostic description of the ECU/target. If not, a compile error will be reported.

```plaintext
On start
{
  DiagRequest ECU1.Service1 req1;			// OK since Service1 is defined for ECU1
  DiagRequest ECU1.NotExisting req2;		// compile error since service unknown
}
```

**Example 4**

Specifying a target in the declaration of a diagnostic object has the benefit that it is NOT necessary to call [DiagSetTarget](../Functions/CAPLfunctionDiagSetTarget.md), and it is possible to communicate with several targets in parallel.

```plaintext
ParallelCommunication()
{
  DiagRequest ECU1.Service1 req1;
  DiagRequest ECU2.Service2 req2;

  // DiagSetTarget is NOT necessary!

  // Put the requests in the send queues of the integrated channels
  req1.SendRequest();
  req2.SendRequest();

  {
    // Since the order in which the responses will be received is not known,
    // join the response events to wait for them to arrive in any order
    long cond1;
    long cond2;
    long status;
    cond1 = testJoinDiagResponseFromEcu( "ECU1");
    cond2 = testJoinDiagResponseFromEcu( "ECU2");

    status = testWaitForAllJoinedEvents( 1000);
    if( cond1 == status || cond2 == status)
      testStepPass("Joined events received.");
    else
      testStepFail( "", "Waiting for all joined events returns %d", status);
  }
}
```

**Example 5**

Also, mixing diagnostic requests from a master description and any of its additional descriptions is possible without setting a target.

```plaintext
GetSomeInfo()
{
  DiagRequest ECU1.Service1 req1;
  DiagRequest ECU1.Additional1.ServiceA req2;

  // DiagSetTarget is NOT necessary!

  // Put both requests in the send queue of the integrated channel
  req1.SendRequest();
  req2.SendRequest();

  // Wait for the responses that must arrive in sending order since
  // the requests are sent on the same channel
  TestWaitForDiagResponse( req1, 1000);
  TestWaitForDiagResponse( req2, 1000);

  // ... access responses via the requests
  write( "Service1: %f", req1.GetRespParameter( "Param1");
  write( "ServiceA: %f", req2.GetRespParameter( "ParamA");
}
```
