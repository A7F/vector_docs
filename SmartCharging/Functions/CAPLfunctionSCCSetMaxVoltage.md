[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetMaxVoltage.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Simulation Data** » **Shared Functions** » **SCC_SetMaxVoltage**

# SCC_SetMaxVoltage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function needs a running SCC session in order to work. Make sure to call it only after the Session Setup Request message is sent.

## Function Syntax

`long SCC_SetMaxVoltage ( float MaxVoltage )`

## Description

Sets the limit for voltage. These limits are used in various messages for both AC and DC mode (the actual element name depends on the charging mode and the protocol version). Defaults can be set using the respective configuration file.

## Parameters

- **MaxVoltage**: Limit value to be set.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
