[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429SetConfiguration.md)

[CAPL Functions](../../CAPLfunctions.md) » [A429](../CAPLfunctionsA429Overview.md) » a429SetConfiguration

# a429SetConfiguration

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long a429SetConfiguration( long channel, a429settings mySettings );
```

## Description

This function sets the actual channel configuration. Internally the function [a429ResetEx](CAPLfunctionA429ResetEx.md) is called to apply the changes.

## Parameters

- **channel**: valid channel number
- **mySettings**: variable to provide channel parameters

## Return Values

- **0**: channel parameters could not be written
- **1**: parameters successfully written

## Example

```plaintext
variables
{
  long RxChannel = 5;
  long TxChannel = 1;

  a429Settings ValidSetTx[2] = {
    { Bitrate = 100000, // default high-speed
      RxMinBitrate = 10500,
      RxMaxBitrate = 120000,
      MinGap = 32,
      Parity = a429OddParity,
      Flags = a429FlagsTx
    },
    { Bitrate = 12500, // default low-speed
      RxMinBitrate = 10500,
      RxMaxBitrate = 120000,
      MinGap = 32,
      Parity = a429OddParity,
      Flags = a429FlagsTx
    }
  };

  a429Settings ValidSetRx[2] = {
    { Bitrate      = 100000, // default high-speed
      RxMinBitrate = 97560,
      RxMaxBitrate = 102400,
      MinGap       = 32,
      Parity       = a429OddParity,
      Flags        = a429FlagsRx
    },
    { Bitrate = 12500, // default low-speed
      RxMinBitrate = 12188,
      RxMaxBitrate = 12810,
      MinGap = 32,
      Parity = a429OddParity,
      Flag = a429FlagsRx
    }
  };
}

// set channels to low speed
on key 'l'
{
  if (a429SetConfiguration(TxChannel, ValidSetTx[1])) {
    write("channel '%d' configured: OK", TxChannel);
  }
  else {
    write("channel '%d' not configured: FAILED", TxChannel);
  }
  if (a429SetConfiguration(RxChannel, ValidSetRx[1])) {
    write("channel '%d' configured: OK", RxChannel);
  }
  else {
    write("channel '%d' not configured: FAILED", RxChannel);
  }
}

// set channels to high speed
on key 'h'
{
  if (a429SetConfiguration(TxChannel, ValidSetTx[0])) {
    write("channel '%d' configured: OK", TxChannel);
  }
  else {
    write ("channel '%d' not configured: FAILED", TxChannel);
  }
  if (a429SetConfiguration(RxChannel, ValidSetRx[0])) {
    write("channel '%d' configured: OK", RxChannel);
  }
  else {
    write("channel '%d' not configured: FAILED", RxChannel);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)