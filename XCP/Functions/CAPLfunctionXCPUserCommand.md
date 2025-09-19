[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPUserCommand.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpUserCommand

# xcpUserCommand

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void xcpUserCommand(char ecuQualifier[], byte data[], long dataSize);
```

## Callback

```plaintext
void OnXcpUserCommand(char ecuQualifier[], byte data[], long dataSize);
```

## Description

Sends user-defined data to the XCP slave.

The callback returns the response on the user command.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).
- **data**: Byte array for user-defined data.
- **dataSize**: Size of the user-defined data.

## Return Values

—

## Example

In the following example the use of user commands for XCP with [xcpSet/GetCalPage](CAPLfunctionXCPSetCalPage.md) is shown.

```plaintext
variables
{
    long mMode;
    long mSegmentNr;
    byte mUsrCmdResponse = 0;
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
    ProcessUserCmd();
}

void ProcessUserCmd()
{
    byte adata[12] = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x0A, 0x0B, 0x0C };
    XCPUserCommand("XcpSim", adata, 12);
}

void OnXcpUserCommand(char ecu[], byte data[], long dataSize)
{
    mUsrCmdResponse = data[0];
    Write("OnXcpUserCommandResponse callback! ECU: %s. Data: %d. Data size: %d", ecu, data[0], dataSize);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
