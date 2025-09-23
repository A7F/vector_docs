# J1939UpdateTable

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939UpdateTable( char busName[] );
```

## Description

Updates the network table.

The function deletes the content of the current table and initiates the RequestPGN that was used to request Address Claiming. After that, the table is restructured. With `busName`, you assign a table which is used in a network. A node which was displaced from the network if it has lost the Address Claiming, will be placed in the network table with the NULL address. After calling this function, all contents of the table will be deleted and the table will update itself by sending a request. All ECU which sends the NULL address will be ignored. Only the active nodes will be inserted into the table.

## Parameters

- **busName**: bus name or "default"

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```plaintext
J1939UpdateTable( "default" );
```
