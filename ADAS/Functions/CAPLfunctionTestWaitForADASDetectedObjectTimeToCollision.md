# TestWaitForADASDetectedObjectTimeToCollision

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `long TestWaitForADASDetectedObjectTimeToCollision (dword overUnder, float threshold, long aTimeout); // form 1`
- `long TestWaitForADASDetectedObjectTimeToCollision (dword overUnder, float threshold, int64 trackingId, long aTimeout); // form 2`
- `long TestWaitForADASDetectedObjectTimeToCollision (long overUnder, float threshold, float minLateralOffset, float maxLateralOffset,long aTimeout)// form 3`
- `long TestWaitForADASDetectedObjectTimeToCollision (long overUnder, float threshold, float minLateralOffset, float maxLateralOffset, int64 trackingId, long aTimeout) // form 4`

## Description

Waits for the occurrence of the first Detected Object matching the Time Collision (TTC) conditions passed as arguments. The TTC is calculated as current distance divided by current relative speed. Only the longitudinal movement is considered.

Should the Detected Object not occur before the expiration of the time `aTimeout`, the wait condition is resolved, nevertheless.

## Parameters

- **overUnder**: Specifies if the TTC should be over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum TTC. The unit is specified in seconds.
- **trackingId**: TrackingId of the Detected Object. Only a Detected Object with this trackingId triggers the wait condition.
- **minLateralOffset**: Specifies the minimum lateral offset [m] of the Detected Object. The lateral offset is positive for an offset to the left.
- **maxLateralOffset**: Specifies the maximum lateral offset [m] of the Detected Object. The lateral offset is positive for an offset to the left.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

## Example

```c
enum OverUnder
{
    kUnder = 0,
    kOver = 1
};

// form 1
if(TestWaitForADASDetectedObjectTimeToCollision(kUnder, 5,  10000))
{
    testStepPass("Detected Object with TTC under 5s");
}
else
{
    testStepFail("Timeout TestWaitForADASDetectedObjectTimeToCollision");
}

// form 2
if(TestWaitForADASDetectedObjectTimeToCollision(kUnder,3, 103, 20000))
{
    testStepPass("Detected Object with Id 103 and TTC under 3s");
}
else
{
    testStepFail("Timeout TestWaitForADASDetectedObjectTimeToCollision");
}

// form 3
if(TestWaitForADASDetectedObjectTimeToCollision(kUnder, 10.0, -1, 1, 1000))
{
    testStepPass("Detected Object with TTC under 10s and a lateral offset to the host vehicle between -1 m and 1 m.");
}
else
{
    testStepFail("Timeout");
}

// form 4
if(TestWaitForADASDetectedObjectTimeToCollision(kUnder, 5, 2, 4, 3 , 1000))
{
    testStepPass("Detected Object with trackingId 3, TTC under 5s and a lateral offset to the host vehicle between 2 m and 5 m.");
}
else
{
    testStepFail("Timeout");
}
```
