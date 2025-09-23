# TestWaitForImplValueFloat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long TestWaitForImplValueFloat(valueHandle * value, float awaitedValue, dword timeoutMs);
```

## Description

Waits for the impl encoding of a **valueHandle** to reach a certain value. This function can only be used for **valueHandles** with a floating point data type. It cannot be used for system variables or bus system signals.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **awaitedValue**: Value which is awaited.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (value has been reached)

## Example

```c
long ret;
ret = testWaitForImplValueFloat(MirrorStatus[CANoe].Temperature, 20.0, 200);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForImplValueUInt](CAPLfunctionTestWaitForImplValueUInt.md) • [TestWaitForImplValueSInt](CAPLfunctionTestWaitForImplValueSInt.md) • [TestWaitForImplValue](CAPLfunctionTestWaitForImplValue.md) • TestWaitForImplValueFloat
