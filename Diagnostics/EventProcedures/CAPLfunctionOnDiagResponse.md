# on diagResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following syntax forms require a defined target ECU by calling `diagSetTarget(char ecuQualifier[])` beforehand. When using these forms, no semantic check can be performed at compile-time, so no warnings will be emitted for nonexistent diagResponses.

- form 1
- form 2
- form 3
- form 4

## Function Syntax

`on diagResponse`

## Description

The procedure is sub-divided into the following events; the first matching event procedure (top-down) is called:

- `on diagResponse <service>` // form 1  
  Is called when a response is received in the tester that belongs to the indicated diagnostic service.

- `on diagResponse <class>::<instance>::<service>`  
  Is called when the service of the response received belongs to the specified class and instance. If an ECU qualifier is given, the procedure is called only when the response was sent by this ECU. This procedure may therefore be called for several services!

- `on diagResponse <class>::*` // form 3  
  Is called when the service of the response received belongs to the specified class. If an ECU qualifier is given, the procedure is called only when the response was sent by this ECU. This procedure may therefore be called for several services!

- `on diagResponse *` // form 4  
  Is called when no other event procedure matches. If an ECU qualifier is given, the procedure is called only when the response was sent by this ECU. This procedure may therefore be called for several services!

- `on diagResponse <ECU>.<service>` // form 5  
  Is called when a response from the indicated ECU (specified with its [ECU qualifier](../../../CANoeCANalyzer/Diagnostics/DiagISOTPconfig/DiagDescr/DiagDescOther.md)) is received in the tester, that belongs to the indicated diagnostic service. This is especially useful in situations where the tester program communicates with more than one diagnostic targets, e.g. sending functional requests.

- `on diagResponse <ECU>.<class>::<instance>::*` // form 6  
  Is called when a response from the indicated ECU (specified with its [ECU qualifier](../../../CANoeCANalyzer/Diagnostics/DiagISOTPconfig/DiagDescr/DiagDescOther.md)) is received in the tester which belongs to the specified class and instance. This procedure may therefore be called for several services!

- `on diagResponse <ECU>.<class>::*` // form 7  
  Is called when a response from the indicated ECU (specified with its [ECU qualifier](../../../CANoeCANalyzer/Diagnostics/DiagISOTPconfig/DiagDescr/DiagDescOther.md)) is received in the tester which belongs to the specified class. This procedure may therefore be called for several services!

- `on diagResponse <ECU>.*` // form 8  
  Is called when a response from the indicated ECU (specified with its [ECU qualifier](../../../CANoeCANalyzer/Diagnostics/DiagISOTPconfig/DiagDescr/DiagDescOther.md)) is received in the tester when no other event procedure matches. This procedure may therefore be called for several services!

**Note**  
Please note that, after every sending of a request, all responses are signaled only to the sender. Diagnostic requests that are sent from the Diagnostic Console are thus invisible for a CAPL program as are the received responses. Similarly, no responses to requests sent from a CAPL program are displayed in the Diagnostic Console.

**Note**  
When the procedure is called in the analysis branch of the Measurement Setup, only a fraction of the diagnostic functions is available. Please refer to [Diagnostics Event Handlers in Measurement Setup](../CAPLfunctionsDiagnosticsEventHandlerAnalysisBranch.md) for details. The event must be forwarded with **output(this)** if processing shall continue in blocks of the [Measurement Setup](../../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindow.md).

_______________________  
**(1)** While the CANdela process knows the concept of a "diagnostic instance", ODX does not. Starting with CANoe 7.0 it is possible to use new unique service qualifiers, while CAPL programs for earlier CANoe versions might indicate the equivalent long qualifier path. It is not recommended to mix these forms of declaration!

## Example

**Example 1 - Simulation Setup**  

```c
// e.g. used in a Tester module
on diagResponse *
{
  byte data[4096];
  long size;
  double param_value1=0xFF;
  double param_value2=0xFF;
  diagResponse * resp; // declare response with no concrete interpretation
  size=this.GetPrimitiveSize();             // get length of response
  this.GetPrimitiveData(data, elcount(data));  // copy actual response from "on diagResponse *" into data array

  switch(data[0])
  {
    case 0x50: // UDS: DiagnosticSessionControl_Process positive Response
      diagInitialize(resp, "DiagnosticSessionControl_Process");
      resp.Resize(size); // make sure there is room for the received bytes
      resp.SetPrimitiveData(data, size);           // initialize resp with actual response from data array
      param_value1=diagGetParameter(resp, "diagnosticSessionType");
      param_value2=diagGetParameter(resp, "sessionParameterRecord");
      break;
    case 0x51: // UDS: EcuReset_Process positive Response
      diagInitialize(resp, "EcuReset_Process");
      resp.Resize(size); // make sure there is room for the received bytes
      resp.SetPrimitiveData(data, size);           // initialize resp with actual response from data array
      param_value1=diagGetParameter(resp, "resetType");
      param_value2=diagGetParameter(resp, "powerDownTime");
      break;
    default:
      break;
  }
  write("Tester: Value of parameter according to chosen interpretation: 0x%x 0x%x %3.0lf %3.0lf",data[0], data[1], param_value1, param_value2);
}
```

**Example 2 - Measurement Setup**  

```c
// Indicate all responses in the write window
diagResponse *
{
  char objectPath[200];
  char currentEcu[100];
  this.GetObjectPath(objectPath, elcount(objectPath));
  DiagGetCurrentEcu(currentEcu, elcount(currentEcu));

  write( "Response %s from ECU %s", objectPath, currentEcu);
  output(this); // forward down the measurment branch
}
```

[on diagRequest](CAPLfunctionOnDiagRequest.md) • [on diagRequestSent](CAPLfunctionOnDiagRequestSent.md)
