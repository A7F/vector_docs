# AfdxGetDBMessageName

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetDBMessageName.md)

**CAPL Functions** » **AFDX** » AfdxGetDBMessageName

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetDBMessageName( long msgID, long bufSize, char buffer[] );
```

## Description

Retrieves the message name from database from a given message ID if it is defined there.

## Parameters

- **msgID**: Unique message ID as defined in the DBC.
- **bufSize**: Size of the provided buffer to put the name into.
- **buffer**: Buffer which should hold the found name.

## Return Values

- **0**: Success
- **other value**: See [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)