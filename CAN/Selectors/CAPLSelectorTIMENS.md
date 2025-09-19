[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorTIMENS.md)

## Example Selector TIME_NS (time stamp of message in nanoseconds)

- **Type**: int64 (signed 64 bit integer) – only readable.

```plaintext
On message CAN1.100 {
  Write("CAN – Frame with time %I64d received", this.time_ns);
}
```

- Technical References are only available in English
- Build Time: 2024-10-8T21:20:34

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
