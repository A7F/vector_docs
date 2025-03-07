[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetNodeAdr.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetNodeAdr, mostGetGroupAdr, mostGetAltPktAdr, mostGetNodePosAdr

# mostGetNodeAdr, mostGetGroupAdr, mostGetAltPktAdr, mostGetNodePosAdr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostGetNodeAdr(long channel); // form 1`
- `long mostGetGroupAdr(long channel); // form 2`
- `long mostGetAltPktAdr(long channel); // form 3`
- `long mostGetNodePosAdr(long channel); // form 4`

## Description

Return of the node address, group address, alternative packet address or node position address of the MOST hardware associated with the specified channel.

## Parameters

- **channel**: Channel of the connected interface.

## Return Values

- **NodeAdr**: Logical node address
- **GroupAdr**: Group address
- **AltPktAdr**: Alternative packet address
- **NodePosAdr**: Node position address
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetNodeAdr, mostSetGroupAdr, mostSetAltPktAdr, mostSetOwnAdr](CAPLfunctionMOSTSetNodeAdr.md) • [OnMostNodeAdr](../EventProcedures/CAPLfunctionOnMOSTNodeAdr.md) • [OnMostGroupAdr](../EventProcedures/CAPLfunctionOnMOSTGroupAdr.md) • [OnMostNPR](../EventProcedures/CAPLfunctionOnMOSTNPR.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)