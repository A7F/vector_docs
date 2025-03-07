[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionsExampleWrite.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » Example: writeClear, writeCreate, writeDestroy, writeEx, writeLineEx

# Example: writeClear, writeCreate, writeDestroy, writeEx, writeLineEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

```
variables
{
    long mNewPage; // Sink identifier
}

on start
{
    // Create a new page at the Write Window
    mNewPage = writeCreate("New Page");

    // Configure the page so that its content is logged
    writeConfigure(mNewPage, 20, 1, "c:\\temp\\writelog.TXT");

    // Clear content of CAPL page
    writeclear(1);

    // Show the description of the program
    writeLineEx(mNewPage, 2, "This program shows the keyboard sequence in a new created Page ");
    writeLineEx(mNewPage, 4, "\nKeyboard sequence: ");
}

on key *
{
    // Show the current key at the "New Page"
    char currentKey;
    currentKey = this;
    writeEx(mNewPage, 4, "%c ", currentKey);
}

on stopMeasurement
{
    // Destroy the new created Page
    writeDestroy(mNewPage);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)