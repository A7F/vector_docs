[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetProFileArray.md)

**CAPL Functions** » **General** » **Function Overview** » **getProfileArray**

# getProfileArray

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**: A filename must be passed to this function. The absolute filename is determined by means of a [search procedure](../CAPLfunctionsFileSearchProcedure.md).

## Function Syntax

```plaintext
long getProfileArray(char section[], char entry[],char buff[], long buffsize, char filename[]); // form 1
long getProfileArray(char section[], char entry[],char buff[], long buffsize, char filename[], dword utf16); // form 2
```

## Description

Searches the file under **section** section for the variable **entry**. **Entry** is interpreted as a list of numerical values, separated by comma, tab, space, semicolon or slash. A 0x prefix indicates hex values.

## Parameters

- **section**: Section of the file as a string.
- **entry**: Variable name as a string.
- **buff**: Buffer for the read-in numerical values. Due to the **char** data type, the values must be in the range -128 .. 127 (inclusive).
- **buffsize**: Size of **buff**: Maximum number of read in numerical values (max. 1279 characters).
- **filename**: File path as a string.
- **utf16**: If this flag is set the file will be interpreted as UTF-16LE encoded, if the corresponding BOM is also present.

## Return Values

Number of numerical values read in.

## Example

See [getProfileArray](CAPLfunctionsExampleProfile.md)

**Note**: Using 256 hex values (format 0x??) and int values (format ??? plus signed) respectively as well as separators the string length is 4 * 256 + 255 = 1279 characters. The first 1279 characters are read from the ini entry and are converted to numerical values. The above mentioned format is sufficiently for 256 numerical values. Does the string contain figures with only one figure as well as separators (e.g. 3,1,4,1,5,9,2,6,5,3,5...), 640 numerical values can be read.
