[TestWaitForADASDetectedObjectDistance](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionTestWaitForADASDetectedObjectDistance.md)

**CAPL Functions » ADAS » TestWaitForADASDetectedObjectDistance**

# TestWaitForADASDetectedObjectDistance

**Valid for:** CANoe DE

## Changes

This function was renamed from **TestWaitForADASDistance** in CANoe DE product version 16 SP3.

## Function Syntax

- `long TestWaitForADASDetectedObjectDistance (long overUnder, float threshold, long aTimeout)` // form 1
- `long TestWaitForADASDetectedObjectDistance (long overUnder, float threshold, int64 trackingId, long aTimeout)` // form 2
- `long TestWaitForADASDetectedObjectDistance (long overUnder, float threshold, float minLateralOffset, float maxLateralOffset, long aTimeout)` // form 3
- `long TestWaitForADASDetectedObjectDistance (long overUnder, float threshold, float minLateralOffset, float maxLateralOffset, int64 trackingId, long aTimeout)` // form 4

## Description

Waits for the occurrence of the first Detected Object matching the distance conditions passed as arguments. Should the Detected Object not occur before the expiration of the time `aTimeout`, the wait condition is resolved, nevertheless.

## Parameters

- **overUnder**: Specifies if the distance should be over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum distance.
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
if(TestWaitForADASDetectedObjectDistance(kUnderThreshold, 30, 3000)) // Wait for Detected Object under 30m distance for 3 seconds
{
  // Detected Object below distance of 30 m detected
}
else
{
  // Timeout
}

// form 2
if (TestWaitForADASDetectedObjectDistance(kUnderThreshold, 30, 42, 3000))
{
  // Detected Object with a trackingId of 42 and a distance below 30 m detected
}

// form 3
if (TestWaitForADASDetectedObjectDistance(kUnderThreshold, 50, -1, 1, 1000))
{
  // Detected Object below distance of 50 m detected. Detected Object has a lateral Offset to the host vehicle between -1 m and 1 m.
}

// form 4
if (TestWaitForADASDetectedObjectDistance(kOverThreshold, 50, -4, -2, 3 , 1000))
{
  // Detected Object with trackingId 3 above distance of 50 m detected. Detected Object has a lateral Offset to the host vehicle between -4 m and -2 m.
}
```

[TestWaitForADASDetectedObjectSpeed](CAPLfunctionTestWaitForADASDetectedObjectSpeed.md) • [TestGetWaitADASDetectedObject](CAPLfunctionTestGetWaitADASDetectedObject.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)