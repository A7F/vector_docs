[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSendVariableBitStream.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSendVariableBitStream

# linSendVariableBitStream

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long linSendVariableBitStream(byte dataBuffer[], int64 lengthInNS[], dword numberOfBits, dword roundUp);` // form 1
- `long linSendVariableBitStream(byte dataBuffer[], int64 lengthInNS[], dword numberOfBits, dword roundUp, dword timeoutPrevention)` // form 2
- `long linSendVariableBitStream(byte dataBuffer[], int64 lengthInNS[], dword numberOfBits, dword roundUp, dword timeoutPrevention, dword interruptingTx)` // form 3

## Description

Sends an arbitrary bitstream with bits of variable length on the LIN bus.

## Parameters

- **dataBuffer**: The bitstream to be sent. Maximum number of bits: 2^31-1.
- **lengthInNS**: The length of each bit in nanoseconds.
- **numberOfBits**: The number of bits in the bitStream-array. Note that while the dataBuffer-array will usually have a size of ceil(numberOfBits / 8), the size of lengthInNS will need to be at least numberOfBits.
- **roundUp**: If true, the lengths specified in lengthInNS will be rounded up to the next possible length that can be transmitted by the LIN hardware, otherwise the lengths will be rounded down.
- **timeoutPrevention**:
  - 0: deactivates the timeout prevention for the 7259-transceiver.
  - 1: activates the timeout prevention for the 7259-transceiver.
- **interruptingTx**: When activated (= 1) the transmission of the bitstream starts immediately without waiting for the bus to be free. Note that this mode may disturb a running transmission.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```c
// This function sends a disturbance of 1 second, followed by a pause of 1 second,
// followed by a disturbance of 7 seconds using the variable bitstream functionality
void SendDisturbances()
{
    byte data[1] = { 2 };
    int64 lengthInNS[3] = { 1000000000LL, 1000000000LL, 7000000000LL };
    linSendVariableBitStream(data, lengthInNS, 3, 1, 1);  byte data[25];
}
```

[linSendBitStream](CAPLfunctionLINSendBitStream.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
