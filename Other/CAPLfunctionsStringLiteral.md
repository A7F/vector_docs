[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLfunctionsStringLiteral.md)

[CAPL Functions](../CAPLfunctions.md) » [General](CAPLGeneralStartPage.md) » String Literal

# String Literal

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

A string literal is a character string in quotation marks: "This is a character string"

**Note**  
Like in the C language, when storing string literals in char arrays, one char at the end of the array needs to be reserved for the string termination character (/0), i.e. the char array needs to be one element longer than the pure string length.

## Escape Sequences

Certain characters are displayed as a combination of characters with a preceding backslash (escape sequence) within a character string, e.g:

- **Description**: New line  
  **Display Inside Character Strings**: `\n`

- **Description**: Tabulator  
  **Display Inside Character Strings**: `\t`

- **Description**: Backslash  
  **Display Inside Character Strings**: `\\`

- **Description**: Carriage return  
  **Display Inside Character Strings**: `\r`

- **Description**: Backspace  
  **Display Inside Character Strings**: `\b`

- **Description**: Double quotation mark  
  **Display Inside Character Strings**: `\"`

- **Description**: Single quotation mark  
  **Display Inside Character Strings**: `\'`

**Note**  
The CAPL string encoding usually matches the encoding of the source file. When you create a file with the CAPL Browser, it will save the file in an encoding which matches the language settings of your computer and write the encoding in a special comment at the beginning of the file. If the source file is encoded in UTF-16 or if an include file has a different encoding than the source file, the CAPL string encoding will be UTF-8.

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
