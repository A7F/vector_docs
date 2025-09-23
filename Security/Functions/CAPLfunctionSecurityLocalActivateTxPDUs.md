# SecurityLocalActivateTxPDUs

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalActivateTxPDUs

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
Replaces `LocalSecurityActivateTxPDUs`.

## Function Syntax

- `long SecurityLocalActivateTxPDUs(char nodeName[]) // form 1`
- `long SecurityLocalActivateTxPDUs(char nodeName[], char databaseNetwork []) // form 2`
- `long SecurityLocalActivateTxPDUs(char nodeName[], char databaseNetwork [], dword vLanId) // form 3`

## Description

Allows a node (e.g. gateway) to do a MAC calculation for Tx secured PDUs of another node. The calling node registers to all Tx PDUs of the specified node.

You have to set the bus context before you call this method.

This method has to be executed in Pre Start callback of CAPL.

## Parameters

- **char nodeName[]**: Name of the other node.
- **char databaseNetwork[]**: The name of a network in the arxml database. Only for those PDUs the registration takes place. This is an optional parameter. If this parameter is not specified, the PDU registration considers PDUs of all networks in the database where the node with the specified name exists.
- **dword vLanId**: The vLan Id number identifies the Ethernet vLAN. Only PDUs which are transmitted on this vLAN shall be considered, when registering application protocols. If this parameter is not specified, all vLANs are considered.

## Return Values

- **1**: Activation successful.
- **0**: Specified node is already activated.
- **-1**: Specified node is null or empty.
- **-10**: Security is not usable.

## Example

—
