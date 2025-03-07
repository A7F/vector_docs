[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPSetCalPage.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpSetCalPage

# xcpSetCalPage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void xcpSetCalPage(char ecuQualifier[], byte mode, byte segmentNr, byte pageNr);
```

## Callback

```plaintext
void OnXcpSetCalPage(char ecuQualifier[]);
```

## Description

If the XCP slave device supports calibration data page switching, this command sets the current page and access mode. The callback returns that the ECU switched the calibration data page.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).
  
- **mode**: Bit field defined in the XCP specification.
  - **Bit 7**: Use for all segments, i.e. parameter `segmentNr` is ignored.
  - **Bit 1**: The slave device XCP driver will access the given page.
  - **Bit 0**: The given page will be used by the slave device application.

- **segmentNr**: Logical data segment number. Ignored if bit 7 of the mode parameter is set to 1.

- **pageNr**: Logical data page number. Usually 0 identifies the page in RAM and 1 the page in FLASH memory. Option AMD/XCP can only work on parameters stored in RAM.

## Return Values

—

## Example

```plaintext
variables
{
   long mMode;
   long mSegmentNr;
}

void OnXcpConnect(char ecuName[])
{
   mMode = 255;
   mSegmentNr = 0;
   write("Connect callback! ECU: %s", ecuName);
   XcpGetCalPage(ecuName, mMode, mSegmentNr);
}

void OnXcpGetCalPage(char ecu[], long reserved1, long reserved2, long pageNumber)
{
   Write("OnXcpGetCalPage callback! ECU: %s. Current PageNumber: %d", ecu, pageNumber);
   if (pageNumber == 0)
   {
      pageNumber = 1;
   }
   else
   {
      pageNumber = 0;
   }
   XcpSetCalPage(ecu, mMode, mSegmentNr, pageNumber);
}

void OnXcpSetCalPage(char ecu[])
{
   Write("OnXcpSetCalPage callback! ECU: %s", ecu);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)