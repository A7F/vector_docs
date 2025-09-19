# C2xTestJoinSignalMatch

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, int64 tokenValue)` // form 1
- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, int64 tokenValue, char* stationName)` // form 2
- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, long dataSize, byte* data)` // form 3
- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, long dataSize, byte* data, char* stationName)` // form 4
- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, char* namedBit, long tokenValue)` // form 5
- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, char* namedBit, long tokenValue, char* stationName)` // form 6
- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, long bitPosition, long tokenValue)` // form 7
- `long C2xTestJoinSignalMatch (char* protocolDesignator, char* tokenDesignator, long bitPosition, long tokenValue, char* stationName)` // form 8

## Description

Completes the current set of joined events with the transmitted event. This function does not wait.

## Parameters

- **protocolDesignator**: Protocol designator of the Car2x message that should be awaited.
- **tokenDesignator**: Token designator of the Car2x message that should be awaited.
- **tokenValue**: Token value that should be awaited.
- **dataSize**: Length of the token data that should be awaited in bytes.
- **data**: Token data that should be awaited.
- **namedBit**: Name of a bit in a bitstring that should be awaited.
- **bitPosition**: Position of a bit in a bitstring that should be awaited. The first bit has the bit position 0.
- **stationName**: Name of the sender station of the Car2x message that should be awaited.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **>0**: Number of the joined event.

## Example

```c
long index;
long packet;
byte macAddress[6] = { 0x02, 0x00, 0x00, 0x00, 0x00, 0x01 };

// Form 1
index = C2xTestJoinSignalMatch("CAM", "header::protocolVersion", 2);

// Form 2
C2xTestJoinSignalMatch("DENM", "denm::situation::eventType::causeCode", 1, "Station1");
testWaitForAllJoinedEvents(1000);

// Form 3
C2xTestJoinSignalMatch("eth", "source", 6, macAddress);

// Form 4
C2xTestJoinSignalMatch("eth", "source", 6, macAddressStation2, "Station2");

// Form 5
C2xTestJoinSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", "lowBeamHeadlightsOn", 1);

// Form 6
C2xTestJoinSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", "lowBeamHeadlightsOn", 0, "Station2");

// Form 7
C2xTestJoinSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", 7, 0);

// Form 8
C2xTestJoinSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", 7, 0, "Station2");
if(testWaitForAllJoinedEvents(1500))
{
    // Get the message for the first joined event
    C2xTestGetWaitForMessage(index, packet);
}
```

[C2xTestWaitForSignalInRange](CAPLfunctionC2xTestWaitForSignalInRange.md) | [C2xTestWaitForSignalMatch](CAPLfunctionC2xTestWaitForSignalMatch.md) | [C2xTestJoinSignalInRange](CAPLfunctionC2xTestJoinSignalInRange.md)
