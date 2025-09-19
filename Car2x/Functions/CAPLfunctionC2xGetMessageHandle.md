# C2xGetMessageHandle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xGetMessageHandle(char* dbMessage); // form 1`
- `long C2xGetMessageHandle(char* stationName, char* dbMessage); //form 2`
- `long C2xGetMessageHandle(uint64 stationID, long sequenceNumber); //form 3`
- `long C2xGetMessageHandle(char* stationName, uint64 stationID, long sequenceNumber); //form 4`

## Description

This function returns the packet handle for a specified Car2x message. Form 3 & 4 only work for stations where one or more DENMs are active.

## Parameters

- **dbMessage**: Name of the message
- **stationName**: Name of the specified station
- **stationID**: Id of the station that sends multiple DENM messages
- **sequenceNumber**: Sequence number of the specified DENM messages

## Return Values

- **-1**: General error, for example, functionality is not available
- **>0**: Handle of the packet

## Example

```c
//Form 1: Single DENM or other application message
long handle;
handle= C2xGetMessageHandle("DENM");

//Form 3: Multiple DENM active

long eeblPacketHdl = 0;
long emcyPacketHdl = 0;
long rwwPacketHdl = 0;
long causeCode = 0;
eeblPacketHdl = C2xGetMessageHandle(1,1);
emcyPacketHdl = C2xGetMessageHandle(1,2);
rwwPacketHdl  = C2xGetMessageHandle(1,3);

causeCode=C2xGetTokenInt64(eeblPacketHdl,"DENM", "denm::situation::eventType::causeCode");
Write("EEBL CauseCode: %d", causeCode);
causeCode=C2xGetTokenInt64(emcyPacketHdl,"DENM", "denm::situation::eventType::causeCode");
Write("Emergency Vehicle CauseCode: %d", causeCode);
causeCode=C2xGetTokenInt64(rwwPacketHdl,"DENM", "denm::situation::eventType::causeCode");
Write("Roadworks CauseCode: %d", causeCode);
```
