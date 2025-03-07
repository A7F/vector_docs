[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionChipState.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » ChipState

# ChipState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long ChipState ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.ChipState
```

## Description

Returns the current chip state of the CAN **x** controller.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Chip state of the CAN **x** controller. See the following list for a description of the return values.

- **0**: Value not available
- **1**: Simulated
- **2**: Not used
- **3**: Error Active
- **4**: Warning Level
- **5**: Error Passive
- **6**: Bus Off

A description of the chip states can also be found here: [Bus Statistics Window](../../../CANoeCANalyzer/Windows/BusStatistic/BusStatisticWindowCAN.md) of option CAN.

## Example

```
write ("Chip state of CAN1 = %d", CAN1.ChipState);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)