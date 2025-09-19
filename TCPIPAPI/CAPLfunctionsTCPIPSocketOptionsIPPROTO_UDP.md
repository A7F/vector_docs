# Socket Options: IPPROTO_UDP

[CAPL Functions](../CAPLfunctions.md) » [TCP/IP API](CAPLfunctionsTCPIPOverview.md) » [Socket Options](CAPLfunctionsTCPIPSocketOptions.md) » IPPROTO_UDP

**Valid for**: CANoe DE • CANoe4SW DE

The following socket options can be set at the IPPROTO_UDP socket option level in CAPL. They influence the behavior of the UDP protocol per socket. For all BOOL typed options a non-zero value will be interpreted as TRUE.

**Stacks**

- **C**: Supported by CANoe internal network stack
- **W**: Supported by Windows network stack

## Socket Options Table

- **Socket Option**: UDP_NOCHECKSUM
- **Set/Get**: set/get
- **Description**: The UDP checksum will be set to zero if this option is set TRUE.
- **Type**: DWORD (boolean)
- **Stack**: W

[See Also](javascript:void(0);)

---

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
