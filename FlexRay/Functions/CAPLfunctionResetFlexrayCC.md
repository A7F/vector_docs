[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionResetFlexrayCC.md)

## resetFlexRayCC

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » resetFlexRayCC

**Valid for**: CANoe DE

### Note

The resetting of the FlexRay communication controller takes considerable time (approx. up to 100 ms). During this time, the complete execution including any remaining bus simulation is halted/suspended. Also bus events from other buses are not recognized. Therefore this function should only be used in one channel configurations. For an alternative functionality see Example 2.

### Function Syntax

```plaintext
void resetFlexRayCC (int channel);
```

### Description

This function initializes the FlexRay **C**ommunication **C**ontroller (CC) and begins a new start-up phase for the cluster or a new integrations phase in the cluster - depending on whether a start-up frame is to be sent or not.

### Parameters

- **channel**: FlexRay channel (cluster number).

### Return Values

—

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)