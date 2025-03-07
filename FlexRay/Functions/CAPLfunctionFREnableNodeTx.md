[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFREnableNodeTx.md)

**CAPL Functions** » **FlexRay** » **frEnableNodeTx**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)