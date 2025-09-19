[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBGetCtrlLineStatus.md)

# GPIBGetCtrlLineStatus

[CAPL Functions](../../CAPLfunctions.md) » [GPIB](../CAPLfunctionsGPIBOverview.md) » GPIBGetCtrlLineStatus

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long GPIBGetCtrlLineStatus (long boardIdx);
```

## Description

Returns the status of the GPIB control lines.

## Parameters

- **boardIdx**: GPIB Board ID

## Return Values

- **Line Status Bytes**: The value consists of 2 bytes. The low-order byte (bits 0 through 7) contains a mask indicating the capability of the GPIB interface to sense the status of each GPIB control line. The high-order byte (bits 8 through 15) contains the GPIB control line state information. If a bit is set (1), the corresponding control line can be monitored by the interface or is asserted, respectively. The following is a pattern of each byte.

  - **7**: EOI
  - **6**: ATN
  - **5**: SRQ
  - **4**: REN
  - **3**: IFC
  - **2**: NRFd
  - **1**: NDAC
  - **0**: DAV

- **-1**: (all bits set in 4 bytes) is returned on error, if no GPIB driver is available.

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
