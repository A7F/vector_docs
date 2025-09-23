# TestWaitForMostApInstID

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestWaitForMostApInstID(unsigned long aTimeout);
```

## Description

The function waits for the specified period of time for a special change event of the application socket which is triggered when the InstanceId of an FBlock on its channel changes.

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]  
  (Transmission of 0: no timeout monitoring)

## Return Values

- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on Timeout
- **1**: Resume based on occurred event

## Example

—
