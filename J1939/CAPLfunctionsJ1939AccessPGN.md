[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/CAPLfunctionsJ1939AccessPGN.md)

# Access PGNs of Database Messages

[CAPL Functions](../CAPLfunctions.md) » [J1939](CAPLfunctionsJ1939StartPage.md) » Access PGNs of Database Messages

**Valid for**:  CANoe DE • CANoe4SW DE

If you need the PGN of a database message, you can get it with the **PGN** selector.

**Example**

```plaintext
on pg *
{
  if (this.PGN == EEC1.PGN)
  {
    write( "Received EEC1" );
  }
}
```

•  Technical References are only available in English

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
