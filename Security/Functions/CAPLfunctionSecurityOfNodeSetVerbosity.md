[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityOfNodeSetVerbosity.md)

# SecurityOfNodeSetVerbosity

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityOfNodeSetVerbosity

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SecurityOfNodeSetVerbosity(char nodeName[], char networkName[], dword level)
```

## Description

Configures the notification level for the specified node on the specified network from low (0) to high (5).

## Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **dword level**: Desired notification level. Range: 0-5
  - 0: Only critical errors are printed.
  - 1: All errors are printed
  - 2: Additionally warnings are printed
  - 3: Information messages are printed too.
  - 4-5: Debug messages are active.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
