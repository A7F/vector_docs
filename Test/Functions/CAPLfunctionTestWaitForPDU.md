[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForPDU

# TestWaitForPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForPDU (dbPDU aPDU, dword flags1, dword aTimeout); // form 1`
- `long TestWaitForPDU (char aPDUName[], dword flags2, dword aTimeout); // form 2`
- `long TestWaitForPDU (dword aHeaderID, dword flags3, dword aTimeout); // form 3`
- `long TestWaitForPDU (dword flags4, dword aTimeout); // form 4`
- `long TestWaitForPDU (dbPDU aPDU, dword flags1, dword vlanId, dword aTimeout); // form 5`
- `long TestWaitForPDU (char aPDUName[], dword flags2, dword vlanId, dword aTimeout); // form 6`
- `long TestWaitForPDU (dword aHeaderID, dword flags3, dword vlanId, dword aTimeout); // form 7`
- `long TestWaitForPDU (char aPDUName[], dword flags2, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint sourceIPEndpoint, ip_Endpoint destinationIPEndpoint, dword aTimeout); // form 8`
- `long TestWaitForPDU (dword aHeaderID, dword flags3, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint sourceIPEndpoint, ip_Endpoint destinationIPEndpoint, dword aTimeout); // form 9`

## Description

Waits for the occurrence of the specified PDU. Should the PDU not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

When no PDU is specified the wait condition is resolved on any PDU.

**Note:** Consider to set always the appropriate bus context in a [multibus environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md) before the function is called.

## Parameters

- **aPDU**: PDU to be awaited as it is defined in the database.
- **aPDUName**: Name of a PDU to be awaited as it is defined in the database. Possibly the TX node’s name can be given as a prefix, e.g. `<TXNodeName>::<PDUName>`.
- **aHeaderID**: The appropriate header ID of the PDU in the database. Whether this denotes the long or short header ID is determined by the flags parameter.

  **Note:** If the header ID is not unique, the function will return on the PDU that is first found in the database. In those cases it is better to use the PDU name.

- **flags3**: Some flags to configure special behaviors. A value of 0 means all flags are deactivated (default).
  - 0x0001 – use long header ID instead of short head ID
  - 0x0008 – if vlanID is set to 0 the value 0 shall be tested and not wildcard

  All other bits are reserved and should be set to 0.

- **flags1, flags2, flags4**: Some flags to configure special behaviors. A value of 0 means all flags are deactivated (default).
  - 0x0008 – if vlanID is set to 0 the value 0 shall be tested and not wildcard

  All other bits are reserved and should be set to 0.

- **ethernetPort**: Ethernet port of the specified PDU.
- **direction**: Direction of the specified PDU. Possible values:
  - 0: Rx only
  - 1: Tx only
  - 2: Rx and Tx

- **vlanId**: VlanID of the specified PDU. 0 means wildcard.
- **sourceIPEndpoint**: Source IP address and port number.
- **destinationIPEndpoint**: Destination IP address and port number.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling

## Return Values

- **-6**: Parse error, PDU is specified as string, but the name cannot be resolved or the PDU header ID cannot be found.
- **-5**: Uninitialized Ethernet port.
- **-2**: Resume due to constraint violation.
- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

## Example

—

[TestGetWaitPDUData](CAPLfunctionTestGetWaitPDUData.md) • [TestJoinPDUEvent](CAPLfunctionTestJoinPDUEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
