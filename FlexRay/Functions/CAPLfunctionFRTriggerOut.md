[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRTriggerOut.md)

# frSetTrigger

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetTrigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The function is supported by VN interfaces only!

## Function Syntax

`long frSetTrigger( long channel, long portNo );`

## Description

This function activates the Trigger output of the selected VN interface. The VN interfaces provide three different trigger ports. The ports can be set separately.

## Parameters

- **channel**: FlexRay channel (cluster number). The channel number identifies the VN interfaces in case several interfaces are active.
- **portNo**: 1-3: Number of corresponding trigger output. The PIN assignment is defined in the manual of the network interface.

## Return Values

- **0**: Error

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
