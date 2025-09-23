# TestWaitForBusIntegration

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`TestWaitForBusIntegration(dword channel, dword timeout);`

## Description

Can be used to wait for the Bus Integration event of a CAN channel. The Bus Integration event occurs if the channel is activated. The activation occurs at the start of measurement and if the CAN channel is reset or options changed during the measurement.

## Parameters

- **channel**: CAN channel.
- **timeout**: Max. time in ms for waiting of the occurrence of this event.

## Return Values

- **-999**: If aborted by measurement stop.
- **-1**: If used within Measurement Setup or called in prestart.
- **0**: Timeout occurred.
- **1**: Event occurred.

## Example

```c
testcase WaitForBusIntegrationEvents()
{
  long result;
  resetCan();
  result = TestWaitForBusIntegration(1, 10);
  if(result == 1)
  {
    testStepPass("CAN1: TestWaitForBusIntegration event received in timeout time of 10 ms");
  }
  else
  {
    testStepFail("CAN1: TestWaitForBusIntegration event not received in timeout time of 10 ms");
  }
  result = TestWaitForBusIntegration(2, 10);
  if(result == 1)
  {
    testStepPass("CAN2: TestWaitForBusIntegration event received in timeout time of 10 ms");
  }
  else
  {
    testStepFail("CAN2: TestWaitForBusIntegration event not received in timeout time of 10 ms");
  }
}
```
