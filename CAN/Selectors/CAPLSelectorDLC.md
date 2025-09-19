[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorDLC.md)

## Example Selector DLC (data length code)

```plaintext
on message OneByteMessage {
  if (this.DLC != 1) {
    write("error: OneByteMessage has DLC != 1");
    stop();
  }
}
```

- Technical References are only available in English
- Build Time: 2024-10-8T21:20:34

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
