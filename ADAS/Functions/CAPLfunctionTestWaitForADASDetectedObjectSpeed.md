[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionTestWaitForADASDetectedObjectSpeed.md)

# TestWaitForADASDetectedObjectSpeed

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » TestWaitForADASDetectedObjectSpeed

Valid for: CANoe DE

## Changes

This function was renamed from **TestWaitForADASSpeed** in CANoe DE product version 16 SP3.

## Function Syntax

- `long TestWaitForADASDetectedObjectSpeed (long overUnder, float threshold, long aTimeout)` // form 1
- `long TestWaitForADASDetectedObjectSpeed (long overUnder, float threshold, int64 trackingId, long aTimeout)` // form 2
- `long TestWaitForADASDetectedObjectSpeed (long overUnder, float threshold, float minLateralOffset, float maxLateralOffset, long aTimeout)` // form 3
- `long TestWaitForADASDetectedObjectSpeed (long overUnder, float threshold, float minLateralOffset, float maxLateralOffset, int64 trackingId, long aTimeout)` // form 4

## Description

Waits for the occurrence of the first Detected Object matching the speed conditions passed as arguments. Should the Detected Object not occur before the expiration of the time `aTimeout`, the wait condition is resolved nevertheless.

## Parameters

- **overUnder**: Specifies if the relative speed should be over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum relative speed. An object moving towards the sensor has a negative relative speed. An object moving away from the sensor has a positive relative speed. The unit is specified in m/s.
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
enum VWaitThreshold
{
  kUnderThreshold = 0,
  kOverThreshold = 1
};

// form 1
if(TestWaitForADASDetectedObjectSpeed(kUnderThreshold, -30, 3000)) 
{
  // Detected Object with relative speed less than –30 m/s detected
}
else
{
  // Timeout
}

// form 2
if(TestWaitForADASDetectedObjectSpeed(kUnderThreshold, -30, 42,3000))
{
  // Detected Object with a trackingId of 42 and a relative speed less than –30 m/s detected
}

// form 3
if (TestWaitForADASDetectedObjectSpeed(kUnderThreshold, -9, -1, 1, 1000))
{
  // Detected Object with relative speed less than –9 m/s and a lateral Offset to the host vehicle between -1 m and 1 m detected.
}

// form 4
if(TestWaitForADASDetectedObjectSpeed(kUnderThreshold, -9, 2, 4, 3 , 1000))
{
  // Detected Object with trackingId 3 and relative speed less than –9 m/s and a lateral Offset to the host vehicle between 2 m and 4 m detected.
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)