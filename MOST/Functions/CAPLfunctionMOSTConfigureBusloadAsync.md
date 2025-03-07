[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTConfigureBusloadAsync.md)

**CAPL Functions** » **MOST** » **mostConfigureBusloadAsync**

# mostConfigureBusloadAsync

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2600, VN2610 and VN2640.

## Function Syntax

```plaintext
long mostConfigureBusloadAsync (long channel, long rate, long countertype, long counterpos, long destadr, long pktdatalen, BYTE pktdata[]);
```

## Description

The function configures the busload generator for the asynchronous channel. With the specified rate the generator tries to send packets. Due to arbitration delays, the busload actually generated can deviate from the specified rate.

As an option, the packets can be supplied with a sequence counter.

Load generation can be started with the [mostGenerateBusloadAsync()](CAPLfunctionMOSTGenerateBusloadAsync.md) function.

Busload can also be generated without CAPL programming using the MOST Stress Window.

**Note**  
Busload can also be generated without CAPL programming using the MOST Stress Window.

## Parameters

- **channel**: Channel of the connected MOST hardware.
- **rate**: Number of packets per second. The maximum transmission rate depends on the packet length, the synchronous bandwidth control (SBC) and the MOST loop frequency.
- **countertype**: Sequence counter type:
  - 0: No sequence counter
  - 1: 1 byte counter
  - 2: 2 byte counter (higher quality byte first)
  - 3: 3 byte counter (higher quality bytes first)
  - 4: 4 byte counter (higher quality bytes first)
- **counterpos**: Position of the lowest value sequence counter byte.
- **destadr**: Destination address
- **pktdatalen**: Number of user data bytes (MOST25: 0<= pktdatalen <= 1014, MOST150: 1 <= pktdatalen <= 1524)
- **pktdata[]**: User data

## Return Values

- **<= 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGenerateBusloadAsync](CAPLfunctionMOSTGenerateBusloadAsync.md) • [mostConfigureBusloadCtrl](CAPLfunctionMOSTConfigureBusloadCtrl.md) • [outputMostPkt](CAPLfunctionMOSTOutputMostPkt.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)