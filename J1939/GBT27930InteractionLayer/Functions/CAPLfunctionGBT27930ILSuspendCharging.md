[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILSuspendCharging.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SuspendCharging**

# GBT27930IL_SuspendCharging

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_SuspendCharging(); // form 1`
- `long GBT27930IL_SuspendCharging(dbNode node); // form 2`

## Description

Node suspends the charging. This function is only effective if the simulated node is in the **Charging** state. The **Charger** node stops sending the CCS message and starts sending the CST message. The BMS node stops sending the BCL, BCS and MSM messages and starts sending the BST message.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: on success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
