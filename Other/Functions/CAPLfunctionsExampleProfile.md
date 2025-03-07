[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionsExampleProfile.md)

## Example: writeProfileInt, writeProfileFloat, writeProfileString, getProfileInt, getProfileFloat, getProfileString, getProfileArray

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » Example: writeProfileInt, writeProfileFloat, writeProfileString, getProfileInt, getProfileFloat, getProfileString, getProfileArray

**Valid for:** CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

```plaintext
on key 'i'
{
    int defaultPara1;
    int returnParaInt;
    int returnArray;
    int counter;

    double defaultPara2;
    double returnParaFloat; 

    char buffer [1280];
    char buffarray[640];

    defaultPara1 = -1; 
    defaultPara2 = -1;

    // Write different values into the section "Parameter" of the INI file "Test.Ini"

    writeProfileString ("Parameter","String","TestString","Test.Ini");
    writeProfileFloat ("Parameter","Float", 1.7845,"Test.Ini");
    writeProfileInt ("Parameter", "Integer", 8, "Test.Ini"); 

    // Read different values from the Section "Parameter" of the INI file "Test.Ini"
    // And display the values in the Write Window

    returnParaInt = getProfileInt("Parameter","Integer",defaultPara1,"Test.Ini");
    returnParaFloat = getProfileFloat("Parameter","Float",defaultPara2,"Test.Ini"); 
    getProfileString("Parameter","String","Default String", buffer, elcount(buffer), "Test.Ini");
    returnArray = getProfileArray("Parameter","Array", buffarray, elcount(buffarray), "Test.Ini");

    write("Integer: %d", returnParaInt);
    write("Float: %f", returnParaFloat);
    write("String: %s", buffer);

    if (returnArray == 0) 
    {
        write("Non array content!");
    }
    else
    {
        for (counter = 0; counter <= returnArray - 1; counter++)
        { 
            write("Array: %d", buffarray[counter]);
        }
    }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)