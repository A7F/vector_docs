# GetCanBittimingConfiguration, SetCanBittimingConfiguration

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

- `int GetCanBittimingConfiguration(dword channel, BitTiming timing);`
- `int GetCanBittimingConfiguration(dword channel, BitTiming[] timings, dword countOfBittimings);`
- `int SetCanBittimingConfiguration(dword channel, BitTiming timing);`
- `int SetCanBittimingConfiguration(dword channel, BitTiming[] timings, dword countOfBittimings);`

## Description

The CAN, CAN FD or CAN-XL controller parameters can be set or read. An automatic reset of the controller is performed.

## Parameters

- **Channel**: The CAN channel.
- **BitTiming**: The bit timing for the defined phase.
- **BitTimings**: The bit timings for more than one defined phase.
- **countofBittimings**: Number of bit timings contained in the array.

## Selectors

- **struct BitTiming**
  - **BitTiming.BitTimingPhase**: The bit timing phase. Type: BitTimingPhase, Access: r/w
  - **BitTiming.Bitrate**: The bitrate for the defined phase. Type: double, Access: r/w
  - **BitTiming.TSEG1**: The time quanta count of the time segment 1. Type: dword, Access: r/w
  - **BitTiming.TSEG2**: The time quanta count of the time segment 2. Type: dword, Access: r/w
  - **BitTiming.SJW**: The synchronization jump width for the phase error correction. Type: dword, Access: r/w

- **enum BitTimingPhase**
  - **eCANInvalidPhase**: Invalid value for a phase within the bit timing structure. Type: int, Access: r
  - **eCANNominalPhase**: BitTiming values represent the nominal phase of CAN, CAN-FD or CAN-XL frame. Type: int, Access: r
  - **eCANFDPhase**: BitTiming values represent the data phase of a fd frame. Type: int, Access: r
  - **eCANXLPhase**: BitTiming values represent the data phase of a xl frame. Type: int, Access: r

## Return Values

- **0**: Successful
- **-1**: Invalid bit timing phase
- **-2**: Invalid parameter
- **-3**: No bit timings available for defined phase
- **-4**: No bit timings available for defined channel
- **-255**: Unknown error

## Example

**Example 1**

```plaintext
dword     result;
BitTiming timingsToSet; //variable definition
BitTiming timingsAreGet; //variable definition

//-------------------------------------
//Define values for the nominal phase
//-------------------------------------
timingsToSet.Bitrate = 500000.0;
timingsToSet.Tseg1 = 55;
timingsToSet.Tseg2 = 24;
timingsToSet.Sjw = 24;
timingsToSet.BitTimingPhase = eCANNominalPhase;
timingsAreGet.BitTimingPhase = eCANNominalPhase;
//-------------------------------------

//-------------------------------------
//Configure the new values
//-------------------------------------
result = SetCanBittimingConfiguration(1, timingsToSet);
if(result == 0)
{
  result = GetCanBittimingConfiguration(1, timingsAreGet);
  if(result == 0)
  {
    write("Settings: Phase = %d bitrate = %f, tseg1 = %d, tseg2= %d, sjw = %d", timingsAreGet.BitTimingPhase, timingsAreGet.Bitrate, timingsAreGet.tseg1,
    timingsAreGet.tseg2, timingsAreGet.sjw);
  }
}
```

**Example 2**

```plaintext
dword     result;
BitTiming timingsToSet[3]; //variable definition
BitTiming timingsAreGet[3]; //variable definition

//-------------------------------------
//Define values for the nominal phase
//-------------------------------------
timingsToSet[0].Bitrate = 500000.0;
timingsToSet[0].Tseg1 = 55;
timingsToSet[0].Tseg2 = 24;
timingsToSet[0].Sjw = 24;
timingsToSet[0].BitTimingPhase = eCANNominalPhase;
timingsAreGet[0].BitTimingPhase = eCANNominalPhase;
timingsToSet[1].Bitrate = 1000000.0;
timingsToSet[1].Tseg1 = 27;
timingsToSet[1].Tseg2 = 12;
timingsToSet[1].Sjw = 12;
timingsToSet[1].BitTimingPhase = eCANFDPhase;
timingsAreGet[1].BitTimingPhase = eCANFDPhase;
timingsToSet[2].Bitrate = 4000000.0;
timingsToSet[2].Tseg1 = 6;
timingsToSet[2].Tseg2 = 3;
timingsToSet[2].Sjw = 2;
timingsToSet[2].BitTimingPhase = eCANXLPhase;
timingsAreGet[2].BitTimingPhase = eCANXLPhase;
//-------------------------------------

//-------------------------------------
//Configure the new values
//-------------------------------------
result = SetCanBittimingConfiguration(1, timingsToSet, 3);
if(result == 0)
{
  result = GetCanBittimingConfiguration(1, timingsAreGet, 3);
  if(result == 0)
  {
    int index;
    for(index = 0; index < 3; ++index)
    {
      write("Settings: Phase = %d bitrate = %f, tseg1 = %d, tseg2=%d, sjw = %d", timingsAreGet[index].BitTimingPhase, timingsAreGet[index].Bitrate, timingsAreGet[index].tseg1, timingsAreGet[index].tseg2, timingsAreGet[index].sjw);
    }
  }
}
```
