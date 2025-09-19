[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetNodeAdr.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetNodeAdr, mostSetGroupAdr, mostSetAltPktAdr, mostSetOwnAdr

# mostSetNodeAdr, mostSetGroupAdr, mostSetAltPktAdr, mostSetOwnAdr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostSetNodeAdr(long channel, long nodeadr);`
- `long mostSetGroupAdr(long channel, long grpadr);`
- `long mostSetAltPktAdr(long channel, long altpktadr);`
- `long mostSetOwnAdr(long channel, long grpadr, long nodeadr);`

## Description

These functions set the node address, group address or alternative packet address of the MOST hardware to the specified values.

## Parameters

- **channel**: Channel of the connected interface
- **nodeadr**: Logical node address
- **groupadr**: Group address
- **altpktadr**: Alternative packet address
- **nodeposadr**: Node position address

## Return Values

- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetNodeAdr, mostGetGroupAdr, mostGetAltPktAdr, mostGetNodePosAdr](CAPLfunctionMOSTGetNodeAdr.md) • [OnMostNodeAdr](../EventProcedures/CAPLfunctionOnMOSTNodeAdr.md) • [OnMostGroupAdr](../EventProcedures/CAPLfunctionOnMOSTGroupAdr.md) • [OnMostNPR](../EventProcedures/CAPLfunctionOnMOSTNPR.md) • [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetMacAdr](CAPLfunctionMOSTSetGetMacAdr.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
