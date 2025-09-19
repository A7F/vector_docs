# CarMaker_Connect

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long CarMaker_Connect(char host[], char user[]);
```

## Description

Creates a connection to the CarMaker instance running on the selected host by the given user. If the user name is an empty string, only the host name is used to select the CarMaker instance. An IPv4 address is also accepted as host name.

## Parameters

- **host**: Host name or IP address of the CarMaker host computer.
- **user**: Name of the user running the CarMaker instance.
  - If this value is an empty string and multiple CarMaker instances are running on the specified host, any instance is connected.
  - If the special name **localuser** is given, the current user of the CANoe RT kernel is resolved and used for the connection.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
on start
{
  // connect to CarMaker instance
  gErrorState = CarMaker_Connect("localhost", "localuser");
}
```
