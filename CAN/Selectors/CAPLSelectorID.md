[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorID.md)

## Example Selector ID (message identifier)

```plaintext
on message * {
  if (this.ID == 0x600) {
    write("message 0x600 received; triggering logging...");
    trigger();
  }
}
```

- Technical References are only available in English
- © Vector Informatik GmbH
- CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
- [Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
- [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)