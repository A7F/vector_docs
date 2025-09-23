[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILStartChargingSimulation.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_StartChargingSimulation**

# GBT27930IL_StartChargingSimulation

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_StartChargingSimulation(); // form 1`
- `long GBT27930IL_StartChargingSimulation(dbNode node); // form 2`

## Description

Node starts the charging simulation. In the role that was previously defined with the call [GBT27930IL_InitAsCharger](CAPLfunctionGBT27930ILInitAsCharger.md) or [GBT27930IL_InitAsBMS](CAPLfunctionGBT27930ILInitAsBMS.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: on success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
