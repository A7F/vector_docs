# getNextCANdbFilename

**Valid for:** CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword getNextCANdbFilename( dword pos, char buffer[], dword size);
```

## Description

Finds out the filenames of the other assigned databases with **pos**.

## Parameters

- **pos**: Position number of the database to be found.
- **buffer**: Buffer in which the database filename is written.
- **size**: Size of the buffer in Byte.

## Return Values

If successful unequal 0, otherwise 0.

## Example

```plaintext
on start
{
    char buffer[256];
    dword pos;

    pos = getFirstCANdbFilename( buffer, elcount( buffer));
    // Finds the filename of the first database.
    // If a database is found, "pos" contains the value 1.
    // If none is found "pos" contains 0.

    while ( 0 != pos)
    {
        write( "CANdb: %s", buffer);
        pos = getNextCANdbFilename( pos, buffer, elcount( buffer));
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
    pos = getNextCANdbFilename(DbcNumber, buffer, elcount(buffer));
    // Returns the filename of the third database.
    // Return value "pos" contains the value 3.
    // If no third database is found "pos" contains 0.

    write( "Database position number : %d Database file name : %s", pos, buffer);
}
```

[getFirstCANdbFilename](CAPLfunctionGetFirstCANdbFileName.md) • [getNextCANdbName](CAPLfunctionGetNextCANdbName.md)
