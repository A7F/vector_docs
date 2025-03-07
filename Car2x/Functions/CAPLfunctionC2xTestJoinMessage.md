[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xTestJoinMessage.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xTestJoinMessage

# C2xTestJoinMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xTestJoinMessage(char* AppMsg)` //form 1
- `long C2xTestJoinMessage(char* AppMsg, char* stationName)` //form 2

## Description

Completes the current set of joined events with the transmitted event. This function does not wait.

## Parameters

- **appMsg**: Name of application message of the Car2x message that should be awaited.
- **stationName**: Name of the sender station of the Car2x message that should be awaited.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **>0**: Number of the joined event.

## Example

```c
long index;
long packet;

//Form 1
index = C2xTestJoinMessage("DENM");
//Form 2
C2xTestJoinMessage("CAM", "Station1");
testWaitForAllJoinedEvents(1000);
//Get message of first joined event
C2xTestGetWaitForMessage(index, packet);
```

[C2xTestGetWaitForMessage](CAPLfunctionC2xTestGetWaitForMessage.md) • [C2xTestWaitForMessage](CAPLfunctionC2xTestWaitForMessage.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)