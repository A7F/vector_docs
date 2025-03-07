[J1939GetDTC](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetDTC.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939GetDTC

# J1939GetDTC

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939GetDTC(pg pgWithDTC, dword spn, byte fmi, byte oc, dword &dtcValue)
```

## Description

Function looks through a J1939 diagnostic message and returns the first DTC block that matches the search criteria, i.e. that contains defined SPN/FMI/OC values.

## Parameters

- **pgWithDTC**: Message to be checked for a specific DTC block. Must be a J1939 Parameter Group.
- **spn**: Suspect Parameter Number of the specified DTC. `0xFFFFFFFF` if `spn` is to be ignored.
- **fmi**: Failure Mode Identifier of the specified DTC. `0xFFFF` if `fmi` is to be ignored.
- **oc**: Occurrence Counter of the specified DTC. `0xFFFF` if `oc` is to be ignored.
- **dtcValue**: The value of the found DTC block.

## Return Values

- **≥ 0**: Byte number of the start position of the found DTC block (zero-based).
- **-1**: Message does not contain a DTC block matching the search criteria.

## Example

```plaintext
on pg DM1
{
  int posOfDTC;
  dword foundDTC;
  word fmi, oc;
  dword spn;

  // Look for the DTC with SPN=67890
  posOfDTC = J1939GetDTC(this, 67890, 0xFFFF, 0xFFFF, foundDTC);
  if(posOfDTC > 0)
  {
    fmi = J1939GetFmiFromDTC(foundDTC);
    oc = J1939GetOcFromDTC(foundDTC);
    WriteEx(-3, 3, "DM1 with DTC (SPN=67890) observed: FMI=%d, OC=%d", fmi, oc);
  }

  // Look for the DTC with SPN=123 and OC=5
  posOfDTC = J1939GetDTC(this, 123, 0xFFFF, 5, foundDTC);
  if(posOfDTC > 0)
  {
    fmi = J1939GetFmiFromDTC(foundDTC);
    WriteEx(-3, 3, "DM1 with DTC (SPN=123, OC=5) observed: FMI=%d", fmi);
  }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)