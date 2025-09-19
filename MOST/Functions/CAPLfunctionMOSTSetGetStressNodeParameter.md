[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetGetStressNodeParameter.md)

**CAPL Functions** » **MOST** » **mostSetStressNodeParameter, mostGetStressNodeParameter**

# mostSetStressNodeParameter, mostGetStressNodeParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640, OptoLyzer G2 3150o, OptoLyzer, MOCCA compact 50e and OptoLyzer MOCCA compact 150c.

## Function Syntax

**MOST50 / MOST150**: `long mostSetStressNodeParameter(long channel, long id, long value);`  
**MOST50 / MOST150**: `long mostGetStressNodeParameter(long channel, long id);`

## Description

**VN2640:**  
Additional parameters of the stress generators ([mostGenerateBusloadCtrl](CAPLfunctionMOSTGenerateBusloadCtrl.md), [mostGenerateBusloadAsync](CAPLfunctionMOSTGenerateBusloadAsync.md), [mostGenerateBusloadEthPkt](CAPLfunctionMOSTGenerateBusloadEthPkt.md)) can be set with `mostSetStressNodeParameter`.

**OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e and OptoLyzer MOCCA compact 150c:**  
The interfaces for MOST150 provide stress functionality through an additional network interface controller (NIC). For a set of stress functions ([mostSetRxBufferCtrl](CAPLfunctionMOSTSetRxBufferCtrl.md), [mostSyncAlloc](CAPLfunctionMOSTSyncAlloc.md)) the NIC is required to be visible in the network (bypass open).

With `mostSetStressNodeParameter` the MOST node parameters of this additional NIC can be configured.

## Parameters

- **channel**: Channel of the connected interface.
- **id**: Parameter identification:
  - **1**: Node address (0...0xFFFF)
    - Availability: OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **2**: Group address (0x300...0x3FF)
    - Availability: OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **3**: Bypass
    - Values: 0: open bypass, 1: retimed bypass (only for OptoLyzer G2 3150o), 2: active bypass
    - Availability: OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **10**: Control busload destination address (0...0xFFFF)
    - Availability: VN2640, OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **11**: Control busload speed/value range
    - VN2640: Messages per second
    - OptoLyzer G2 3150o, OptoLyzer MOCCAcompact50e: >0: Specifies the delay between two packets (in ms), =0: send as fast as possible
    - Availability: VN2640, OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **12**: Control busload pattern: specifies what message is sent as busload
    - 0: FBlockID: 0xF1, InstID: 0x00, FuncID: 0xFFF, OpType: 0xC, Length
    - 2: (OptoLyzer G2 3150o, OptoLyzer MOCCA compact 150c only) FBlockID: 0x01, InstID: 0x00, FuncID: 0x000, OpType: 0x1
    - 16: (OptoLyzer G2 3150o, OptoLyzer MOCCA compact 150c only) custom message (to specify custom message use function [mostConfigureBusloadCtrl](CAPLfunctionMOSTConfigureBusloadCtrl.md))
    - Availability: OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **13**: Control busload pattern length: amount of payload sent as busload, applies for pattern 0x00 only
    - 6...51 (OptoLyzer G2 3150o, OptoLyzer MOCCA compact 150c), 5...17 (OptoLyzer MOCCA compact 50e)
    - Availability: OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **14**: Control busload burst count: amount of messages sent as busload per (10 ms) cycle. For further information regarding the burst mode please refer to K2L socket protocol specification.
    - 1...65535
    - Availability: OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **15**: Control busload send attempts
    - 1...16
    - Availability: VN2640, OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **16**: Control busload counter type
    - 0: no counter, 1...4: 1-4 byte counter
    - Availability: VN2640, OptoLyzer G2 3150o
  - **17**: Control busload counter position: specifies the position of the payload byte that is incremented
    - 6...50
    - Availability: VN2640, OptoLyzer G2 3150o
  - **50**: Data packet channel busload destination address (0...0xFFFF)
    - Availability: VN2640, OptoLyzer G2 3150o, MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **51**: Data packet channel busload speed/value range
    - VN2640: Packets per second
    - OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c: >0: Specifies the delay between two packets (in ms), =0: send as fast as possible
    - Availability: VN2640, OptoLyzer G2 3150o, MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **52**: Data packet channel busload pattern: specifies what a message is sent as busload
    - 0: FBlockID: 0xF1, InstID: 0x00, FuncID: 0xFFF, OpType: 0xC, Length (2 Byte)
    - Availability: OptoLyzer G2 3150o, MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **53**: Data packet channel busload pattern length
    - 6...48 (OptoLyzer G2 3150o, OptoLyzer MOCCA compact 150c), 6…1014 (OptoLyzer MOCCA compact 50e)
    - Availability: OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, OptoLyzer MOCCA compact 150c
  - **55**: Send attempts for data packet busload
    - 1...16
    - Availability: VN2640
  - **56**: Data packet busload counter type
    - 0: no counter, 1...4: 1-4 byte counter
    - Availability: VN2640
  - **57**: Data packet busload counter position
    - 0...1523
    - Availability: VN2640
  - **75**: Send attempts for Ethernet busload packet
    - 1...16
    - Availability: VN2640
  - **76**: Ethernet busload counter type
    - 0: no counter, 1...4: 1-4 byte counter
    - Availability: VN2640
  - **77**: Ethernet busload counter position
    - 0...1505
    - Availability: VN2640

- **value**: Parameter value to be set.

## Return Values

- **mostSetStressNodeParameter**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)
- **mostGetStressNodeParameter**:
  - >=0: Parameter value
  - <0: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

**Example VN2640**  
See [mostConfigureBusloadCtrl](CAPLfunctionMOSTConfigureBusloadCtrl.md)

**Example OptoLyzer G2 3150o**  

```c
// configure stress controller as visible network node with logical address 0x123
mostSetStressNodeParameter(1, 1, 0x123); // set node address
mostSetStressNodeParameter(1, 3, 0); // open bypass
```

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSyncDealloc](CAPLfunctionMOSTSyncDealloc.md) • [mostSetStressNodeParameterData](CAPLfunctionMOSTSetStressNodeParameterData.md) • [mostSetAllBypass](CAPLfunctionMOSTSetAllBypass.md) • [mostSetNodeAdr](CAPLfunctionMOSTSetNodeAdr.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
