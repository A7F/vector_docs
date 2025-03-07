[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionResetFlexrayCCEX.md)

**CAPL Functions** » **FlexRay** » **resetFlexRayCCEx**

# resetFlexRayCCEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The resetting of the FlexRay communication controller takes considerable time (approx. up to 100 ms). During this time the complete execution including any remaining bus simulation is halted/suspended. Also bus events from other buses are not recognized. Therefore this function should only be used in one channel configurations. For an alternative functionality see Example 2.

## Function Syntax

```plaintext
long resetFlexRayCCEx (int channel, int wuChMask, int wuCount, int wuTxIdle, int wuTxLow, char[] cfg);
```

## Description

This function initializes the FlexRay **C**ommunication **C**ontroller (CC) and generates the specified wake-up pattern before reintegration in the cluster or the start-up.

## Parameters

- **channel**: FlexRay channel (cluster number)
- **wuChMask**: Channel for the wake-up pattern.  
  Values:
  - 1: Channel A
  - 2: Channel B
- **wuCount**: Number of repetitions (2 – 63) of the wake-up symbol in a wake-up pattern.
- **wuTxIdle**: This number designates the number of idle bits in a wake-up symbol. According to protocol specification, this should result in 18 µs.
- **wuTxLow**: This number designates the number of low bits in a wake-up symbol. According to protocol specification, this should result in 6 µs.
- **cfg**: Character data array. This is currently not used and is of no importance.

## Return Values

—

## Example

**Example 1**  
The following program resets the FlexRay interface of the attached channel and sends a wake-up (if network is idle), when the `<W>` key is pressed.

```plaintext
on key 'w'
{
   int wuChMask = 3;   // send wake-up on both channels
   int wuCount  = 4;   // send symbol 2 times (range 2-63)
   int wuTxIdle = 180; // idle time of symbol in bit (range 0-255)
   int wuTxLow = 60;   // low time of symbol in bit (range 0-63)
   CHAR cfg[1];        // <cfg> -> not used yet
   resetFlexRayCCEx(%CHANNEL%,wuChMask,wuCount,wuTxIdle,wuTxLow,cfg);
   Write("FlexRay CC %d is reset and sending a wakeup.", %CHANNEL%);
}
```

**Example 2**  
In order to prevent the suspension during the call of `ResetFlexRayCCEx` the reset can be executed asynchronously by manipulating the **Protocol Operation Control** (POC) state machine of the FlexRay Communication Controller directly. See [Reset of the CC by its POC](../../../CANoeCANalyzer/FlexRay/CAPL_Functions/FlexRay_CAPL_Reset_FlexRay-CC_by_POC.md).

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)