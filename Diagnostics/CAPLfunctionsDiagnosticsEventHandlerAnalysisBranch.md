# Diagnostic Event Handlers in Measurement Setup

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

In the [Measurement Setup](../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindow.md) of your CANoe DE product, a diagnostic interpreter creates diagnostic request and response events for transport protocol events, if matching diagnostic descriptions have been configured. In addition to the display in the Trace window, these events can be processed in CAPL program nodes: the event handlers [on diagRequest](EventProcedures/CAPLfunctionOnDiagRequest.md) and [on diagResponse](EventProcedures/CAPLfunctionOnDiagResponse.md) can be defined and will be called for matching objects. While it is not possible to use both types of handlers in the same CAPL node in the [Simulation Setup](../../CANoeCANalyzer/Windows/SimulationSetup/SimulationSetupWindow.md) (since a ECU does not receive responses and a tester does not receive its own requests), it is no problem to use both handler types in a CAPL node in the [Measurement Setup](../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindow.md) simultaneously.

## Restrictions

Note that certain restrictions apply to the code in these handlers.

- It is NOT possible to change the values of diagnostic parameters in the object. These objects have been sent already, and therefore any change to them would be tool-internal: a Trace Window behind the node would no longer see the actual event, but an event changed by the program.
- All functions that cause the sending of diagnostic objects are unavailable. Nodes in the [Measurement Setup](../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindow.md) are not connected to a network.
- Events will be filtered by the handler, unless **output(this)** is called to forward them in the [Measurement Setup](../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindow.md).
- It is not possible to declare diagnostic objects in these handlers.

The documentation for every diagnostic function indicates whether it is available in the [Measurement Setup](../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindow.md).

### Example

```plaintext
On diagResponse Sessions::*
{
  char line[200];
  char ecu[100];
  long i;
  long firstCall = 1;
  if( this.IsPositiveResponse() == 1)
    write( "Positive response");
  else
    write( "Negative response");

  diagGetCurrentEcu( ecu, elcount(ecu));
  DiagGetObjectPath( this, line, elcount( line));

  write( "on diagResponse Sessions::*: %s from %s", line, ecu);
  i = 0;
  while( DiagGetParameterPath( this, i, line, elcount(line)) > 0)
  {
    char symbol[200];
    this.GetParameter( line, symbol, elcount(symbol));
    write( "%4d %-40s = %s", i++, line, symbol);
  }

  if( firstCall)
  {
    firstCall = 0;
    line[0] = 0;
    diagGetDescriptionInformation( "", line, elcount(line));
    write( line);

    line[0] = 0;
    i = diagGetActiveVariant( line, elcount(line));
    write( "  diagGetActiveVariant (no target) returns %d and '%s'", i, line);

    line[0] = 0;
    i = diagGetConfiguredVariant( line, elcount(line));
    write( "  diagGetConfiguredVariant (no target) returns %d and '%s'", i, line);
  }
  output(this);
}
```
