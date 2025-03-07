[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsShdEnableCAPLfunctionMOSTAsShdDisable.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsShdEnable, mostAsShdDisable

# mostAsShdEnable, mostAsShdDisable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostAsShdEnable(long fblockId, long instId);`
- `long mostAsShdDisable(long fblockId, long instId);`

## Description

`mostAsShdEnable()` adds an entry to the list of searched function blocks. If certain network events occur, CANoe automatically sends a request to the NetworkMaster to determine the logical device address of the function block.

Registration with `mostAsShdEnable(fblockId, 0xFF)` causes the service to request the device addresses of all function blocks with the appropriate FBlockId at the NetworkMaster.

`mostAsShdDisable()` removes an entry from the list of searched function blocks.

## Parameters

- **fblockId**: Function block ID
- **instId**: Instance ID

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)