[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorRTR.md)

## Example Selector RTR (remote transmission request)

```plaintext
// send remote frame
message 0x100 rmsg;
rmsg.RTR = 1;
output(rmsg);
```

- Technical References are only available in English
- © Vector Informatik GmbH
- CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
- [Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
- [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)