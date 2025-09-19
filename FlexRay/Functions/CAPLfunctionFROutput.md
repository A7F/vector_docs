[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFROutput.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » output (FlexRay)

# output (FlexRay)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `void output(flexraymessage msg); // form 1`
- `void output(flexraystartcycle msg); // form 2`
- `void output(flexraysymbol msg); // form 3`
- `void output(flexraypocstate msg); // form 4`
- `void output(flexrayerror msg); // form 5`

## Description

Outputs the object from the program block of the analysis branch. This function must be used inside the appropriate event procedure in order to forward the event to the next block in the analysis branch. If the function is not called, then the event is not forwarded. Thus, events will be filtered by the CAPL program when omitting this function.

The function must not be used in the Simulation Setup or transmit branch.

## Parameters

- **Msg**: Variable of type
  - **flexraymessage**: List of available selectors for this type of objects can be found under [on frFrame](../EventProcedures/CAPLfunctionOnFRFrame.md) selectors, [on frSlot](../EventProcedures/CAPLfunctionOnFRSlot.md) selectors, [on frNullFrame](../EventProcedures/CAPLfunctionOnFRNnullFrame.md) selectors, and [on frFrameError](../EventProcedures/CAPLfunctionOnFRFrameError.md) selectors.
  - **flexraystartcycle**: List of available selectors for this type of objects can be found under [on frStartCycle](../EventProcedures/CAPLfunctionOnFRStartCycle.md) selectors.
  - **flexraysymbol**: List of available selectors for this type of objects can be found under [on frSymbol](../EventProcedures/CAPLfunctionOnFRSymbol.md) selectors.
  - **flexraypocstate**: List of available selectors for this type of objects can be found under [on frPocState](../EventProcedures/CAPLfunctionOnFRPocState.md) selectors.
  - **flexrayerror**: List of available selectors for this type of objects can be found under [on frRError](../EventProcedures/CAPLfunctionOnFRError.md) selectors.

The parameter variable can be accessed in each event handler by the keyword `this`.

## Return Values

—

## Example

If you react on start of cycle, frame, Null Frame or frame error events, then you must forward the event explicitly to the next node in the Measurement Setup. Otherwise the successor node will not receive that event!

```plaintext
on frFrame *
{
   // do something ...
   // forward event to next node in Measurement Setup:
   output(this);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
