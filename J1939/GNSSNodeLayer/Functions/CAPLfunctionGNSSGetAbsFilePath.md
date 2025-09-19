[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSGetAbsFilePath.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSGetAbsFilePath

# GNSSGetAbsFilePath

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
In contrast to `getAbsFilePath()`, this function is available in case of a distributed environment.

## Function Syntax

```plaintext
long GNSSGetAbsFilePath( char file [], char fileNameWithAbsPath[], long absPathLen )
```

## Description

This function gets the absolute path of a file.

**Functionality**

1. Extract the filename only and check if the file is registered as a "user file". If yes the obtained full path is obtained.
2. Check if the "file" contains the absolute path. If yes this path is obtained.
3. Check if the "file" contains the relative path. If yes –the absolute path based on the location of the current configuration is obtained.

## Parameters

- **file**  
  The file can be defined:
  - with the filename only
  - with the filename and relative path to the current configuration
  - with the absolute path

- **fileNameWithAbsPath**  
  buffer to which the full path name should be copied

- **absPathLen**  
  size of the buffer in bytes for the full path name.

## Return Values

[Error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```plaintext
on key 'x'
{
  char absPath[256];

  GNSSGetAbsFilePath("Test.can", absPath, 256);
  write ("absPath 1: %s ", absPath);

  GNSSGetAbsFilePath("Nodes\\Test.can", absPath, 256);
  write ("absPath 1: %s ", absPath);

  GNSSGetAbsFilePath("C:\\Nodes\\Test.can", absPath, 256);
  write ("absPath 1: %s ", absPath);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
