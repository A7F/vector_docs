# J1939MakeDTC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939MakeDTC(dword spn, byte fmi, byte oc, dword &dtcValue)
```

## Description

Function generates a DTC from the defined SPN, FMI, and OC.

## Parameters

- **spn**: Suspect Parameter Number of the specified DTC. Valid value range: 0x0 – 0x7FFFF.
- **fmi**: Failure Mode Identifier of the specified DTC. Valid value range: 0x0 – 0x1F.
- **oc**: Occurrence Counter of the specified DTC. Valid value range: 0x0 – 0x7F.
- **dtcValue**: The value of the generated DTC block.

## Return Values

- **0**: `dtcValue` is successfully generated.
- **-1**: One of the input parameters does not fit into the valid value range.

## Example

```c
// Fill DM1 with two DTCs and send it

pg DM1 myDM1 = {DLC=10, SA=1};
dword dtc;

// Activate Protect Lamp (permanent lighting)
myDM1.word(0) = 0xFF01;

// Make first DTC (SPN=67890, FMI=16, OC=101)
J1939MakeDTC(67890, 16, 101, dtc);
myDM1.dword(2) = dtc;

// Make second DTC (SPN=123, FMI=11, OC=5)
J1939MakeDTC(123, 11, 5, dtc);
myDM1.dword(6) = dtc;

// Send DM1 message
output(myDM1);
```
