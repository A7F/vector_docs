# frEnableNodeTx

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
The function is supported by VN interfaces only!

## Function Syntax

```plaintext
long FrEnableNodeTx(long channel, char[] node, long enable);
```

## Description

Enable/disable all TX frames/PDUs of the specified node.  
With enabling the default data of the frames/PDUs are transmitted.

## Parameters

- **channel**: FlexRay channel.
- **node**: Name of the node.
- **enable**: 
  - 1: Enables the transmission
  - 0: Disables the transmission

## Return Values

- **1**: Successful
- **0**: Not successful

## Example

—
