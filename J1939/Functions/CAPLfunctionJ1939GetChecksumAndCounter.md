# J1939GetChecksumAndCounter

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetChecksumAndCounter.md)

**CAPL Functions** » **J1939** » **Function Overview** » J1939GetChecksumAndCounter

## Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939GetChecksumAndCounter(pg * msg, char[] calculationMethod, dword & checksum, dword & counter)
```

## Description

This function returns the checksum and the message counter of the given parameter group. The available calculation methods are described in [J1939 Functional Safety – Messages With Integrated Checksum and Counter](../../../CANoeCANalyzer/J1939/j1939basics/j1939CrcAndCounter.md) and are used to determine the alignment of the checksum and message counter in the given parameter group. After calling this function the parameters **checksum** and **counter** contain the values that were transmitted in the message, and the return value indicates if an error occurred.

## Parameters

- **msg**: The parameter group to get the checksum and counter from.
- **calculationMethod**: Two letters in the form [A-E][a-f] (e.g. **Bc**) that define the calculation rule and position of the checksum and message counter.
- **checksum**: The checksum retrieved from the given parameter group.
- **counter**: The message counter retrieved from the given parameter group.

## Return Values

- **0**: Checksum successfully filled.
- **-1**: Error: calculation method is invalid.

## Example

```plaintext
on pg *
{
  long err;
  dword checksum;
  dword counter;
  switch(this.pgn)
  {
    case 0xF123: //DCDC4OS
      err = J1939GetChecksumAndCounter(this, "Aa", checksum, counter);
      if(err != 0)
      {
        write("Invalid calculation method");
      }
      write("Checksum: %d", checksum);
      write("Message Counter: %d", counter);
      break;
    default:
      break;
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
