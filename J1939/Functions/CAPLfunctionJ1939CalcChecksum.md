[J1939CalcChecksum](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939CalcChecksum.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939CalcChecksum

# J1939CalcChecksum

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This function has been completely revised with CANoe DE product version 15. The former variant J1939CalcChecksum (Obsolete) is deprecated.

## Function Syntax

```
J1939CalcChecksum(pg * msg, char[] calculationMethod, dword & checksum)
```

## Description

Provides the checksum calculation for all PGNs as described in the J1939 Digital Annex. Possible calculation algorithms and message counter alignment is described in [J1939 Functional Safety – Messages With Integrated Checksum and Counter](../../../CANoeCANalyzer/J1939/j1939basics/j1939CrcAndCounter.md).

## Parameters

- **msg**: The parameter group to calculate the checksum for.
- **calculationMethod**: Two letters in the form [A-E][a-f] (e.g. **Bc**) that define the calculation rule and position of the checksum and message counter.
- **checksum**: Out parameter where the checksum is stored.

## Return Values

- **0**: Checksum is successfully filled.
- **-1**: Error: calculation method is invalid.

## Example

```c
on pg *
{
  long err;
  dword checksum;
  switch(this.pgn)
  {
    case 0xF123: //DCDC4OS
      err = J1939CalcChecksum(this, "Aa", checksum);
      if(checksum != this.byte(7) || err != 0)
      {
        write("Checksum error");
      }
      break;
    default:
      break;
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
