[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILControlStart.md)

## J1939ILControlStart

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILControlStart

### Tool Availability
[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

- `long J1939ILControlStart();` // form 1
- `long J1939ILControlStart(dbNode node);` // form 2
- `long J1939ILControlStart(byte address);` // form 3
- `long J1939ILControlStart(dbNode node, byte address);` // form 4

### Description

The node starts [Address Claiming](../../../../CANoeCANalyzer/J1939/j1939basics/j1939NMT.md) (if [NMT is activated](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILActivateFeatures.md)). If the Address Claiming was successful, cyclic messages are sent.

The source address can be specified optionally. If it is not specified the node attribute [NmStationAddress](../../../../CANoeCANalyzer/J1939/j1939basics/j1939CanDbAttributes.md) must be defined.

### Parameters

- **address**: source address of the node (optional)
- **node**: Simulation node to apply the function

### Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

```plaintext
on start
{
    J1939ILControlStart();
}
```
