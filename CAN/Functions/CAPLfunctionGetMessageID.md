# getMessageID

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword getMessageID(char messageName[]); // form 1`
- `dword getMessageID(char messageName[], char dbName[]); // form 2`

## Description

Finds out the message ID

## Parameters

- **messageName**: Name of the message.
- **dbName**: Name of the database, needed if the message name is used in more than one database.

## Return Values

Message ID, or (dword)-1 if the message is not found

## Example

```c
dword id;
id = GetMessageID("LightState");
```

[getMessageName](CAPLfunctionGetMessageName.md)
