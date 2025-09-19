[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetLogFileName.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setLogFileName

# setLogFileName

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `setLogFileName(char fileName[]); // form 1`
- `setLogFileName(char strLoggingBlockName[], char fileName[]); // form 2`
- `setLogFileName(char strLoggingBlockName[], char fileName[], int appendIncrementFieldCodes); // form 3`

## Description

Sets the name of the logging file. If a valid extension is given it also changes the file type.

## Parameters

- **fileName**  
  - Note: Since Version 8.5 the filename can also contain field codes. If the new filename does not contain any field code, all increment field codes from the old one will be appended (regardless of whether there are other field codes there as well). The auto increment field codes will be added to the filenames as usual. With form 3, this behavior can be suppressed with the parameter **appendIncrementFieldCodes**.
  - Example field codes:
  
```
    ...
    setLogFileName( "logFile_M{IncMeasurement}.blf" );
    ...
    // Sets the name of the logging file to logFile_MX.blf with X = current measurement index.

    ...
    setLogFileName( "logFile_ {Date}.blf" );
    ...
    // Sets the name of the logging file to logFile_YYYY-MM-DD.blf with YYYY-MM-DD = current system date.
    ```

  - The name may be an absolute path, a single filename or a relative path. If an absolute path or a relative path is supplied, all non existing directories of the path will be created. The logging file will be placed in the directory of the current configuration, if a single filename is supplied, or in the path relative to the configuration file if a relative path is supplied. The directories of the path must be separated by a backslash ('\'). The filename can contain a filename extension. If no extension is input, the last used file type will be set automatically. If an invalid extension is given the function will do nothing.
  - Note: Within a [string literal](../CAPLfunctionsStringLiteral.md) a second backslash has to be set (see example).
  - The new name will only be changed with a new `setLogFileName` call or by a corresponding entry in the configuration dialog of the logging file.
  - If the Logging Block does not log (logging is not active) the name is changed immediately.
  - If the Logging Block logs (logging is active) the new name will be taken over with the next trigger event or with a new measurement start.
  - Note: The name set with the `setLogFileName` function will not be saved when saving the configuration. Only the name set in the configuration dialog of the logging file will be taken over.

- **strLoggingBlockName**  
  Name of the Logging Block.

- **appendIncrementFieldCodes**  
  - 0: no field codes are appended automatically to the given file name.
  - Otherwise: If the new filename does not contain any field codes, all increment field codes from the old filename are appended to the new filename, as described in the note to parameter **fileName**.

## Return Values

—

## Example

- `setLogFileName("Logging1", "newlog");`  
  Sets the name of the logging file to "newlog" in the directory of the current configuration.

- `setLogFileName("Logging1", "c:\\canw\\demo\\automot\\newlog");`  
  Sets the absolute path of the logging file.

- `setLogFileName("Logging1", "..\\Logging\\newlog");`  
  Sets the relative path of the logging file.

### Example File Type

- `setLogFileName( "newlog.blf" );`  
  Sets the name of the logging file to newlog and the file type blf

- `setLogFileName( "newlog.notSupportedExtension" );`  
  Does nothing //filename extension not valid

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
