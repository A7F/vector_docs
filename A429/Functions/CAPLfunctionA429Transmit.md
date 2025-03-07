[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429Transmit.md)

**CAPL Functions** » **A429** » **a429Transmit**

# a429Transmit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long a429Transmit (a429word myA429Word[], dword myNum);
```

## Description

This function triggers the transfer of `myNum A429words` to the network interface at once. When the mode **Simulated bus** is used, a built-in simulation layer takes care of the ARINC word.

The following restrictions apply:

- All ARINC words are transmitted on the same channel. The channel of the first array entry pointed to by `myA429Word[0]` is used.
- With a single call of this function, 64 ARINC words may be transferred to the hardware at once.
- The ARINC word selectors TxCtrl and TxCycle are ignored.

**Note** that the ARINC word selector **Gap** (see [a429SetGap](CAPLfunctionA429SetGap.md)) may be used to adjust the distance between the ARINC words. A single ARINC word is transmitted or updated with [output](CAPLfunctionA429output.md).

**Attention:** Be aware that the hardware queue size is limited; therefore calling this method rapidly may cause a queue overflow.

## Parameters

- **myA429word**: array of ARINC words
- **myNum**: [1...64] number of elements to be sent from `myA429word`

## Return Values

- **0**: myNum ARINC words were transferred successfully to the hardware.
- **1...64**: the number of ARINC words not transferred to hardware (hardware queue full)
- **-1**: invalid channel
- **-2**: invalid number of labels (0 or > 64)
- **-3**: output not allowed on this channel
- **-4**: measurement not yet running (e.g. on start or on prestart)
- **-5**: transmission error on hardware (besides hardware queue full)

## Example

Transmit ARINC words on request:

```plaintext
variables
{
  a429Word * myWord[3];
}

on start {
  int i;
  for (i = 0; i < elCount(myWord); i++) {
    myWord[i].msgChannel = 2;
    myWord[i].Id = 64 + i; // create different label numbers
    // send 3 ARINC words with 38.75 and 37.5 us gap
    a429SetGap (myWord[i],
                a429CalcBitLength(myWord[i].msgChannel, 32 - i));
  }
}

on key 's' {
  int i;
  for (i = 0; i < elCount(myWord); i++) {
    myWord[i].byte(1) += 1;
  }
  a429Transmit(myWord, elCount(myWord)); // update
}
```

## Availability

- **Since Version**: CANalyzer 9.0 SP2, CANoe 9.0 SP2
- **Restricted To**: A429
- **CANalyzer Measurement Setup (Transmit Branch)**: ✔
- **CANoe Simulation Setup**: ✔
- **CANoe Communication Setup**: ✔
- **CANoe Test Setup for Test Modules**: ✔
- **CANoe Test Setup for Test Units**: ✔
- **32-Bit**: ✔
- **64-Bit**: ✔

[See Also](javascript:void(0);)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)