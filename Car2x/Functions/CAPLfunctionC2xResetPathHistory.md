# C2xResetPathHistory

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long C2xResetPathHistory() // form 1`
- `long C2xResetPathHistory(long routeId) // form 2`

## Description

This function clears path history data for the current station which was previously stored by periodic [C2xAddGeoPos](CAPLfunctionC2xAddGeoPos.md) calls.

Call this function when:

- Station gets a new geographical position, more than 0.15° degree latitude or longitude away from the current position. Otherwise, the (relative) latitude or longitude calculated for the path history points cannot be applied to the message due to violation of the maximal range value.
- A new identity or use case is set for this station, so the old path history is no more needed.

By starting a scenario for this station the previous path history will be cleared automatically.

## Parameters

- **routeId**: Unique integer number which identify the path history position data storage from where the position data shall be deleted. This concrete routeId value must be previously used in periodic calls to the CAPL Function [C2xAddGeoPos](CAPLfunctionC2xAddGeoPos.md). Valid value range: routeId > 0.

  If **routeId** parameter is not used (form 1), all previously known path history data will be deleted.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

—
