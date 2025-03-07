[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILStopChargingSimulation.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_StopChargingSimulation

# GBT27930IL_StopChargingSimulation

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_StopChargingSimulation(); // form 1`
- `long GBT27930IL_StopChargingSimulation(dbNode node); // form 2`

## Description

Node stops the charging simulation.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: on success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—