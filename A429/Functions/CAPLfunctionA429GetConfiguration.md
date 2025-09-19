# a429GetConfiguration

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long a429GetConfiguration( long channel, a429settings mySettings );
```

## Description

This function returns the actual channel configuration settings.

## Parameters

- **channel**: valid channel number
- **mySettings**: variable to store channel parameters

## Return Values

- **0**: channel parameters could not be retrieved
- **1**: parameters successfully read

## Example

```plaintext
on key 'c'
{
  long channel;
  a429settings mySettings;

  channel = RxChannel;
  if (a429GetConfiguration(channel, mySettings)) {
    write ("parameters of channel '%d', bitrate '%d' (%d .. %d), parity = '%s', flags = '%s'", channel, mySettings.Bitrate, mySettings.RxMinBitrate, mySettings.RxMaxBitrate, ((enum Ea429ParityCtrl)mySettings.Parity).name(), ((enum Ea429SettingsFlags)mySettings.Flags).name());
  }
  else {
    write(" parameters for '%d' not available");
  }
}
```
