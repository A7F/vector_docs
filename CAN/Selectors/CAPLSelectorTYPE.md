[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorTYPE.md)

### Example Selector TYPE

```plaintext
message 0x100 resp_msg = {dlc = 2, word(0) = 0x1234};

on message 0x100 {
  if (this.TYPE == RXREMOTE) {
    // remote frame 0x100 received
    output(resp_msg);
  }
}
```

- Technical References are only available in English
- © Vector Informatik GmbH
- CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
- [Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
- [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)