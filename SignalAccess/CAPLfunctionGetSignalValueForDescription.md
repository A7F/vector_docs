[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SignalAccess/CAPLfunctionGetSignalValueForDescription.md)

[CAPL Functions](../CAPLfunctions.md) » [Signal Access](CAPLfunctionsSignalAccessOverview.md) » getSignalValueForDescription

# getSignalValueForDescription

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long getSignalValueForDescription(Signal signal, char description[], int64& rawValue); // form 1`
- `long getSignalValueForDescription(char signalName[], char description[], int64& rawValue); // form 2`
- `long getSignalValueForDescription(serviceSignalNumber signal, char description[], int64& rawValue); // form 3`

## Description

Retrieves the value for a value description of a database signal. In this way, you can access the value table of the signal.

## Parameters

- **signal**: The signal (form 1).
- **description**: The value description for which the value shall be retrieved.
- **rawValue**: The value for the description. This is the raw value, not the physical value.
- **signalName**: The name of the signal (form 2).

  **Note Signal Ambiguity**: You have to use further objects to identify the signal uniquely. They are: channel, database name (alias), node name and message name. The exact qualification syntax is:

  `[Channel::][Database name (alias)::][Node::][Message::]Signal`

  The order and completeness of the objects from right to left is important (see example).

## Return Values

- **0**: No error, function successful.
- **-1**: The signal is not valid.
- **-2**: There is no value table for the signal or the value table doesn't contain the description.
- **-4**: The description contains special characters which can't be represented on the current computer.
- **-5**: The signal was not found (form 2 only).

## Example

```plaintext
int64 val; long ret;
ret = getSignalValueForDescription(PowerTrain::Engine::GearBoxInfo::Gear, "Gear_2", val);
if (ret == 0) write("Value for description 'Gear_2' is %I64d", val);
else write("Error getting value for description 'Gear_2': %d", ret);
```
