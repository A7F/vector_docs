[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalActivateRxPDUs.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalActivateRxPDUs

# SecurityLocalActivateRxPDUs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces `LocalSecurityActivateRxPDUs`.

## Function Syntax

- `long SecurityLocalActivateRxPDUs(char nodeName[]) // form 1`
- `long SecurityLocalActivateRxPDUs(char nodeName[], char databaseNetwork []) // form 2`
- `long SecurityLocalActivateRxPDUs(char nodeName[], char databaseNetwork [], dword vLanId) // form 3`

## Description

Allows a node (e.g. gateway) to validate Rx secured PDUs of another node. The calling node registers to all Rx PDUs of the specified node. You have to set the bus context before you call this method. This method has to be executed in Pre Start callback of CAPL.

## Parameters

- **char nodeName []**: Name of the other node.
- **char databaseNetwork[]**: The name of a network in the arxml database. Only for those PDUs the registration takes place. This is an optional parameter. If this parameter is not specified, the PDU registration considers PDUs of all networks in the database where the node with the specified name exists.
- **dword vLanId**: The vLan Id number identifies the Ethernet vLAN. Only PDUs which are transmitted on this vLAN shall be considered, when registering application protocols. If this parameter is not specified, all vLANs are considered.

## Return Values

- **1**: Activation successful
- **0**: Specified node is already activated
- **-1**: Specified node is null or empty
- **-10**: Security is not usable

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
