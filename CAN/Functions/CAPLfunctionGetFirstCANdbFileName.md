[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionGetFirstCANdbFileName.md)

**CAPL Functions** » **CAN** » **getFirstCANdbFilename**

# getFirstCANdbFilename

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword getFirstCANdbFilename( char buffer[], dword size);
```

## Description

Finds out the filename of the first assigned database.

## Parameters

- **buffer**: Buffer in which the database filename is written.
- **size**: Size of the buffer in Byte.

## Return Values

If successful unequal 0, otherwise 0.

## Example

```c
on start
{
    char buffer[256];
    dword pos;

    pos = GetFirstCANdbFilename( buffer, elcount( buffer));
    // Finds the filename of the first database.
    // If a database is found, "pos" contains the value 1.
    // If none is found "pos" contains 0.

    while ( 0 != pos)
    {
        write( "CANdb: %s", buffer);
        pos = GetNextCANdbFilename( pos, buffer, elcount( buffer));
        // Finds the filenames of other databases.
        // If any other databases are found
        // "pos" contains the value 2, 3, etc
        // If no further databases are found
        // "pos" contains 0 and the loop is exited
    }
}

Example to find the third database

on key '3'
{
    char buffer[256];
    dword pos;
    dword DbcNumber = 2; // Position number of the second database
    pos = GetNextCANdbFilename(DbcNumber, buffer, elcount(buffer));
    // Returns the filename of the third database.
    // Return value "pos" contains the value 3.
    // If no third database is found "pos" contains 0.

    write( "Database position number : %d Database file name : %s", pos, buffer);
}
```

[getFirstCANdbName](CAPLfunctionGetFirstCANdbName.md) • [getNextCANdbFilename](CAPLfunctionGetNextCANdbFileName.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)