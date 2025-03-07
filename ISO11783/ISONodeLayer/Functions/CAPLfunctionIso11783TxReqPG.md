[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783TxReqPG.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » **Iso11783TxReqPG**

# Iso11783TxReqPG

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783TxReqPG( dword ecuHandle, dword pgn, dword destination, dword priority, dword dlc, char data[] );
```

```plaintext
dword Iso11783TxReqPG( dword ecuHandle, dword pgn, dword destination, dword priority, dword dlc, byte data[] );
```

## Description

Sends any PG. The node layer handles fragmenting automatically. As soon as the PG has been transferred, [Iso11783AppTxIndication()](CAPLfunctionIso11783AppTxIndication.md) is called. This gives the application the possibility of protocol monitoring, especially in the case of fragmented PGs.

**Note**

It should be noted with this function that the destination address must be transferred in a separate parameter `dest` for PDU Format I. The PDUS byte of `pgNum` must therefore contain "00". The PG is then transferred to a specific destination address (as a CMDT if appropriate).

In the case of PDU Format II the total PG number is transferred in `pgNum`. The value in `dest` will then be ignored. The parameter group is sent globally (in some cases as BAM). In this version, you should note that each immediately sequential, fragmented PG for an ECU cannot be sent until after the TxIndication of the previous one has been received. If the data length fits with the transmission protocol, the return value is "0" and the PGN is sent. Otherwise a non-zero value will be returned and the message will not be transferred.

## Parameters

- **ecuHandle**: ECU handle
- **pgn**: PGN which should be sent
- **destination**: Destination address or global address (255)
- **priority**: Priority
- **dlc**: Number of data bytes
- **data**: Data

## Return Values

0 on success or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
char data[14];

// global parameter group
res = Iso11783TxReqPG(ecuHdl, 0xFE45, 0xFF, 4, 14, data);

// specific parameter group:
res = Iso11783TxReqPG(ecuHdl, 0xE600, 0x09, 4, 14, data);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)