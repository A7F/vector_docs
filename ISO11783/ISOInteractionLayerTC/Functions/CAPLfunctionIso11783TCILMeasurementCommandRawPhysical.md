[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILMeasurementCommandRawPhysical.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_MeasurementCommandRaw, TCIL_MeasurementCommandPhysical**

# TCIL_MeasurementCommandRaw, TCIL_MeasurementCommandPhysical

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long TCIL_MeasurementCommandRaw(dbNode client, dword ddi, dword elementNumber, char[] logTriggerType, long triggerValue); // form 1`
- `long TCIL_MeasurementCommandRaw(dword addressClient, dword ddi, dword elementNumber, char[] logTriggerType, long triggerValue); // form 2`
- `long TCIL_MeasurementCommandRaw(dbNode tc, dbNode client, dword ddi, dword elementNumber, char[] logTriggerType, long triggerValue); // form 3`
- `long TCIL_MeasurementCommandRaw(dbNode tc, dword addressClient, dword ddi, dword elementNumber, char[] logTriggerType, long triggerValue); // form 4`
- `long TCIL_MeasurementCommandPhysical(dbNode client, dword ddi, dword elementNumber, char[] logTriggerType, double triggerValue); // form 5`
- `long TCIL_MeasurementCommandPhysical(dword addressClient, dword ddi, dword elementNumber, char[] logTriggerType, double triggerValue); // form 6`
- `long TCIL_MeasurementCommandPhysical(dbNode tc, dbNode client, dword ddi, dword elementNumber, char[] logTriggerType, double triggerValue); // form 7`
- `long TCIL_MeasurementCommandPhysical(dbNode tc, dword addressClient, dword ddi, dword elementNumber, char[] logTriggerType, double triggerValue); // form 8`

## Description

These functions send a trigger definition to the client.

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the TC sends the **Measurement command** to.
- **addressClient**: Address of the Task Controller client node the TC sends the **Measurement command** to.
- **elementNumber**: Element number, 0x000..0xFFF.
- **ddi**: Data dictionary identifier, 0x0000..0xFFFF.
- **logTriggerType**:
  - **time_interval**: The client sends the value cyclically with this time interval = triggerValue. 0 stops measurement, 100 ms is the minimum. Unit: milliseconds.
  - **distance_interval**: The client sends the value cyclically with this distance interval = triggerValue. 0 stops measurement. Unit: millimeters.
  - **min_within_threshold**: The client sends the value when it is higher than the triggerValue. Unit: as specified by the DDI definition.
  - **max_within_threshold**: The client sends the value when it is lower than the triggerValue. Unit: as specified by the DDI definition.
  - **change_threshold**: The client sends the value when the change is higher than or equal to the triggerValue since last transmission. 0 stops measurement, 1 logs each change. Unit: as specified by the DDI definition.
- **triggerValue**: Raw or physical logging trigger value.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 3**

```c
void StartDistanceTrigger(dword ddi, dword elementNumber, dword distance) {
  long result;
  result = TCIL_MeasurementCommandRaw(TC, Sprayer, ddi, elementNumber, "distance_interval", distance);
  switch (result) {
    case 0: TestStepPass(); break;
    case -2202: TestStepFail("Function is not available in passive mode of the TC IL!"); break;
    case -2204: TestStepFail("Node 'Sprayer' is no client device!"); break;
    case -2206: TestStepFail("Task Controller IL is currently not online!"); break;
    case -2210: TestStepFail("Failed to send Measurement command!"); break;
    default: TestStepFail("Unexpected error"); break;
  }
}
```

**Example form 7**

```c
void StopMinWithinThresholdTrigger(dword ddi, dword elementNumber) {
  long result;
  result = TCIL_MeasurementCommandRaw(TC, Sprayer, ddi, elementNumber, "min_within_threshold", 0x7FFFFFFF);
  switch (result) {
    case 0: TestStepPass(); break;
    default: TestStepFail("StopMinWithinThresholdTrigger", "Unexpected error (error code %i)", result); break;
  }
}
```
