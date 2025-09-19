[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SignalAccess/CAPLfunctionGetSignalDescriptionForValue.md)

**CAPL Functions** » [Signal Access](CAPLfunctionsSignalAccessOverview.md) » getSignalDescriptionForValue

# getSignalDescriptionForValue

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long getSignalDescriptionForValue(Signal signal, int64 rawValue, char buffer[], long bufferSize); // form 1`
- `long getSignalDescriptionForValue(char signalName[], int64 rawValue, char buffer[], long bufferSize); // form 2`
- `long getSignalDescriptionForValue(serviceSignalNumber signal, int64 rawValue, char buffer[], long bufferSize); // form 3`

## Description

Retrieves the description for the value of a database signal. In this way, you can access the value table of the signal.

## Parameters

- **signal**: The signal (form 1).
- **rawValue**: The value for which the description shall be retrieved. This must be the raw value, not the physical value.
- **buffer**: String buffer which receives the value description.
- **bufferSize**: Size of the buffer.
- **signalName**: The name of the signal (form 2).

  **Note Signal Ambiguity**: You have to use further objects to identify the signal uniquely. They are: channel, database name (alias), node name and message name. The exact qualification syntax is: `[Channel::][Database name (alias)::][Node::][Message::]Signal`. The order and completeness of the objects from right to left is important (see example).

## Return Values

- **0**: No error, function successful.
- **-1**: The signal is not valid.
- **-2**: There is no value table for the signal or the value table doesn't contain the value.
- **-3**: The provided buffer is too small.
- **-4**: The description contains special characters which can't be represented in the current CAPL string encoding.
- **-5**: The signal was not found (form 2 only).

## Example

```c
char buffer[100]; 
long ret;
ret = getSignalDescriptionForValue(PowerTrain::Engine::GearBoxInfo::Gear, 1, buffer, elcount(buffer));
if (ret == 0) 
    write("Description for value 1 is '%s'", buffer);
else 
    write("Error getting description for value 1: %d", ret);
```

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
