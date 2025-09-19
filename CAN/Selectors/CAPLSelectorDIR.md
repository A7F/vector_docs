[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorDIR.md)

## Example Selector DIR (direction of transmission)

```plaintext
on message 0x100 {
  if (this.DIR == Rx) {
    write("message 0x100 received");
  }
  if (this.DIR == Tx) {
    write("message 0x100 sent");
  }
}
```

### Note

Please note the [semantics of Rx](../../../CAPLBrowser/General/CAPLBrowserRXSemantics.md) for CAPL nodes in the Simulation Setup.

---

- Technical References are only available in English
- © Vector Informatik GmbH
- CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
- [Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
- [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
