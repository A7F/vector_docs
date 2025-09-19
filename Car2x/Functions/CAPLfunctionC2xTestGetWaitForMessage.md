# C2xTestGetWaitForMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xTestGetWaitForMessage(long &packethandle)` // form 1
- `long C2xTestGetWaitForMessage(long index, long &packethandle)` // form 2

## Description

If a valid Car2x message is the last event that triggers a wait instruction, the packet's handle can be called up with form 1.

Form 2 can only be used for **joined events**. The number of the **joined event** (return value of **C2xTestJoin…**) is here being used as an index.

## Parameters

- **packetHandle**: A packet handle for the awaited Car2x message.
- **Index**: Number of the **joined event** corresponds with the return value of **C2xTestJoin…**.

## Return Values

- **0**: Data access successful.
- **-1**: Data access could not be executed, the last event was not an Car2x event.

## Example

```plaintext
long index;
long packet;
int version;

//Form 1
C2xTestWaitForMessage("CAM",1000);
C2xTestGetWaitForMessage(packet);
version = C2xGetTokenInt(packet,"geo_bh","version");

//Form 2
C2xTestJoinMessage("CAM", "Station1");
// more joined events
// ...
index = testWaitForAnyJoinedEvent(1000);
C2xTestGetWaitForMessage(index, packet);
```

[C2xTestWaitForMessage](CAPLfunctionC2xTestWaitForMessage.md) • [C2xTestJoinMessage](CAPLfunctionC2xTestJoinMessage.md)
