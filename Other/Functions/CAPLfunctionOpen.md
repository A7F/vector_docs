[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionOpen.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » Open

# Open

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
A relative filename must be passed to this function. The absolute filename is determined by means of a search procedure. First a search is made to determine whether the given file is located in a directory of the databases. If the desired file is not found the active configuration directory is used.

## [Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- `file(char [] filename, dword access, dword mode); // form 1`
- `file(char [] filename, dword access, dword mode, dword fileEncoding); // form 2`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax (Dynamic)

- `long File::Open(char filename[], dword access, dword mode); // form 1`
- `long File::Open(char filename[], dword access, dword mode, dword fileEncoding); // form 2`

## Description

This function opens the **filename** file.

- If `access = 0`, the file is opened for write access;  
  if `access = 1` the file is opened for read access.
- Use `mode = 0` to open the file in text mode;  
  Use `mode = 1` to open the file in binary mode;
- Use `mode = 2` to append data at the end of the file in text mode;  
  Use `mode = 3` to append data at the end of the file in binary mode;

## Parameters

- **filename**: The name of the file
- **access**: 0 for write access, 1 for read access
- **mode**: 0 for text mode, 1 for binary mode, 2 for append in text mode, 3 for append in binary mode. Appending requires write access.
- **fileEncoding**: Identifier of the Microsoft code page that is used to encode the file.

## Return Values

- — (constructor)
- > 0 on success, 0 on error (method)

## Example

```plaintext
file f;
f.open("test.txt", 0, 0);
f.WriteString("Hello", 6);
f.Close();

// alternatively, use constructor / destructor:
{
    file f("test.txt", 0, 0);
    f.WriteString("Hello", 6);
}
```

[Class: File](../../ObjectOrientedProg/CAPLfunctionsOOPFile.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
