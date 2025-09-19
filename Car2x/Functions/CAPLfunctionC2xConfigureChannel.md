# C2xConfigureChannel

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xConfigureChannel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long C2xConfigureChannel(long appChannel, long radioChannel, long txPower, long maxTxPower, long layout, long dataRate, long bandWidth, long txAntenna, long rxAntenna)
```

## Description

Configure a hardware channel. This method allows to redefine some or all channel parameters on the fly, i.e. for all following activities on a specific VN4610 channel those new settings will be used. In fact, the method overwrites the corresponding internal configuration settings provided by the setup-dialog.

- To redefine just a subset of the channel parameters, a value of `<-1>` can be used for most entries other than both txPower-parameters; for those two, the value `<-100>` can be used for this purpose.
- To set just a subset of the parameters, the value `<-1>` can be used for antenna, dataRate, and expiry to leave the corresponding parameters of the configuration unchanged.

**Notes:**

- This method can only be used with VN4610 hardware.
- This method reconfigures the device internally and blocks regular operation for a couple of 10msec, so packets might be lost.

## Parameters

- **appChannel**: Channel to apply settings to (1 .. n), n = available hardware channels (1=Ath1, 2=Ath2,…)
- **radioChannel**: Used radio channel (172, 174, 175, 176, 178, 180, 181, 182, 184)
- **txPower**: Default transmission power in dBm for ACK / CTS-messages, if not using individual transmission power setting by C2xOutputPacket; use "-100" to keep the original setting.
- **maxTxPower**: Maximum transmission power which will not be exceeded even if requested by txPower setting or OutputPacket. Use "-100" to keep the original setting.
- **layout**: 0: LPD, 1: EPD protocol
- **dataRate**: Data rate [Mbps] to be used (use "4" to set 4.5Mbps); Allowed values: 3,4,6,9,12,18,24,27; -1: keep the original setting
- **bandwidth**: Used channel bandwidth (10: 10 MHz; 20: 20Mhz)
- **txAntenna**: Antenna used for Tx:
  - 1: Ant1
  - 2: Ant2
  - 3: both
  - -1: keep the original setting

  **Note**: If both hardware channels of a VN4610 device are used, the antenna setting cannot be changed during measurement time, use -1 in this case.

- **rxAntenna**: Antenna used for Rx:
  - 1: Ant1
  - 2: Ant2
  - 3: both
  - -1: keep the original setting

  **Note**: If both hardware channels of a VN4610 device are used, the antenna setting cannot be changed during measurement time, use -1 in this case.

## Return Values

0 or error code according to the following:

- **-1**: channel not open for access
- **-2**: invalid channel number
- **-3**: failure on reading current setting from hardware
- **-4**: setting configuration parameters on hardware failed
- **-5**: invalid radioChannel
- **-6**: invalid txAntenna selection
- **-7**: invalid txAntenna selection
- **-8**: invalid bandwidth
- **-9**: invalid dataRate
- **-10**: invalid txPower
- **-11**: invalid maxTxPower
- **11**: function call not allowed in this context like calling from measurement setup

## Example

```c
void configureChannel()
{
  word channelTable[7] = { 172,174,176,178,180,182,184};
  word dataRates[8] = {3,4,6,9,12,18,24,27};
  word currentChannelIndex = 0;
  word currentRateIndex = 0;
  dword errFlag = 0;
  word txPower = 0;

  // loop over all radio channels and data rates per timer callback
  // and configure 2 channels for Tx and Rx

  Write("C2xConfigureChannels radioCh:%d, txPow:%d, dataRate:%d, bandWidth:%d", channelTable[currentChannelIndex], txPower, dataRates[currentRateIndex], 10);
  errFlag = C2xConfigureChannel(1, channelTable[currentChannelIndex], txPower, 25, 1,
    dataRates[currentRateIndex], 10, 1, 1);
  if (errFlag != 0) Write("C2xConfigureChannel #1 failed with err=%d", errFlag);
  errFlag = C2xConfigureChannel(2, channelTable[currentChannelIndex], txPower, 25, 1,
    dataRates[currentRateIndex], 10, 2, 2);
  if (errFlag != 0) Write("C2xConfigureChannel #2 failed with err=%d", errFlag);
}
```
