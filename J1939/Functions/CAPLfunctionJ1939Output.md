[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939Output.md)

CAPL Functions » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » output (J1939)

# output (J1939)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`output(pg pg_variable);`

## Description

Outputs a parameter group onto the CAN bus.

## Parameters

- **pg_variable**: Variable of the type "pg".

## Return Values

—

## Example

```plaintext
on key F1
{
  pg 0xFEE1 pg_1; // define parameter group
  pg_1.sa = 1;
  pg_1.da = 2;
  pg_1.prio = 7;
  output (pg_1); // output parameter group
}
```

```plaintext
void SendVehicleIdentification(byte idString[])
{
  dword i;
  pg VI_EMS vi = {dlc = 1785}; // define parameter group with biggest possible value
  if(elcount(idString) > 1785)
    return;
  for (i=0; i<elcount(idString); ++i)
  {
    vi.byte(i) = idString.byte(i);
  }
  vi.dlc = elcount(idString); // set data length to length of the string
  output(vi);
}

Example 3 (J1939-22):
On key 'a'
{
  // Send a PG as a single C-PG within Multi-PG
  pg 0x0 pgTSC1 = {dlc = 8};
  pgTSC1.sa = 1;
  pgTSC1.da = 2;
  pgTSC1.fdf = 1;
  pgTSC1.tm = 1;
  output(pgTSC1);
}
```

[Define Parameter Groups (J1939)](../CAPLfunctionsJ1939DefinePG.md) • [Parameter Group Selectors (J1939)](../CAPLfunctionJ1939GroupSelectors.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)