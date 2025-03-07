[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorECC.md)

## Example Selector ECC

```plaintext
on errorFrame
{
  switch (this.ecc & 0x20)
  {
    case (0x20):
      write ("%d Ch %d RxErr",  this.time, this.can);
      return;
    case (0):
      write  ("%d Ch %d TxErr", this.time, this.can);
      return;
  };
}
```

- Technical References are only available in English
- © Vector Informatik GmbH
- CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
- [Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
- [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)