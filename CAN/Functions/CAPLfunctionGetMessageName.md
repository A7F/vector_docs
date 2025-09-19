# getMessageName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword getMessageName( dword id, dword context, char buffer[], dword size)
```

## Description

Finds out the message name.

## Parameters

- **id**: Id of the message for which the message name should be found.
- **context**: Context of assigned databases.
  - The low word of context contains the channel number.
  - The high word of context contains the bus system.
  - Available bus systems:
    - **CAN**: 1
    - **LIN**: 5
    - **MOST**: 6
    - **FlexRay**: 7
    - **J1708**: 9
- **buffer**: Buffer in which the message name is written.
- **size**: Size of the buffer in Byte.

## Return Values

If successful unequal 0, otherwise 0.

## Example

```plaintext
variables
{
  dword contextCAN = 0x00010000;
  dword contextLIN = 0x00050000;
  dword contextMOST = 0x00060000;
  dword contextFLEXRAY = 0x00070000;
  dword contextBEAN = 0x00080000;
  dword contextJ1708 = 0x00090000;
}
on message *
{
  char buffer[64];
  if ( getMessageName( this.ID, contextCAN | this.CAN, buffer, elcount( buffer)))
  {
    write( "Message: %s", buffer);
  }
}
```

[getFirstCANdbName](CAPLfunctionGetFirstCANdbName.md) • [getNextCANdbName](CAPLfunctionGetNextCANdbName.md)
