# C2xTestWaitForMessage

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xTestWaitForMessage.md)

**CAPL Functions** » **Car2x** » **C2xTestWaitForMessage**

**Valid for**: CANoe DE

## Function Syntax

- `long C2xTestWaitForMessage(char* appMsg, long aTimeout)` // form 1
- `long C2xTestWaitForMessage(char* appMsg, char* stationName, long aTimeout)` // form 2

## Description

Waits for the occurrence of the first Car2x message matching the conditions passed as arguments. Should the message not occur before the expiration of the time `aTimeout`, the wait condition is resolved nevertheless.

## Parameters

- **appMsg**: Name of application message of the Car2x message that should be awaited.
- **stationName**: Name of the sender station of the Car2x message that should be awaited.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

## Example

```plaintext
long result;
// Form 1: Wait for occurrence of Car2x message with application message "CAM"
result = C2xTestWaitForMessage("CAM", 1000);

// Form 2: Wait for occurrence of Car2x message with application message "CAM" and sender "Station1"
result = C2xTestWaitForMessage("CAM", "Station1", 1000);
```

[C2xTestJoinMessage](CAPLfunctionC2xTestJoinMessage.md) • [C2xTestGetWaitForMessage](CAPLfunctionC2xTestGetWaitForMessage.md)
