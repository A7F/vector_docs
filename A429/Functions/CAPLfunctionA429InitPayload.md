# a429InitPayload

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long a429InitPayload (a429Word myA429word)
```

## Description

Initialize the payload of an existing a429word using the current values of corresponding signals from SignalServer.

This can be used to initialize a message from scratch to the StartValues of the StartValue-table in the Init-section, or to assign the current signal values to the payload during any time of measurement.

## Parameters

- **myA429Word**: message which should be initialized with current signal values

## Return Values

- **-1**: message not valid or corresponding signal(s) not found
- **0**: no error
- **> 0**: Values are a sum of individual signal setting errors as per:
  - **1**: access is wrong
  - **2**: wrong signal value type (can_db_sigval_t)
  - **3**: signal too long in the context of the chosen conversion method
  - **4**: signal value is out of range
  - **5**: error in mode dependent signal (value of mode signal doesn't match with signal mode)
  - **6**: passed data field too small
  - **7**: physical value rounded during Raw2Phys-conversion
  - **8**: physical value exceeds the maximum number of bits passed to the conversion method

## Example

```c
variables
{
  a429Word *msg = { msgChannel = 1};
}
on key '1'
{
  a429InitPayload(msg);
}
```

XREF • XREF
