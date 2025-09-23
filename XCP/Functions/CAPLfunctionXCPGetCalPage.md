[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPGetCalPage.md)

**CAPL Functions** » **XCP** » **xcpGetCalPage**

# xcpGetCalPage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void xcpGetCalPage(char ecuQualifier[], byte mode, byte segmentNr);
```

## Callback

```plaintext
void OnXcpGetCalPage(char ecuQualifier[], byte reserved0, byte reserved1, byte pageNr);
```

## Description

If the XCP slave device supports calibration data page switching, this command gets the currently active page and access mode. The callback returns the currently active calibration data page of the ECU.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).
- **mode**: Access mode of the currently active page. The values may be 0x01 (ECU access) or 0x02 (XCP access). All other values are invalid.
- **segmentNr**: Logical data segment number.
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
