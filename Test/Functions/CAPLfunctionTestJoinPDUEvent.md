# TestJoinPDUEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinPDUEvent(dbPDU aPDU, dword flags); // form 1`
- `long TestJoinPDUEvent(char aPDUName[], dword flags); // form 2`
- `long TestJoinPDUEvent(dword aHeaderID, dword flags); // form 3`
- `long TestJoinPDUEvent(dword flags); // form 4`
- `long TestJoinPDUEvent(dword aHeaderID, dword flags, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint sourceIPEndpoint, ip_Endpoint destinationIPEndpoint); // form 5`
- `long TestJoinPDUEvent(char aPDUName[], dword flags, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint sourceIPEndpoint, ip_Endpoint destinationIPEndpoint); // form 6`

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

**Note:** Consider to set always the appropriate bus context in a [multibus environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md) before the function is called.

## Parameters

- **aPDU**: PDU to be awaited as it is defined in the database. Default value: wait for any PDU.
- **aPDUName**: Name of a PDU to be awaited as it is defined in the database. Possibly the TX node’s name can be given as a prefix, e.g. `<TXNodeName\>::<PDUName\>`.
- **aHeaderID**: The appropriate header ID of the PDU in the database. Whether this denotes the long or short header ID is determined by the flags parameter.

  **Note:** If the header ID is not unique, the function will return on the PDU that is first found in the database. In those cases it is better to use the PDU name.

- **flags**: The lowest bit denotes whether the long or short header ID is to be resolved:
  - `0x0001`: use long header ID instead of short header ID.
  - `0x0008`: if vlanID is set to 0 the value 0 shall be tested and not wildcard.
  - All other bits are reserved and should be set to 0.
- **ethernetPort**: Ethernet port of the specified PDU.
- **direction**: Direction of the specified PDU. Possible values:
  - `0`: Rx only
  - `1`: Tx only
  - `2`: Rx and Tx
- **vlanId**: VlanID of the specified PDU. 0 means wildcard.
- **sourceIPEndpoint**: IP address and UDP/TCP port number of source. If address type is not set, address is used as wildcard. If protocol type is not set, protocol is wildcard.
- **destinationIPEndpoint**: IP address and UDP/TCP port number of destination. If address type is not set, address is used as wildcard. If protocol type is not set, protocol is wildcard.

## Return Values

- **-6**: Parse error, PDU is specified as string, but the name cannot be resolved or the PDU header ID cannot be found.
- **-3**: Join error
- **-2**: Resume due to constraint violation.
- **-1**: General error, for example, functionality is not available.
- **\>0**: Number of the joined event.

## Example

—

[TestJoinPDUEvent](#) • [TestWaitForPDU](CAPLfunctionTestWaitForPDU.md)
