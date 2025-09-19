[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTConfigureBusloadCtrl.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostConfigureBusloadCtrl

# mostConfigureBusloadCtrl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2600, VN2610, VN2640, OptoLyzer G2 3150o, OptoLyzer MOCCA compact 150c.

## Function Syntax

**MOST25**: `long mostConfigureBusloadCtrl(long channel, long rate, long countertype, long counterpos, long prio, long rtype, long destadr, BYTE pdata[]);`

**MOST150**: `mostConfigureBusloadCtrl(long rate, mostMessage msg);`

## Description

The function configures the busload generator for the control channel. Load generation can be started with the [mostGenerateBusloadCtrl()](CAPLfunctionMOSTGenerateBusloadCtrl.md) function.

**Form 1:**  
With the specified rate the generator tries to send messages on the control channel. Due to repeated transmissions or arbitration delays, the busload actually generated can deviate from the specified rate. As an option, the messages can be supplied with a sequence counter.

**Form 2:**  
For OptoLyzer G2 3150o and OptoLyzer MOCCA compact 150c, rate specifies the delay between two messages in 1 ms steps and hence it is not possible to specify number of messages sent per second.

**Note**  
Busload can also be generated without CAPL programming using the MOST Stress Window.

**VN2600/VN2610**  
Repeated transmissions on the control channel can be eliminated by setting the OS8104 transmit retry register (XRTY) to 1 ([mostWriteReq()](CAPLfunctionMOSTWriteReg.md)).

**VN2640, OptoLyzer G2 3150o and OptoLyzer MOCCA compact 150c**  
A sequence counter and the stress pattern can be configured with [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md).

## Parameters

- **channel**: Channel of the connected MOST hardware.
- **rate**:
  - VN2600/VN2610: Number of messages per second. At best (optimal arbitration), the chip can send (frequency * 21 / 1024) messages per second.
  - VN2640: Number of messages per second.
  - OptoLyzer G2 3150o, OptoLyzer MOCCA compact 150c: Control busload period. Specifies the delay between two messages: 1 means 1 ms, 2 means 2 ms and so on.
- **countertype**: Sequence counter type:
  - 0: No sequence counter
  - 1: 1 byte counter
  - 2: 2 byte counter (higher quality byte first)
  - 3: 3 byte counter (higher quality bytes first)
  - 4: 4 byte counter (higher quality bytes first)
- **counterpos**: Position of the lowest value sequence counter byte.
- **prio**: Sending priority (standard value: 1)
- **rtype**: Message type:
  - 0: Normal
  - 1: RemoteRead
  - 2: RemoteWrite
  - 3: Alloc
  - 4: Dealloc
  - 5: GetSource

  See also [mostRawMessage - Selectors](../Selectors/CAPLfunctionMOSTSelectors.md)
- **destadr**: Destination address of the messages.
- **pdata[]**: 17 user data bytes; for rtype=normal pdata[0] is the message FBlockID.
- **msg**: Variable of type mostMessage; control busload custom message.

## Return Values

- **<= 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

```c
// message data
byte data[17] =
    { 0x01,0x00,0xCC,0xC1,0x04,0x00,0x00,0x00,
      0x00,0x00,0x00,0x00,0x00,0x00,0x00,0x00,
      0x00 };
// configure busload
// channel, rate, countertype, counterpos, prio, rtype, destadr, data
mostConfigureBusloadCtrl(mostGetChannel(), 10, 4, 8, 1, 0, 0x1234, data);
// start busload
mostGenerateBusloadCtrl(mostGetChannel(), 3);
```

Transmits the following messages:

```
DestAdr message data
                  |- counter -|
1234     01 00 CC C1 04 00 00 00 00 00 00 00 00 00 00 00 00
1234     01 00 CC C1 04 00 00 00 01 00 00 00 00 00 00 00 00
1234     01 00 CC C1 04 00 00 00 02 00 00 00 00 00 00 00 00
```

Configure and start busload stress on keyboard event.

```c
on key 's'
{
    long channel, rate;
    mostmessage NetBlock.DeviceInfo.Get msg;

    channel = 1;
    rate = 50; // msgs/s

    // set counter type: 1-byte
    mostSetStressNodeParameter(channel, 16, 1);

    // set counter in byte6 (first user data byte)
    mostSetStressNodeParameter(channel, 17, 6);

    // configure stress pattern
    msg.MsgChannel = channel;
    msg.DA = 0x100;
    mostConfigureBusloadCtrl(rate, msg);

    // start stress: send 10 messages
    mostGenerateBusloadCtrl(channel, 10);
}
```

[mostGenerateBusloadCtrl](CAPLfunctionMOSTGenerateBusloadCtrl.md) • [mostConfigureBusloadAsync](CAPLfunctionMOSTConfigureBusloadAsync.md) • [mostSetStressNodeParameter, mostGetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md) • [OnMostStress](../EventProcedures/CAPLfunctionOnMOSTStress.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
