[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetProFileString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getProfileString

# getProfileString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
A filename must be passed to this function. The absolute filename is determined by means of a [search procedure](../CAPLfunctionsFileSearchProcedure.md).

## Function Syntax

```plaintext
long getProfileString(char section[], char entry[], char def[], char buff[], long buffsize, char filename[]); // form 1
long getProfileString(char section[], char entry[], char def[], char buff[], long buffsize, char filename[], dword utf16); // form 2
```

## Description

Searches the file **filename** under **section** section for the variable **entry**. Its contents (value) are written to the buffer **buff**. Its length must be passed correctly in **buffsize**.

If the file or entry is not found, the default value **def** is copied to buffer.

If the read string length is longer than the buffer, the string will be cut to the buffer length.

## Parameters

- **section**: Section of the file as a string.
- **entry**: Variable name as a string.
- **def**: Default value in case of error as a string.
- **buff**: Buffer for the read-in character as a string.
- **buffersize**: Size of **buff** in bytes.
- **filename**: Filename as a string.
- **utf16**: If this flag is set the file will be interpreted as UTF-16LE encoded, if the corresponding BOM is also present. The string written to **buff** will be converted to the CAPL encoding.

## Return Values

- Length of the read string.
- Length of the default string: Fault **Key not found**
- **-1**: Fault **File not found**

## Example

See [getProfileString](CAPLfunctionsExampleProfile.md)
