[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthResetStatistics.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethResetStatistics

# ethResetStatistics

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void ethResetStatistics( long channel );
```

## Description

Resets Ethernet channel statistics. The Ethernet channel statistics are provided by the [Eth](../Objects/CAPLfunctionEth.md)`<channel>` object.

## Parameters

- **channel**: Ethernet channel number.

## Return Values

- **Value range**: 1..32

## Example

```c
on key 'i'
{
  ethResetStatistics( 1 ); // Reset statistics of Eth 1
}
```

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
