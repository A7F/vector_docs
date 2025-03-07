[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetFmiFromDTC.md)

**CAPL Functions** » **J1939** » **Function Overview** » **J1939GetFmiFromDTC**

# J1939GetFmiFromDTC

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
dword J1939GetFmiFromDTC(dword dtc)
```

## Description

Function extracts FMI from DTC.

## Parameters

- **dtc**: DTC from which an FMI is to be extracted.

## Return Values

Extracted FMI.

## Example

```plaintext
on pg DM1
{
  int totalNumOfDTCs, curNumOfDTC;
  dword dtc;
  word fmi, oc;
  dword spn;

  // Iterate over all DTC blocks
  // and extract corresponding SPN, FMI and OC
  totalNumOfDTCs = (this.dlc - 2) / 4;
  for(curNumOfDTC = 0; curNumOfDTC < totalNumOfDTCs; curNumOfDTC++)
  {
    dtc = this.dword(2 + (curNumOfDTC * 4));
    spn = J1939GetSpnFromDTC(dtc);
    fmi = J1939GetFmiFromDTC(dtc);
    oc = J1939GetOcFromDTC(dtc);
    WriteEx(-3, 3, "DM1, DTC Nr. %d: SPN=%d, FMI=%d, OC=%d",
            curNumOfDTC+1, spn, fmi, oc);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)