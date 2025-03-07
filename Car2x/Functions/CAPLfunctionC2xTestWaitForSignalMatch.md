[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xTestWaitForSignalMatch.md)

**Valid for**: CANoe DE

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xTestWaitForSignalMatch

# C2xTestWaitForSignalMatch

**Valid for**: CANoe DE

## Function Syntax

- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, int64 tokenValue, long timeout)` // form 1
- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, int64 tokenValue, char* stationName, long timeout)` // form 2
- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, long dataSize, byte* data, long timeout)` // form 3
- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, long dataSize, byte* data, char* stationName, long timeout)` // form 4
- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, char* namedBit, long tokenValue, long timeout)` // form 5
- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, char* namedBit, long tokenValue, char* stationName, long timeout)` // form 6
- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, long bitPosition, long tokenValue, long timeout)` // form 7
- `long C2xTestWaitForSignalMatch (char* protocolDesignator, char* tokenDesignator, long bitPosition, long tokenValue, char* stationName, long timeout)` // form 8

## Description

Waits for the occurrence of the first Car2x message with a signal that matches the given value. Should the message not occur before the expiration of the time `aTimeout`, the wait condition is resolved nevertheless.

## Parameters

- **protocolDesignator**: Protocol designator of the Car2x message that should be awaited.
- **tokenDesignator**: Token designator of the Car2x message that should be awaited.
- **tokenValue**: Token value that should be awaited.
- **dataSize**: Length of the token data that should be awaited in bytes.
- **data**: Token data that should be awaited.
- **namedBit**: Name of a bit in a bitstring that should be awaited.
- **bitPosition**: Position of a bit in a bitstring that should be awaited. The first bit has the bit position 0.
- **stationName**: Name of the sender station of the Car2x message that should be awaited.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

## Example

```c
long result;

byte macAddress[6] = { 0x02, 0x00, 0x00, 0x00, 0x00, 0x01 };

// Form 1: Wait for occurrence of a Car2x message with application message "CAM" and a protocol version of 2
result = C2xTestWaitForSignalMatch("CAM", "header::protocolVersion", 2, 1000);

// Form 2: Wait for occurrence of a Car2x message from "Station1" with GeoNetworking version 1
result = C2xTestWaitForSignalMatch("geo_bh", "version", 1, "Station1", 1000);

// Form 3: Wait for occurrence of a Car2x message with the specified macAddress
C2xTestWaitForSignalMatch("eth", "source", 6, macAddress, 1000);

// Form 4: Wait for occurrence of Car2x message with the specified macAddress from "Station2"
C2xTestWaitForSignalMatch("eth", "source", 6, macAddressStation2, "Station2", 1000);

// Form 5: Wait for occurrence of a Car2x message with the CAM lowBeamHeadlights set to 1
C2xTestWaitForSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", "lowBeamHeadlightsOn", 1, 1000);

// Form 6: Wait for occurrence of a Car2x message with the CAM lowBeamHeadlights set to 1 from "Station2"
C2xTestWaitForSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", "lowBeamHeadlightsOn", 0, "Station2", 1000);

// Form 7: Wait for occurrence of a Car2x message in which the bit bitposition 7 in the token exteriorlights is 0.
C2xTestWaitForSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", 7, 0, 1000);

// Form 8: Wait for occurrence of a Car2x message in which the bit bitposition 7 in the token exteriorlights is 0 and which is sent from "Station2".
C2xTestJoinSignalMatch("CAM", "cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.exteriorLights", 7, 0, "Station2", 1000);
```

[C2xTestJoinSignalInRange](CAPLfunctionC2xTestJoinSignalInRange.md) • [C2xTestJoinSignalMatch](CAPLfunctionC2xTestJoinSignalMatch.md) • [C2xTestWaitForSignalInRange](CAPLfunctionC2xTestWaitForSignalInRange.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)