# canFdGetConfiguration, canFdSetConfiguration

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canFdSetConfiguration(long channel, canSettings abrSettings, canSettings dbrSettings);
long canFdGetConfiguration(long channel, canSettings abrSettings, canSettings dbrSettings);
```

## Description

The CAN controller parameters for arbitration and data phase can be set or read.

`canFdSetConfiguration` performs an automatic reset of the CAN controller.

## Parameters

- **Channel**: The CAN channel.

- **struct canSettings**:
  - `float baudrate`: in bit/s
  - `unsigned char tseg1, tseg2`: length of the time segments 1 and 2 in time quanta
  - `unsigned char sjw`: sync jump width in time quanta
  - `unsigned char sam`: number of sampling points (1 or 3). Only valid for CAN. For CAN FD "sam" is hard coded to 1.
  - `unsigned int flags`: see description below

### Flags for canFdGetConfiguration:

- **Bit Position 0, 1**:
  - 0: unknown transceiver
  - 1: Low speed
  - 2: Single wire
  - 3: High speed

- **Bit Position 8**:
  - 0x100: The channel is configured for CAN FD

- **All others**: Reserved

### Flags for canFdSetConfiguration:

- **Bit Position 0**:
  - 0: normal mode
  - 1: silent mode (acknowledge not created)

- **All others**: Reserved, and must be 0.

## Return Values

- **1**: success
- **0**: error

## Example

```plaintext
int ret;
int channel = 1;
CANsettings abrSettings;

CANsettings dbrSettings;

abrSettings.baudrate = 1000000;
abrSettings.tseg1=5;
abrSettings.tseg2=2;
abrSettings.sjw=2;
abrSettings.sam=1;
abrSettings.flags = 0;

dbrSettings.baudrate = 4000000;
dbrSettings.tseg1=6;
dbrSettings.tseg2=3;
dbrSettings.sjw=2;
dbrSettings.sam=1;
dbrSettings.flags = 0;

write("Set 1 MB");
ret = canFdSetConfiguration(channel, abrSettings, dbrSettings);

if (ret)
{
    write("Arbitration settings: baud= %f, tseg1 = %d, tseg2= %d, sjw = %d, sam = %d, flags = 0x%x", abrSettings.baudrate, abrSettings.tseg1, abrSettings.tseg2, abrSettings.sjw, abrSettings.sam, abrSettings.flags);
    write("Data settings: baud= %f, tseg1 = %d, tseg2= %d, sjw = %d, sam = %d, flags = 0x%x", dbrSettings.baudrate, dbrSettings.tseg1, dbrSettings.tseg2, dbrSettings.sjw, dbrSettings.sam, dbrSettings.flags);
}
```
