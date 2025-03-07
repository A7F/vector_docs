[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xTestJoinSignalInRange.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xTestJoinSignalInRange

# C2xTestJoinSignalInRange

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long C2xTestJoinSignalInRange (char* protocolDesignator, char* tokenDesignator, int64 minTokenValue,  int64 maxTokenValue) // form 1
long C2xTestJoinSignalInRange (char* protocolDesignator, char* tokenDesignator, int64 minTokenValue,  int64 maxTokenValue, char* stationName) // form 2
```

## Description

Completes the current set of joined events with the transmitted event. This function does not wait.

## Parameters

- **protocolDesignator**: Protocol designator of the Car2x message that should be awaited.
- **tokenDesignator**: Token designator of the Car2x message that should be awaited.
- **minTokenValue**: Lower limit of the value.
- **maxTokenValue**: Lower limit of the value.
- **stationName**: Name of the sender station of the Car2x message that should be awaited.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **>0**: Number of the joined event.

## Example

```plaintext
long index;
long packet;

// Form 1
index = C2xTestJoinSignalInRange("CAM","cam::generationDeltaTime", 20, 100);
// Form 2
C2xTestJoinSignalInRange("DENM", "denm::management::actionID::sequenceNumber", 1, 20, "Station1");
testWaitForAllJoinedEvents(1000);
// Get message of first joined event
C2xTestGetWaitForMessage(index, packet);
```

[C2xTestJoinSignalMatch](CAPLfunctionC2xTestJoinSignalMatch.md) | [C2xTestWaitForSignalMatch](CAPLfunctionC2xTestWaitForSignalMatch.md) | [C2xTestWaitForSignalInRange](CAPLfunctionC2xTestWaitForSignalInRange.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)