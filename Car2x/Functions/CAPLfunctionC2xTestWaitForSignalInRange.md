# C2xTestWaitForSignalInRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xTestWaitForSignalInRange (char* protocolDesignator, char* tokenDesignator, int64 minTokenValue, int64 maxTokenValue,  long timeout)` // form 1
- `long C2xTestWaitForSignalInRange (char* protocolDesignator, char* tokenDesignator, int64 minTokenValue, int64 maxTokenValue, char* stationName, long timeout)` // form 2

## Description

Waits for the occurrence of the first Car2x message with a signal that is inside or equals the given limit. Should the message not occur before the expiration of the time aTimeout, the wait condition is resolved nevertheless.

## Parameters

- **protocolDesignator**: Protocol designator of the Car2x message that should be awaited.
- **tokenDesignator**: Token designator of the Car2x message that should be awaited.
- **minTokenValue**: Lower limit of the value.
- **maxTokenValue**: Upper limit of the value.
- **stationName**: Name of the sender station of the Car2x message that should be awaited.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **1**: Resume due to event occurred.

## Example

```plaintext
long result;
//Form 1: Wait for occurrence of Car2x message with application message "CAM" and a generationDelatTime in a range of 20-100 ms
result = C2xTestWaitForSignalInRange("CAM","cam::generationDeltaTime", 20, 100, 1000);
//Form 2: Wait for occurrence of Car2x message from "Station1" with GeoNetworking version 1 or 2
result = C2xTestWaitForSignalInRange("geo_bh","version", 1, 2, "Station1", 1000);
```

[C2xTestJoinSignalInRange](CAPLfunctionC2xTestJoinSignalInRange.md) | [C2xTestJoinSignalMatch](CAPLfunctionC2xTestJoinSignalMatch.md) | [C2xTestWaitForSignalMatch](CAPLfunctionC2xTestWaitForSignalMatch.md)
