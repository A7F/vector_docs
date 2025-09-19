# applILTxPending

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The CAPL program may define these optional functions (all marked with the prefix **applIL**) to receive indications about events from the IL.  
**Caution**: Within this callback the **setSignal** functionality must not be used, since it might trigger further unwanted transmissions.

## Function Syntax

```
dword applILTxPending(long aId, dword aDlc, byte data[]);
```

## Description

This callback is optionally being called before the IL sends a message to the bus. In this callback it is possible to prevent the sending of the message or to change the data of the message.

## Parameters

- **aId**: With the ID you can identify the message.
- **aDLC**: The DLC of the message to be sent and the length of the data bytes array.
- **data**: Data bytes array with the bytes to be sent. The bytes can optionally be changed.

## Return Values

- **0**: Sending of the message with the supplied **aId** is prevented.
- **1**: Sending of the message with the supplied **aId** is done.

## Example

**Calculation of a checksum and a message counter:**

```c
dword applILTxPending (long aId, dword aDlc, byte data[])
{
  dword i;
  byte xor;
  /* Message 0x1A0 contains a XOR checksum in Byte 0. It will
  /* be calculated from the other data bytes of the message.
  */
  if(aId == 0x1A0)
  {
    // calculate
    xor = 0x00;
    for(i = 1; i < aDlc; ++i) {
      xor = xor ^ data[i];
    }
    // set the new checksum
    data[0] = xor;
  }
  /* Message 0x1A1 contains a 4-Bit message counter in
  /* the first 4 Bits of Byte 0.
  */
  if(aId == 0x1A1)
  {
    // get the old value
    i = data[0] & 0x0F;
    // increment
    i++;
    i = i % 16;
    //set the new message counter
    data[0] = i & 0x0F;
  }
  return 1; // don't prevent sending of the message
}
```
