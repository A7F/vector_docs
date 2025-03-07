[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetSetConfiguration.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canGetConfiguration, canSetConfiguration

# canGetConfiguration, canSetConfiguration

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetConfiguration(long channel, canSettings settings);
long canSetConfiguration(long channel, canSettings settings);
```

## Description

The CAN controller parameters can be set or read.

`canSetConfiguration` performs an automatic reset of the CAN controller.

## Parameters

- **Channel**: The CAN channel.
- **struct canSettings**:
  - `float baudrate;` // in bit/s
  - `unsigned char tseg1, tseg2;` // length of the time segments 1 and 2 in time quanta
  - `unsigned char sjw;` // sync jump width in time quanta
  - `unsigned char sam;` // number of sampling points (1 or 3)
  - `unsigned int flags;` // see description below

Flags for `canGetConfiguration`:
- **Bit Position 0, 1**:
  - 0: unknown transceiver
  - 1: Low speed
  - 2: Single wire
  - 3: High speed
- **Bit Position 8**:
  - 0x100: The channel is configured for CAN FD
- **All others**: Reserved

Flags for `canSetConfiguration`:
- **Bit Position 0**:
  - 0: Normal mode
  - 1: Silent mode (acknowledge not created)
- **All others**: Reserved, and must be 0.

## Return Values

- **1**: success
- **0**: error

## Example

```plaintext
int ret;
int channel = 1;
canSettings settings;
settings.baudrate = 1000000;
settings.tseg1=5;
settings.tseg2=2;
settings.sjw=2;
settings.sam=1;
settings.flags = 0;

write("Set 1 MB");
ret = canSetConfiguration(channel, settings);

ret = canGetConfiguration(channel, settings);
if (ret)
{
    write("Settings: baud= %f, tseg1 = %d, tseg2= %d, sjw = %d, sam = %d, flags = 0x%x",
          settings.baudrate, settings.tseg1, settings.tseg2, settings.sjw, settings.sam, settings.flags);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)