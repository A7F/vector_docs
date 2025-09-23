# J1939GetNumOfDTCs

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939GetNumOfDTCs(pg pgWithDTCs, dword spn, byte fmi, byte oc)
```

## Description

Function looks through a J1939 diagnostic message and returns the number of DTC blocks that match the search criteria, i.e. that contains defined SPN/FMI/OC values.

## Parameters

- **pgWithDTC**: Message to be checked for a specific DTC block. Must be a J1939 Parameter Group.
- **spn**: Suspect Parameter Number of the specified DTC. `0xFFFFFFFF` if `spn` is to be ignored.
- **fmi**: Failure Mode Identifier of the specified DTC. `0xFFFF` if `fmi` is to be ignored.
- **oc**: Occurrence Counter of the specified DTC. `0xFFFF` if `oc` is to be ignored.

## Return Values

- **≥ 0**: Byte number of the start position of the found DTC block (zero-based).
- **-1**: Message does not contain a DTC block matching the search criteria.

## Example

```plaintext
on pg DM1
{
  int numOfDTCs;

  // Count the number of DTCs with FMI=11
  numOfDTCs = J1939GetNumOfDTCs(this, 0xFFFFFFFF, 11, 0xFFFF);
  if(numOfDTCs > 0)
    WriteEx(-3, 3, "DM1 with %d DTC(s) with FMI=11 observed", numOfDTCs);
}
```
