# frChannelUsesCANoeNetworkSimulator

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frChannelUsesCANoeNetworkSimulator

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long frChannelUsesCANoeNetworkSimulator(long channel);
```

## Description

Gets whether the given channel uses the built-in network simulator.

## Parameters

- **channel**: FlexRay channel (cluster number)

## Return Values

- **1**: True, the given channel uses the built-in network simulator.
- **0**: False, the given channel does not use the built-in network simulator.

## Example

```plaintext
on key 'q'
{
  //checks if channel 1 is simulated
  if(frChannelUsesCANoeNetworkSimulator(1))
  {
    //is simulated
  }
}
```
